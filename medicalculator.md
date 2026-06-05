---
layout: page
title: Medi-Calculator
permalink: /medicalculator/
main_nav: true
---

<style>
    .mc-lede {
    font-size: 1.05rem;
    margin: 0 0 1.5rem;
  }

  /* Space between tables */
#mc-results-top h4, #mc-results-bottom h4 {
    margin-top: 2em;
}

/* Fix section-by-section table column widths */
#mc-tbl-sections {
    table-layout: fixed;
    width: 100%;
}

#mc-tbl-sections th:nth-child(1),
#mc-tbl-sections td:nth-child(1) { width: 8%; }   /* Section */

#mc-tbl-sections th:nth-child(2),
#mc-tbl-sections td:nth-child(2) { width: 32%; }  /* Description */

#mc-tbl-sections th:nth-child(3),
#mc-tbl-sections td:nth-child(3) { width: 18%; }  /* Population */

#mc-tbl-sections th:nth-child(4),
#mc-tbl-sections td:nth-child(4) { width: 18%; }  /* Effect */

#mc-tbl-sections th:nth-child(5),
#mc-tbl-sections td:nth-child(5) { width: 14%; }  /* State Share */

#mc-tbl-sections th:nth-child(6),
#mc-tbl-sections td:nth-child(6) { width: 14%; }  /* 10-yr */

/* Wrap text in cells rather than overflow */
#mc-tbl-sections td {
    word-wrap: break-word;
    vertical-align: top;
}
</style>

<h2 style="text-align:center"><i>How the "Big Beautiful Bill" Actually Changes Medicaid Funding</i></h2>

<p class="mc-lede">
  Nearly a year after the passage of the One Big Beautiful Bill Act (OBBBA), state officials and observers across the country are working to understand its effect on Medicaid. This tool provides clarity by quantifying how the Act will impact federal Medicaid outlays going forward.</p>
  
  <p>Select your desired state from the maps or dropdown below and the calculator will automatically populate a series of tables and charts illustrating the <strong>10-year Medicaid fiscal outlook projection</strong> based on the OBBBA's changes. This tool is derived from research presented in <a href="https://papers.ssrn.com/sol3/papers.cfm?abstract_id=6833362">Medi-Cal and One Big Beautiful Bill: Federal Medicaid Reforms and the Fiscal Premise of California's Billionaire Tax Act</a>.</p>

<p>The OBBBA included 22 sections that made substantial alterations to the program, namely the introduction of work and community engagement requirements for able-bodied individuals and new limits to provider taxes. Each is described beneath the tool.</p>

<script src="https://cdn.plot.ly/plotly-2.27.0.min.js"></script>

<h3 style="text-align:center">The National Picture: Federal Medicaid Reduction by State (10-yr, 2025–2034)</h3>
<p>This map shows the projected change in annual federal Medicaid outlays received by each state resulting from the OBBBA. Darker shading indicates larger reductions in federal spending. Click any state to populate the calculator below.</p>
<div id="mc-map" style="height:450px;width:100%"></div>
<p style="font-size:0.85rem;color:#555">Notes: Projected change in annual federal Medicaid outlays under the OBBBA, by state. Darker shading indicates larger reductions in federal spending. Authors' calculations based on CBO, KFF, and MACPAC data. Click any state to populate the calculator below.</p>

<h3 style="text-align:center">Federal Medicaid Reduction by Expansion State (10-yr, 2025–2034)</h3>
<p>This map shows projected federal Medicaid spending reductions among the 40 states (and the District of Columbia) that have adopted Medicaid expansion under the Affordable Care Act (ACA). Gray states have not expanded Medicaid.</p>
<div id="mc-map3" style="height:450px;width:100%"></div>
<p style="font-size:0.85rem;color:#555">Notes: Projected federal Medicaid spending reductions among the 40 states (and the District of Columbia) that have adopted Medicaid expansion under the Affordable Care Act (ACA). Gray states have not adopted Medicaid expansion. Authors' calculations based on CBO, KFF, and MACPAC data. </p>

<h3 style="text-align:center">Federal Medicaid Reduction by Non-Expansion State (10-yr, 2025–2034)</h3>
<p>This map shows projected federal Medicaid spending reductions among the 10 states that have not adopted Medicaid expansion. Gray states expanded Medicaid.</p>
<div id="mc-map4" style="height:450px;width:100%"></div>
<p style="font-size:0.85rem;color:#555">Notes: Projected federal Medicaid spending reductions among the 10 states that have not adopted Medicaid expansion. Gray states have adopted Medicaid expansion. Authors' calculations based on CBO, KFF, and MACPAC data. </p>

<h3 style="text-align:center">MCO Spending as Share of Total Medicaid Spending (FY 2024)</h3>
<p>This map shows the share of each state's Medicaid financing derived from managed care organization (MCO) taxes and provider taxes. Darker shading indicates greater reliance on these tax financing mechanisms, which the OBBBA limits. N/A states (Alabama, Alaska, Connecticut, Idaho, Maine, Montana, South Dakota, Vermont, Wyoming) have no contracts with comprehensive MCOs.</p>
<div id="mc-map2" style="height:450px;width:100%"></div>
<p style="font-size:0.85rem;color:#555">Notes: Share of state Medicaid financing derived from managed care organization (MCO) taxes and provider taxes, by state. Darker shading indicates greater reliance on provider tax financing mechanisms. N/A states (Alabama, Alaska, Connecticut, Idaho, Maine, Montana, South Dakota, Vermont, Wyoming) have no contracts with comprehensive MCOs. KFF State Health Facts, FY 2024.</p>

<hr>

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
    <div id="mc-results-top" style="display:none">
        <h3 id="mc-state-heading"></h3>
        <!-- Headline Metrics -->
        <div id="mc-metrics">
            <div class="mc-metric">
                <div class="mc-metric-label">Federal Reduction (10-yr)</div>
                <div class="mc-metric-value" id="mc-m-fed"></div>
            </div>
            <div class="mc-metric">
                <div class="mc-metric-label">State Budget Scenario (i): Policy goes into effect and state does not backfill the difference. </div>
                <div class="mc-metric-value" id="mc-m-sub"></div>
            </div>
            <div class="mc-metric">
                <div class="mc-metric-label">State Budget Scenario (ii): Policy goes into effect and state backfills the difference. </div>
                <div class="mc-metric-value" id="mc-m-slb"></div>
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
        <h4>Allocating the Effects</h4>
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

<div id="mc-static">
    <!-- Static Text-->
<h2 style="text-align: center;">Use and Interpretation</h2>

<p>Upon selecting your desired state, a short dashboard of key projections populate, including the state's 10-year federal budget reduction due to the OBBBA and the impact on the state budget under two scenarios. Scenario (i) projects the budget impact if the state chooses not to backfill the difference to providers, causing a larger loss for providers and patients while resulting in greater savings to the state. Scenario (ii) projects the budget impact if the state chooses to backfill the difference to providers, providing a smaller loss for providers and patients while resulting in greater expenses for the state. The projected range for the budget impact on Medicaid providers and patients is provided as well. Whether the selected state is an “Expansion State” or “Non-Expansion State” is demarcated at the top of the page next to the state name.</p>

<p><strong>“Annual Federal Reductions”</strong> lays out the annual breakdown of federal Medicaid reductions by states, with additional columns depicting its cumulative impact over the 10-year outlook period and the share of total funds by year.</p>

<p><strong>“Allocating the Effects”</strong> lists the annual breakdown of the OBBBA’s impact on the state budget and Medicaid providers under Scenarios (i) and (ii). Scenario (i) reflects the State Budget Low ($B) and Providers High ($B) results. Scenario (ii) reflects the State Budget High ($B) and Providers Low ($B) results.</p>

<p>Medi-Calculator also populates twin visualizations presenting the OBBBA’s 10-year impact on (1) federal Medicaid spending and (2) total (federal and state) Medicaid spending, relative to the pre-OBBBA baseline.</p>

</div>

<div id="mc-results-bottom" style="display:none">
    <!-- mc-chart2 (Figure xx2) and anything else below -->
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
</div>

<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.1/chart.umd.min.js"></script>

<script>

    const MCO_PCT = {
    'Alabama': null, 'Alaska': null, 'Arizona': 82.0, 'Arkansas': 9.0,
    'California': 45.0, 'Colorado': 3.0, 'Connecticut': null, 'Delaware': 78.0,
    'DC': 43.0, 'Florida': 65.0, 'Georgia': 37.0, 'Hawaii': 80.0,
    'Idaho': null, 'Illinois': 69.0, 'Indiana': 42.0, 'Iowa': 91.0,
    'Kansas': 90.0, 'Kentucky': 70.0, 'Louisiana': 72.0, 'Maine': null,
    'Maryland': 38.0, 'Massachusetts': 42.0, 'Michigan': 49.0, 'Minnesota': 45.0,
    'Mississippi': 50.0, 'Missouri': 29.0, 'Montana': null, 'Nebraska': 58.0,
    'Nevada': 48.0, 'New Hampshire': 35.0, 'New Jersey': 63.0, 'New Mexico': 77.0,
    'New York': 53.0, 'North Carolina': 57.0, 'North Dakota': 14.0, 'Ohio': 45.0,
    'Oklahoma': 18.0, 'Oregon': 56.0, 'Pennsylvania': 67.0, 'Rhode Island': 60.0,
    'South Carolina': 57.0, 'South Dakota': null, 'Tennessee': 67.0, 'Texas': 62.0,
    'Utah': 41.0, 'Vermont': null, 'Virginia': 54.0, 'Washington': 36.0,
    'West Virginia': 43.0, 'Wisconsin': 25.0, 'Wyoming': null
};

    const STATE_ABBREV = {
        'Alabama':'AL','Alaska':'AK','Arizona':'AZ','Arkansas':'AR','California':'CA',
        'Colorado':'CO','Connecticut':'CT','Delaware':'DE','DC':'DC','Florida':'FL',
        'Georgia':'GA','Hawaii':'HI','Idaho':'ID','Illinois':'IL','Indiana':'IN',
        'Iowa':'IA','Kansas':'KS','Kentucky':'KY','Louisiana':'LA','Maine':'ME',
        'Maryland':'MD','Massachusetts':'MA','Michigan':'MI','Minnesota':'MN',
        'Mississippi':'MS','Missouri':'MO','Montana':'MT','Nebraska':'NE','Nevada':'NV',
        'New Hampshire':'NH','New Jersey':'NJ','New Mexico':'NM','New York':'NY',
        'North Carolina':'NC','North Dakota':'ND','Ohio':'OH','Oklahoma':'OK',
        'Oregon':'OR','Pennsylvania':'PA','Rhode Island':'RI','South Carolina':'SC',
        'South Dakota':'SD','Tennessee':'TN','Texas':'TX','Utah':'UT','Vermont':'VT',
        'Virginia':'VA','Washington':'WA','West Virginia':'WV','Wisconsin':'WI','Wyoming':'WY'
    };
    const ABBREV_STATE = Object.fromEntries(Object.entries(STATE_ABBREV).map(([k,v])=>[v,k]));

    let allStateTotals = {};

    function precomputeAll() {
        for (const state of Object.keys(STATE_PARAMS)) {
            allStateTotals[state] = compute(state).totals;
        }
    }

    let mcMap = null;

    function renderMap(selectedState) {
        const locations = [], values = [], text = [];

        for (const [state, abbrev] of Object.entries(STATE_ABBREV)) {
            if (!allStateTotals[state]) continue;
            const fed = allStateTotals[state].fed / 1000; //billions
            locations.push(abbrev);
            values.push(+fed.toFixed(2));
            text.push(`<b>${state}</b><br>Federal reduction: ${(fed).toFixed(2)}B`);
        }
    
    const trace = {
        type: 'choropleth',
        locationmode: 'USA-states',
        locations,
        z: values,
        text,
        hovertemplate: '%{text}<extra></extra>',
        colorscale: [
            [0, '#1a5276'],
            [0.5, '#f5f5f5']
            [1,'#7b241c']],
        colorbar: { title: '10-yr ($B)', thickness: 15},
        marker: {
            line: {
                color: locations.map(a =>
                    selectedState && STATE_ABBREV[selectedState] === a ? '#e74c3c' : '#fff'
                ),
                width: locations.map(a =>
                    selectedState && STATE_ABBREV[selectedState] === a ? 3 : 0.5
                )
            }
        }
    }

    const layout = {
        geo: { scope: 'usa', showlakes: false},
        margin: { t: 10, b: 0, l: 0, r: 0 },
        paper_bgcolor: 'rgba(0,0,0,0)',
        plot_bgcolor: 'rgba(0,0,0,0)'
    };

    if (mcMap) {
        Plotly.react('mc-map', [trace], layout);
    } else {
        Plotly.newPlot('mc-map', [trace], layout, { displayModeBar: false });
        document.getElementById('mc-map').on('plotly_click', data => {
            const abbrev = data.points[0].location;
            const state = ABBREV_STATE[abbrev];
            if (state) {
                document.getElementById('mc-state-select').value = state;
                onStateChange(state);
            }
        });
        mcMap = true;
    }
}

    let mcMCOMap = null;

    function renderMCOMap() {
        const locations = [], values = [], text = [];

        for (const [state, abbrev] of Object.entries(STATE_ABBREV)) {
            const pct = MCO_PCT[state];
            locations.push(abbrev);
            values.push(pct !== null ? pct : -1);
            text.push(pct !== null
                ? `<b>${state}</b><br>MCO spending: ${pct}% of total Medicaid`
                : `<b>${state}</b><br>No MCO contracts (N/A)`
            );
        }
        
        const trace = {
            type: 'choropleth',
            locationmode: 'USA-states',
            locations,
            z: values,
            text,
            hovertemplate: '%{text}<extra></extra>',
            colorscale: [[0, '#fadbd8'], [1, '#7b241c']],
            zmin: 0, zmax: 100,
            colorbar: { title: '% MCO', thickness: 15 },
            marker: { line: { color: '#fff', width: 0.5}}
        };

        const layout = {
            geo: { scope: 'usa', showlakes: false },
            margin: { t: 10, b: 0, l: 0, r: 0 },
            paper_bgcolor: 'rgba(0,0,0,0)',
            plot_bgcolor: 'rgba(0,0,0,0)'
        };

        if (mcMCOMap) {
            Plotly.react('mc-map2', [trace], layout);
        } else {
            Plotly.newPlot('mc-map2', [trace], layout, { displayModeBar: false});
            mcMCOMap = true;
        }
    }

    let mcMap3 = null;

function renderExpansionMap(selectedState) {
    const locData = [], valData = [], textData = [];
    const locGray = [], textGray = [];

    for (const [state, abbrev] of Object.entries(STATE_ABBREV)) {
        if (!allStateTotals[state]) continue;
        const fed = allStateTotals[state].fed / 1000;
        const isExp = STATE_PARAMS[state] && STATE_PARAMS[state].is_expansion;
        if (isExp) {
            locData.push(abbrev);
            valData.push(+fed.toFixed(2));
            textData.push(`<b>${state}</b><br>Federal reduction: ${fed.toFixed(2)}B`);
        } else {
            locGray.push(abbrev);
            textGray.push(`<b>${state}</b><br>Non-expansion state`);
        }
    }

    const traceData = {
        type: 'choropleth', locationmode: 'USA-states',
        locations: locData, z: valData, text: textData,
        hovertemplate: '%{text}<extra></extra>',
        colorscale: 'Greens',
        colorbar: { title: '10-yr ($B)', thickness: 15 },
        marker: {
            line: {
                color: locData.map(a =>
                    selectedState && STATE_ABBREV[selectedState] === a ? '#e74c3c' : '#fff'
                ),
                width: locData.map(a =>
                    selectedState && STATE_ABBREV[selectedState] === a ? 3 : 0.5
                )
            }
        }
    };

    const traceGray = {
        type: 'choropleth', locationmode: 'USA-states',
        locations: locGray, z: locGray.map(() => 0), text: textGray,
        hovertemplate: '%{text}<extra></extra>',
        colorscale: 'Inferno',
        zmin: 0, zmax: 1, showscale: false,
        marker: { line: { color: '#fff', width: 0.5 } }
    };

    const layout = {
        geo: { scope: 'usa', showlakes: false },
        margin: { t: 10, b: 0, l: 0, r: 0 },
        paper_bgcolor: 'rgba(0,0,0,0)', plot_bgcolor: 'rgba(0,0,0,0)'
    };

    if (mcMap3) {
        Plotly.react('mc-map3', [traceData, traceGray], layout);
    } else {
        Plotly.newPlot('mc-map3', [traceData, traceGray], layout, { displayModeBar: false });
        document.getElementById('mc-map3').on('plotly_click', data => {
            const abbrev = data.points[0].location;
            const state = ABBREV_STATE[abbrev];
            if (state && STATE_PARAMS[state] && STATE_PARAMS[state].is_expansion) {
                document.getElementById('mc-state-select').value = state;
                onStateChange(state);
            }
        });
        mcMap3 = true;
    }
}

let mcMap4 = null;

function renderNonExpansionMap(selectedState) {
    const locData = [], valData = [], textData = [];
    const locGray = [], textGray = [];

    for (const [state, abbrev] of Object.entries(STATE_ABBREV)) {
        if (!allStateTotals[state]) continue;
        const fed = allStateTotals[state].fed / 1000;
        const isExp = STATE_PARAMS[state] && STATE_PARAMS[state].is_expansion;
        if (!isExp) {
            locData.push(abbrev);
            valData.push(+fed.toFixed(2));
            textData.push(`<b>${state}</b><br>Federal reduction: ${fed.toFixed(2)}B`);
        } else {
            locGray.push(abbrev);
            textGray.push(`<b>${state}</b><br>Expansion state`);
        }
    }

    const traceData = {
        type: 'choropleth', locationmode: 'USA-states',
        locations: locData, z: valData, text: textData,
        hovertemplate: '%{text}<extra></extra>',
        colorscale: 'YIOrRd',
        colorbar: { title: '10-yr ($B)', thickness: 15 },
        marker: {
            line: {
                color: locData.map(a =>
                    selectedState && STATE_ABBREV[selectedState] === a ? '#e74c3c' : '#fff'
                ),
                width: locData.map(a =>
                    selectedState && STATE_ABBREV[selectedState] === a ? 3 : 0.5
                )
            }
        }
    };

    const traceGray = {
        type: 'choropleth', locationmode: 'USA-states',
        locations: locGray, z: locGray.map(() => 0), text: textGray,
        hovertemplate: '%{text}<extra></extra>',
        colorscale: [[0, '#bdc3c7'], [1, '#bdc3c7']],
        zmin: 0, zmax: 1, showscale: false,
        marker: { line: { color: '#fff', width: 0.5 } }
    };

    const layout = {
        geo: { scope: 'usa', showlakes: false },
        margin: { t: 10, b: 0, l: 0, r: 0 },
        paper_bgcolor: 'rgba(0,0,0,0)', plot_bgcolor: 'rgba(0,0,0,0)'
    };

    if (mcMap4) {
        Plotly.react('mc-map4', [traceData, traceGray], layout);
    } else {
        Plotly.newPlot('mc-map4', [traceData, traceGray], layout, { displayModeBar: false });
        document.getElementById('mc-map4').on('plotly_click', data => {
            const abbrev = data.points[0].location;
            const state = ABBREV_STATE[abbrev];
            if (state && STATE_PARAMS[state] && !STATE_PARAMS[state].is_expansion) {
                document.getElementById('mc-state-select').value = state;
                onStateChange(state);
            }
        });
        mcMap4 = true;
    }
}

let STATE_PARAMS = null;
let CBO_SCORES   = null;

Promise.all([
    fetch('/medicalculator_state_params.json').then(r => r.json()),
    fetch('/medicalculator_cbo_scores.json').then(r => r.json()),
    fetch('/medicalculator_population.json').then(r => r.json())
])
.then(([stateParams, cboScores, populationData]) => {
    STATE_PARAMS = stateParams;
    CBO_SCORES = cboScores;
    window.populationData = populationData;
    populateDropdown();
    precomputeAll();
    renderMap(null);
    renderMCOMap();
    renderExpansionMap(null);
    renderNonExpansionMap(null);
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
    renderMap(stateName);
    renderExpansionMap(stateName);
    renderNonExpansionMap(stateName);
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
    document.getElementById('mc-results-top').style.display = 'block';
    document.getElementById('mc-results-bottom').style.display = 'block';

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

<p><strong>"Section-by-Section Federal Impact”</strong> outlines each section of the One Big Beautiful Bill Act’s impact on the Medicaid program for the selected state and delineates what population it applies to, whether it be All Populations, Long-Term Services and Supports (LTSS) Recipients, Medicaid Expansion Population, Medicare Savings Programs (MSP) Population, or State Directed Payments (SDP) States. It also classifies each section’s effect as resulting either in savings, losses, or having an indeterminate impact. The state share and 10-year federal impact is applied on a section-by-section basis.</p>

<p>This display is complemented by a listing of the OBBBA provision sections sorted by their effect type, which provides an easy reference to what provisions of the OBBBA reduce federal spending (resulting in savings), increase federal costs, or have an indeterminate impact.</p>

<hr>

<p style="margin-top: 2rem; font-size: 0.9rem; color: #666;">The academic content <a href="https://papers.ssrn.com/sol3/papers.cfm?abstract_id=6833362">[Medi-Cal and One Big Beautiful Bill: Federal Medicaid Reforms and the Fiscal Premise of California's Billionaire Tax Act]</a>, calculator methodology, and associated research are © 2026 Joshua Rauh, Tom Church, Daniel Heil, Benjamin Jaros, and John Doran. For inquiries regarding the research or calculator, please contact: <a href="mailto:hooverfpi@stanford.edu">hooverfpi@stanford.edu</a>.</p>