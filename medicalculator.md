---
layout: page
title: Medi-Calculator
permalink: /medicalculator/
main_nav: true
---

<div id="mc-container">
    <!-- INPUT -->
    <div id="mc-input">
        <label for="mc-state-select"><strong>Select a state:</strong></label>
        <select id="mc-state-select">
            <option value="">- Choose a State -</option>
        </select>
        <span id="mc-status"></span>
    </div>
    <!-- RESULTS (hide until a State is selected) -->
    <div id="mc-results" style="display:none">
        <h3 id="mc-state-heading"></h3>
        <!-- Headline Metrics -->
        <div id="mc-metrics">
            <div class="mc-metric">
                <div class="mc-metric-label">Federal Reduction (10-yr)</div>
                <div class="mc-metric-value" id="mc-m-fed"></div>
            </div>
            <div class="mc-metric">
                <div class="mc-metric-label">State Budget - Best Case</div>
                <div class="mc-metric-value" id="mc-m-slb"></div>
            </div>
            <div class="mc-metric">
                <div class="mc-metric-label">State Budget - Worst Case</div>
                <div class="mc-metric-value" id="mc-m-sub"></div>
            </div>
            <div class="mc-metric">
                <div class="mc-metric-label">Providers &amp; Patients (range)</div>
                <div class="mc-metric-value" id="mc-m-prov"></div>
            </div>
        </div>
        <!-- Annual Table -->
        <h4>Annual Federal Reductions</h4>
        <table id="mc-tbl-annual">
            <thead>
                <tr>
                    <th>Year</th>
                    <th>Annual ($B)</th>
                    <th>Cumulative ($B)</th>
                    <th>Share of Total</th>
                </tr>
            </thead>
            <tbody id="mc-tb-annual"></tbody>
        </table>
        <!-- Distributional Table -->
        <h4>Distributional Effects</h4>
        <table id="mc-tbl-dist">
            <thead>
                <tr>
                    <th>Year</th>
                    <th>Federal ($B)</th>
                    <th>State Budget Low ($B)</th>
                    <th>State Budget High ($B)</th>
                    <th>Providers Low ($B)</th>
                    <th>Providers High ($B)</th>
                </tr>
            </thead>
            <tbody id="mc-tb-dist"></tbody>
        </table>
        <!-- Section-by-Section Table -->
        <h4>Section-by-Section Federal Impact</h4>
        <table id="mc-tbl-sections">
            <thead>
                <tr>
                    <th>Section</th>
                    <th>Description</th>
                    <th>Population</th>
                    <th>Effect</th>
                    <th>State Share</th>
                    <th>10-yr ($B)</th>
                </tr>
            </thead>
            <tbody id="mc-tb-sections"></tbody>
        </table>
    <p id="mc-rht-note"><strong>§71401 Rural Health Transformation:</strong> CBO estimates $50B nationally over 2026-2030. State-specific allocations are uncertain and excluded from the figures above.</p>
    <!-- Sections grouped by effect -->
    <h4>Sections Grouped by Effect Type</h4> 
    <table id="mc-tbl-grouped">
        <thead>
            <tr>
                <th>Reduces Federal Spending (Savings)</th>
                <th>Increases Federal Cost (Loss)</th>
                <th>Indeterminate</th>
            </tr>
        </thead>
        <tbody id="mc-tb-grouped"></tbody>
    </table>
    <!-- Pre vs Post OBBBA federal spending -->
    <h4>Federal Medicaid Spending: Pre- vs. Post-OBBBA</h4>
    <p id="mc-chart-note" style="font-size:0.85rem;color:#555"></p>
    <canvas id="mc-chart" style="max-height:400px"></canvas>
    <!-- Total Medicaid Spending -->
    <h4>Total Medicaid Spending: Pre- vs. Post-OBBBA (Federal + State)</h4>
    <p id="mc-chart2-note" style="font-size:0.85rem;color:#555"></p>
    <canvas id="mc-chart2" style="max-height:400px"></canvas>
    </div><!-- /mc-results -->
   
</div><!-- /mc-container -->

<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.1/chart.umd.min.js"></script>

<script>
let STATE_PARAMS = null;
let CBO_SCORES   = null;

Promise.all([
    fetch('/medicalculator_state_params.json').then(r => r.json()),
    fetch('/medicalculator_cbo_scores.json').then(r => r.json()),
    fetch('/medicalculator_population.json').then(r => r.json())
])
.then(([stateParams, cboScores, populationData]) => {
    STATE_PARAMS      = stateParams;
    CBO_SCORES        = cboScores;
    window.populationData = populationData;
    populateDropdown();
})
.catch(err => {
    document.getElementById('mc-status').textContent = 'Error loading data: ' + err.message; 
});

function populateDropdown() {
    const sel = document.getElementById('mc-state-select');
    Object.keys(STATE_PARAMS).sort().forEach(state => {
        const opt = document.createElement('option');
        opt.value = state;
        opt.textContent = state;
        sel.appendChild(opt);
    });
    sel.addEventListener('change', () => onStateChange(sel.value));
}

const YEARS = ['2025', '2026', '2027', '2028', '2029', '2030', '2031', '2032', '2033', '2034'];
const EXPANSION_ONLY = new Set(['71107', '71110', '71112', '71119', '71120']);

function compute(stateName) {
    const p = STATE_PARAMS[stateName];
    const annual = {};
    YEARS.forEach(y => annual[y] = { fed: 0, sc: 0, loss: 0, indet: 0 });
    const sections = {};

    for (const [key, score] of Object.entries(CBO_SCORES)) {
        const { share_type, ratio_type, effect } = score.rules || {};
        if (share_type === 'rht_special') continue;
        if (!score.annual_millions) continue;

        let share = p[share_type] || 0;
        const ratio = p[ratio_type] || 0;

        if (key === '71116' && !p.sdp_affected)         share = 0;
        if (key === '71115b' && !p.prov_tax_affected)   share = 0;
        if (EXPANSION_ONLY.has(key) && !p.is_expansion) share = 0;
        if (key === '71114' && p.is_expansion)          share = 0;

        let sectionTotal = 0;
        YEARS.forEach(y => {
            const fedImpact = (score.annual_millions[y] || 0) * share;
            annual[y].fed += fedImpact;
            sectionTotal += fedImpact;
            if (effect === 'savings') annual[y].sc += -(fedImpact * ratio);
            else if (effect === 'loss') annual[y].loss += fedImpact;
            else if (effect === 'indeterminate') annual[y].indet += fedImpact;
        });

        sections[key] = { effect, share, total: sectionTotal };
    }

    let cum = 0;
    const rows = YEARS.map(y => {
        const { fed, sc, loss, indet } = annual[y];
        const slb = sc + loss;
        const sub = slb + indet;
        cum += fed;
        return { y, fed, slb, sub, plb: fed - sub, pub: fed - slb, cum };
    });

    const totFed = rows.reduce((s, r) => s + r.fed, 0);
    const totSlb = rows.reduce((s, r) => s + r.slb, 0);
    const totSub = rows.reduce((s, r) => s + r.sub, 0);

    return {
        rows,
        sections,
        params: p,
        totals: {
            fed: totFed,
            slb: totSlb,
            sub: totSub,
            plb: totFed - totSub,
            pub: totFed - totSlb
        }
    };
}

function fmt(v) {
    const b = (v / 1000).toFixed(2);
    return (v >= 0 ? '+' : '') + b + 'B';
}

function computeBaseline(stateName) {
        const p = STATE_PARAMS[stateName];
        const bl = CBO_SCORES['_baseline'];
        const years = bl.years; // 2024-2034
        const baseline = years.map((y, i) =>
        bl.national_traditional_billions[i] * p.share_traditional +
        bl.national_expansion_billions[i] * p.share_expansion
        );
        return { years, baseline };
    }

    let mcChart = null;

    function renderChart(stateName, rows) {
        const { years, baseline } = computeBaseline(stateName);

        const postOBBBA = baseline.map((b, i) => {
            if (i === 0) return b; 
            const reduction = rows[i - 1].fed / 1000;
            return baseline[i] + reduction;
        });

        document.getElementById('mc-chart-note').textContent =
            'Billions of dollars, federal Medicaid payments only. ' + 
            'Post-OBBBA line reflects CBO-scored reductions allocated to ' + stateName + '.';

        if (mcChart) mcChart.destroy();
        mcChart = new Chart(document.getElementById('mc-chart'), {
            type: 'bar',
            data: {
                labels: years,
                datasets: [
                    {
                        label: 'Pre-OBBBA Baseline',
                        data: baseline.map(v => +v.toFixed(2)),
                        backgroundColor: 'rgba(44, 62, 80, 0.75)',
                    },
                    {
                        label: 'Post-OBBBA',
                        data: postOBBBA.map(v => +v.toFixed(2)),
                        backgroundColor: 'rgba(192, 57, 43, 0.75)'
                    }
                ]
            },
            options: {
                responsive: true,
                plugins: { legend: { position: 'top' } },
                scales: { y: { title: { display: true, text: 'Billions of dollars' } } }
            }
        });    
    }

    let mcChart2 = null;

function renderChart2(stateName) {
    const { years, preArr, postArr } = computeFigureXX2(stateName);

    document.getElementById('mc-chart2-note').textContent =
        'Billions of dollars, total Medicaid payments (federal + state). ' +
        'Post-OBBBA reflects CBO-scored reductions allocated to ' + stateName + '.';

    if (mcChart2) mcChart2.destroy();
    mcChart2 = new Chart(document.getElementById('mc-chart2'), {
        type: 'bar',
        data: {
            labels: years,
            datasets: [
                {
                    label: 'Pre-OBBBA',
                    data: preArr.map(v => +v.toFixed(2)),
                    backgroundColor: 'rgba(44, 62, 80, 0.75)'
                },
                {
                    label: 'Post-OBBBA',
                    data: postArr.map(v => +v.toFixed(2)),
                    backgroundColor: 'rgba(192, 57, 43, 0.75)'
                }
            ]
        },
        options: {
            responsive: true,
            plugins: { legend: { position: 'top' } },
            scales: { y: { title: { display: true, text: 'Billions of dollars' } } }
        }
    });
}

    function renderGroupedTable(sections) {
        const savings = ['71101', '71102', '71103', '71107', '71108', '71109', '71111', '71112', '71113', '71119', '71120', '71121'];
        const losses  = ['71106', '71110', '71114'];
        const indeterminate = ['71115a', '71115b', '71116', '71117', '71118'];

        const maxRows = Math.max(savings.length, losses.length, indeterminate.length);
        let html = '';
        for (let i = 0; i < maxRows; i++) {
            const s = savings[i]? `§${savings[i]}` : '';
            const l = losses[i]? `§${losses[i]}` : '';
            const n = indeterminate[i]? `§${indeterminate[i]}` : '';
            html += `<tr><td>${s}</td><td>${l}</td><td>${n}</td></tr>`;
        }
        document.getElementById('mc-tb-grouped').innerHTML = html;
    }

function computeFigureXX2(stateName) {
    const p = STATE_PARAMS[stateName];
    const bl = CBO_SCORES['_baseline'];
    const years = bl.years;
    const preArr = [], postArr = [];

    for (let i = 0; i < years.length; i++) {
        const y = years[i];
        const fedTrad  = bl.national_traditional_billions[i] * p.share_traditional;
        const fedExp   = p.is_expansion ? bl.national_expansion_billions[i] * p.share_expansion : 0;
        const preTotal = fedTrad + fedExp + (fedTrad * p.ratio_traditional) + (p.is_expansion ? fedExp * p.ratio_expansion : 0);
        preArr.push(preTotal);

        let fedTotal_M = 0, stateLB_M = 0;
        for (const [code, score] of Object.entries(CBO_SCORES)) {
            if (code === '_baseline' || !score.annual_millions) continue;
            const { share_type, ratio_type, effect } = score.rules || {};
            if (share_type === 'rht_special') continue;
            let share = p[share_type] || 0;
            const ratio = p[ratio_type] || 0;
            if (code === '71116'  && !p.sdp_affected)        share = 0;
            if (code === '71115b' && !p.prov_tax_affected)   share = 0;
            if (EXPANSION_ONLY.has(code) && !p.is_expansion) share = 0;
            if (code === '71114'  && p.is_expansion)         share = 0;
            const fedImpact_M = (score.annual_millions[y] || 0) * share;
            fedTotal_M += fedImpact_M;
            if (effect === 'savings') stateLB_M += -(fedImpact_M * ratio);
        }
        postArr.push(preTotal + (fedTotal_M - stateLB_M) / 1000);
    }
    return { years, preArr, postArr };
}

function onStateChange(stateName) {
    if (!stateName) return;
    const { rows, sections, params, totals } = compute(stateName);

    // State heading
    const expansion = params.is_expansion ? 'Expansion State' : 'Non-Expansion State';
    document.getElementById('mc-state-heading').textContent = stateName + ' - ' + expansion;

    // Headline metrics
    document.getElementById('mc-m-fed').textContent  = fmt(totals.fed);
    document.getElementById('mc-m-slb').textContent  = fmt(totals.slb);
    document.getElementById('mc-m-sub').textContent  = fmt(totals.sub);
    document.getElementById('mc-m-prov').textContent = fmt(totals.plb) + ' to ' + fmt(totals.pub);

    // show results
    document.getElementById('mc-results').style.display = 'block';

    // Annual table
    let annualHtml = '';
    rows.forEach(r => {
        const pct = totals.fed !== 0 ? (r.fed / totals.fed * 100).toFixed(1) + '%' : '-';
        annualHtml += `<tr>
            <td>${r.y}</td>
            <td>${fmt(r.fed)}</td>
            <td>${fmt(r.cum)}</td>
            <td>${pct}</td>
        </tr>`;
    });
    annualHtml += `<tr>
        <td><strong>2025-2034</strong></td>
        <td><strong>${fmt(totals.fed)}</strong></td>
        <td><strong>${fmt(totals.fed)}</strong></td>
        <td><strong>100%</strong></td>
    </tr>`;
    document.getElementById('mc-tb-annual').innerHTML = annualHtml;

    // Distributional table
    let distHtml = '';
    rows.forEach(r => {
        distHtml += `<tr>
            <td>${r.y}</td>
            <td>${fmt(r.fed)}</td>
            <td>${fmt(r.slb)}</td>
            <td>${fmt(r.sub)}</td>
            <td>${fmt(r.plb)}</td>
            <td>${fmt(r.pub)}</td>
        </tr>`;
    });
    distHtml += `<tr>
        <td><strong>2025-2034</strong></td>
        <td><strong>${fmt(totals.fed)}</strong></td>
        <td><strong>${fmt(totals.slb)}</strong></td>
        <td><strong>${fmt(totals.sub)}</strong></td>
        <td><strong>${fmt(totals.plb)}</strong></td>
        <td><strong>${fmt(totals.pub)}</strong></td>
    </tr>`;
    document.getElementById('mc-tb-dist').innerHTML = distHtml;

    renderChart(stateName, rows);
    renderChart2(stateName);
    renderGroupedTable(sections);

    // Section-by-section table
    const SECTION_META = {
        '71101': ['MSP Population',   'Moratorium - Medicare Savings Programs enrollment rule'],
        '71102': ['All',               'Moratorium - Medicaid/CHIP/BHP eligibility rule'],
        '71103': ['All',               'Reduce duplicate enrollment'],
        '71104': ['All',               'Deceased provider enrollment (de minimis)'],
        '71105': ['All',               'Deceased provider enrollment (de minimis)'],
        '71106': ['All',               'Reduce erroneous excess payments'],
        '71107': ['Expansion Pop.',    'Eligibility redeterminations'],
        '71108': ['LTSS Recipients',   'Revise home equity limits for LTC eligibility'],
        '71109': ['All',               'Medicaid eligibility for non-citizens'],
        '71110': ['Expansion Pop.',    'Expansion FMAP for emergency Medicaid'],
        '71111': ['LTSS Recipients',   'Moratorium - LTC staffing rule'],
        '71112': ['Expansion Pop.',    'Reduce state Medicaid costs'],
        '71113': ['All',               'Restrict payments to prohibited entities'],
        '71114': ['Non-Expansion',     'Sunset enhanced FMAP incentive'],
        '71115a': ['All',              'Provider tax limits - all states'],
        '71115b': ['Expansion States', 'Provider tax limits - expansion states'],
        '71116': ['SDP States',        'State-directed payment limits'],
        '71117': ['All',               'Waivers of uniform tax requirements'],
        '71118': ['All',               'Budget neutrality for §1115 waivers'],
        '71119': ['Expansion Pop.',    'Community engagement requirements'],
        '71120': ['Expansion Pop.',    'Cost sharing for expansion population'],
        '71121': ['All',               'Adjust HCBS coverage'],
        '71401': ['Expansion States',  'Rural Health Transformation Program'],
        'interactions': ['All',        'Medicaid share of health reform interactions'],
    };

    const SECTION_ORDER = [
        '71101', '71102', '71103', '71104', '71105', '71106', '71107', '71108', '71109', '71110',
        '71111', '71112', '71113', '71114', '71115a', '71115b', '71116', '71117', '71118', '71119',
        '71120', '71121', '71401', 'interactions'
    ];

    let secHtml = '';
    SECTION_ORDER.forEach(key => {
        const sec = sections[key];
        if (!sec) return;
        const [pop, desc] = SECTION_META[key] || ['', ''];
        const isRHT = (key === '71401');
        const isZero = Math.abs(sec.total) < 0.5;
        const effectLabel = isRHT ? 'Grant' : isZero ? '-' : sec.effect;
        const shareStr    = isZero ? '-' : (sec.share * 100).toFixed(2) + '%';
        const impactStr   = isRHT ? 'excl.' : isZero ? '-' : fmt(sec.total);
        secHtml += `<tr>
            <td>§${key}</td>
            <td>${desc}</td>
            <td>${pop}</td>
            <td>${effectLabel}</td>
            <td>${shareStr}</td>
            <td>${impactStr}</td>
        </tr>`;
    });
    document.getElementById('mc-tb-sections').innerHTML = secHtml;
}


</script>

