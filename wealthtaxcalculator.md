---
layout: page
title: Wealth Tax Calculator
permalink: /wealthtaxcalculator/
main_nav: true
---
<style>
  /* Wealth Tax Calculator */
  html { scroll-behavior: smooth; }

  .wtc-lede {
    font-size: 1.05rem;
    margin: 0 0 1.5rem;
  }

  .wtc-card {
    max-width: 640px;
    margin: 0 auto 2.5rem;
    padding: 1.5rem;
    border: 1px solid #e0e0e0;
    border-radius: 8px;
    background: #fafafa;
    box-shadow: 0 1px 3px rgba(0,0,0,0.06);
  }

  .wtc-card h2 { margin-top: 0; text-align: center; }

  .wtc-card-sub {
    text-align: center;
    color: #666;
    margin-top: 0;
    margin-bottom: 1.5rem;
    font-size: 0.95rem;
  }

  .wtc-field { margin: 1rem 0; }

  .wtc-field label {
    display: block;
    margin-bottom: 0.35rem;
    font-weight: 600;
  }

  .wtc-help {
    display: block;
    font-size: 0.85rem;
    color: #666;
    font-weight: normal;
    margin-top: 0.15rem;
  }

  .wtc-input-wrap { position: relative; }

  .wtc-card select,
  .wtc-card input[type="number"] {
    width: 100%;
    padding: 0.55rem 0.7rem;
    font-size: 1rem;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-sizing: border-box;
    background: #fff;
  }

  .wtc-card input[type="number"] { padding-right: 2rem; }

  .wtc-suffix {
    position: absolute;
    right: 0.7rem;
    top: 50%;
    transform: translateY(-50%);
    color: #888;
    pointer-events: none;
  }

  .wtc-status {
    display: block;
    font-size: 0.8rem;
    color: #888;
    margin-top: 0.25rem;
    min-height: 1em;
  }

  .wtc-status.is-error { color: #B3173C; }

  .wtc-buttons {
    display: flex;
    gap: 0.5rem;
    margin-top: 1.25rem;
  }

  .wtc-btn {
    flex: 1;
    padding: 0.75rem 1rem;
    font-size: 1rem;
    font-weight: 600;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-family: inherit;
  }

  .wtc-btn-primary {
    background-color: #B3173C;
    color: #fff;
  }

  .wtc-btn-primary:hover { background-color: #8C1515; }

  .wtc-btn-secondary {
    background-color: transparent;
    color: #B3173C;
    border: 1px solid #B3173C;
  }

  .wtc-btn-secondary:hover { background-color: #fbe6eb; }

  .wtc-error {
    margin-top: 1rem;
    padding: 0.75rem 1rem;
    background-color: #fdecef;
    border-left: 4px solid #B3173C;
    color: #8C1515;
    border-radius: 4px;
    display: none;
  }

  .wtc-error.is-visible { display: block; }

  .wtc-results {
    margin-top: 1.5rem;
    padding: 1.25rem;
    background-color: #fff;
    border: 1px solid #e0e0e0;
    border-radius: 6px;
    display: none;
  }

  .wtc-results.is-visible { display: block; }

  .wtc-headline {
    text-align: center;
    margin: 0 0 1rem;
    padding-bottom: 1rem;
    border-bottom: 1px solid #eee;
  }

  .wtc-headline-label {
    display: block;
    font-size: 0.8rem;
    text-transform: uppercase;
    letter-spacing: 0.04em;
    color: #666;
    margin-bottom: 0.25rem;
  }

  .wtc-headline-value {
    font-size: 2rem;
    font-weight: 700;
    color: #B3173C;
    font-variant-numeric: tabular-nums;
  }

  .wtc-breakdown {
    width: 100%;
    border-collapse: collapse;
    font-size: 0.95rem;
    margin: 0;
  }

  .wtc-breakdown td {
    padding: 0.35rem 0.5rem;
    border: none;
  }

  .wtc-breakdown td:last-child {
    text-align: right;
    font-variant-numeric: tabular-nums;
    white-space: nowrap;
  }

  .wtc-breakdown tr.is-total td {
    border-top: 1px solid #ddd;
    font-weight: 700;
    padding-top: 0.55rem;
  }

  .wtc-rho {
    margin-top: 1rem;
    padding-top: 1rem;
    border-top: 1px solid #eee;
    text-align: center;
    font-size: 0.95rem;
  }

  .wtc-rho-value {
    display: block;
    font-size: 1.5rem;
    font-weight: 700;
    color: #B3173C;
    font-variant-numeric: tabular-nums;
    margin-top: 0.25rem;
  }

  .wtc-table-scroll {
    overflow-x: auto;
    -webkit-overflow-scrolling: touch;
  }

  .wtc-sources { margin-top: 2rem; }

  .wtc-sources summary {
    cursor: pointer;
    font-weight: 600;
    padding: 0.5rem 0;
    font-size: 1.1rem;
  }

  @media (max-width: 600px) {
    .wtc-card { padding: 1rem; }
    .wtc-headline-value { font-size: 1.6rem; }
    .wtc-buttons { flex-direction: column; }
  }
</style>

<p class="wtc-lede">
  This tool quantifies the <strong>equivalent capital income tax rate (t*)</strong> of a wealth tax — the income-tax rate on capital that would produce the same economic outcome as living under a given wealth tax — and reports the <strong>required pre-tax return (ρ)</strong> investors must demand to compensate for the recurring expropriation risk. State and federal capital gains taxes are layered in optionally.
</p>

<div id="calculator"></div>

<section class="wtc-card" aria-labelledby="wtc-calc-heading">
  <h2 id="wtc-calc-heading">Calculator</h2>
  <p class="wtc-card-sub">Pick a jurisdiction, enter a wealth tax rate and a risk-free rate. Results update as you type.</p>

  <div class="wtc-field">
    <label for="state">
      Jurisdiction
      <span class="wtc-help">Determines the state, city, and federal capital gains tax layered on top of t*.</span>
    </label>
    <select id="state">
      <optgroup label="Quick selects">
        <option value="0">United States (federal only)</option>
        <option value="0.0522">U.S. national average</option>
      </optgroup>
      <optgroup label="U.S. states">
        <option value="0.05">Alabama</option>
        <option value="0">Alaska</option>
        <option value="0.025">Arizona</option>
        <option value="0.039">Arkansas</option>
        <option value="0.133">California</option>
        <option value="0.044">Colorado</option>
        <option value="0.096">Connecticut</option>
        <option value="0.066">Delaware</option>
        <option value="0">Florida</option>
        <option value="0.0539">Georgia</option>
        <option value="0.0725">Hawaii</option>
        <option value="0.053">Idaho</option>
        <option value="0.0495">Illinois</option>
        <option value="0.03">Indiana</option>
        <option value="0.038">Iowa</option>
        <option value="0.0558">Kansas</option>
        <option value="0.04">Kentucky</option>
        <option value="0.0425">Louisiana</option>
        <option value="0.0715">Maine</option>
        <option value="0.0575">Maryland</option>
        <option value="0.16">Massachusetts</option>
        <option value="0.0425">Michigan</option>
        <option value="0.0985">Minnesota</option>
        <option value="0.044">Mississippi</option>
        <option value="0.0495">Missouri</option>
        <option value="0.041">Montana</option>
        <option value="0.052">Nebraska</option>
        <option value="0">Nevada</option>
        <option value="0">New Hampshire</option>
        <option value="0.1075">New Jersey</option>
        <option value="0.059">New Mexico</option>
        <option value="0.109">New York</option>
        <option value="0.045">North Carolina</option>
        <option value="0.025">North Dakota</option>
        <option value="0.035">Ohio</option>
        <option value="0.0475">Oklahoma</option>
        <option value="0.099">Oregon</option>
        <option value="0.0307">Pennsylvania</option>
        <option value="0.0599">Rhode Island</option>
        <option value="0.0358">South Carolina</option>
        <option value="0">South Dakota</option>
        <option value="0">Tennessee</option>
        <option value="0">Texas</option>
        <option value="0.0455">Utah</option>
        <option value="0.0875">Vermont</option>
        <option value="0.0575">Virginia</option>
        <option value="0.09">Washington D.C.</option>
        <option value="0.099">Washington State</option>
        <option value="0.0512">West Virginia</option>
        <option value="0.0765">Wisconsin</option>
        <option value="0">Wyoming</option>
      </optgroup>
      <optgroup label="U.S. cities">
        <option value="0.1430">New York City</option>
        <option value="0.139">Portland, Oregon</option>
      </optgroup>
      <optgroup label="International">
        <option value="0.3">France — financial assets</option>
        <option value="0.362">France — real estate (under 22 years)</option>
      </optgroup>
    </select>
  </div>

  <div class="wtc-field">
    <label for="theta1">
      Wealth tax rate (θ)
      <span class="wtc-help">The annual tax on accumulated wealth. Enter 1 for 1%. Range 0–100.</span>
    </label>
    <div class="wtc-input-wrap">
      <input type="number" id="theta1" step="0.001" min="0" max="100" inputmode="decimal" placeholder="e.g. 2">
      <span class="wtc-suffix">%</span>
    </div>
  </div>

  <div class="wtc-field">
    <label for="r1">
      Risk-free rate (r)
      <span class="wtc-help">Reference return on capital, e.g. the 30-year U.S. Treasury yield. Auto-fills on load. Range −100 to 100.</span>
    </label>
    <div class="wtc-input-wrap">
      <input type="number" id="r1" step="0.001" min="-100" max="100" inputmode="decimal" placeholder="e.g. 4.5">
      <span class="wtc-suffix">%</span>
    </div>
    <span id="r1-status" class="wtc-status"></span>
  </div>

  <div class="wtc-buttons">
    <button type="button" id="wtc-calc-btn" class="wtc-btn wtc-btn-primary" onclick="calculateAll()">Calculate</button>
    <button type="button" id="wtc-reset-btn" class="wtc-btn wtc-btn-secondary" onclick="resetCalculator()">Reset</button>
  </div>

  <div id="error1" class="wtc-error" role="alert"></div>

  <div id="result1" class="wtc-results" aria-live="polite">
    <div class="wtc-headline">
      <span class="wtc-headline-label">Comparable combined tax on capital income</span>
      <span class="wtc-headline-value" id="wtc-headline-value">—</span>
    </div>
    <table class="wtc-breakdown">
      <tbody id="wtc-breakdown-body"></tbody>
    </table>
    <div class="wtc-rho">
      Required pre-tax return on assets to compensate for expropriation risk (ρ):
      <span class="wtc-rho-value" id="wtc-rho-value">—</span>
    </div>
  </div>
</section>

<script>
(function () {
  var stateEl, thetaEl, rEl, errorEl, resultEl, headlineEl, breakdownEl, rhoEl, rStatusEl;

  function fmt(n, dp) {
    if (dp === undefined) dp = 2;
    if (!isFinite(n)) return '—';
    return n.toFixed(dp).replace(/\.?0+$/, function (m) {
      return m.indexOf('.') === 0 ? '' : m;
    });
  }

  function fmtPct(n, dp) {
    return fmt(n, dp == null ? 2 : dp) + '%';
  }

  function fetchTreasuryYield() {
    rStatusEl.textContent = 'Fetching latest 30-year Treasury rate…';
    rStatusEl.classList.remove('is-error');
    rEl.disabled = true;
    fetch('https://api.fiscaldata.treasury.gov/services/api/fiscal_service/v2/accounting/od/avg_interest_rates?filter=security_desc:eq:Treasury Bonds&sort=-record_date&page[size]=1')
      .then(function (response) { return response.json(); })
      .then(function (data) {
        rEl.disabled = false;
        if (data && data.data && data.data.length > 0) {
          var rate = parseFloat(data.data[0].avg_interest_rate_amt);
          rEl.value = rate.toFixed(3);
          rStatusEl.textContent = 'Auto-filled with the most recent 30-year Treasury bond average rate.';
          rStatusEl.classList.remove('is-error');
          recalc();
        } else {
          rStatusEl.textContent = 'Could not fetch Treasury yield — please enter a value manually.';
          rStatusEl.classList.add('is-error');
        }
      })
      .catch(function (err) {
        console.error('Error fetching Treasury yield:', err);
        rEl.disabled = false;
        rStatusEl.textContent = 'Could not reach Treasury API — please enter a value manually.';
        rStatusEl.classList.add('is-error');
      });
  }

  function showError(msg) {
    errorEl.textContent = msg;
    errorEl.classList.add('is-visible');
    resultEl.classList.remove('is-visible');
  }

  function clearError() {
    errorEl.classList.remove('is-visible');
  }

  function calculateAll() {
    clearError();

    var thetaRaw = thetaEl.value;
    var rRaw = rEl.value;

    if (thetaRaw === '' || rRaw === '') {
      resultEl.classList.remove('is-visible');
      return;
    }

    var thetaPct = parseFloat(thetaRaw);
    var rPct = parseFloat(rRaw);

    if (isNaN(thetaPct) || thetaPct < 0 || thetaPct > 100) {
      showError('Wealth tax rate (θ) must be a number between 0 and 100.');
      return;
    }
    if (isNaN(rPct) || rPct < -100 || rPct > 100) {
      showError('Risk-free rate (r) must be a number between −100 and 100.');
      return;
    }

    var theta = thetaPct / 100;
    var r = rPct / 100;
    var stateCapGainsRate = parseFloat(stateEl.value);
    var selectedStateName = stateEl.options[stateEl.selectedIndex].text;

    var isFrance = selectedStateName.indexOf('France') !== -1;
    var isNYC = selectedStateName.indexOf('New York City') !== -1;
    var isPortland = selectedStateName.indexOf('Portland') !== -1;

    var cityRate = 0;
    var actualStateRate = stateCapGainsRate;
    var cityLabel = '';

    if (isNYC) {
      cityRate = 0.034;
      actualStateRate = 0.109;
      cityLabel = 'New York City capital gains';
    } else if (isPortland) {
      cityRate = 0.04; // 1% Metro + 3% PFA
      actualStateRate = 0.099;
      cityLabel = 'Portland city (Metro + PFA)';
    }

    var federalCapGains = isFrance ? 0 : 0.20;
    var niit = isFrance ? 0 : 0.038;

    // Base equivalent capital income tax rate
    var tBase = (1 - ((r * (1 - theta)) / (r + theta))) * 100;
    if (!isFinite(tBase)) {
      showError('Cannot evaluate at these inputs (division by zero in t*).');
      return;
    }

    var combinedTax = tBase + (cityRate * 100) + (actualStateRate * 100) + (federalCapGains * 100) + (niit * 100);
    var tCombinedDecimal = combinedTax / 100;

    if (tCombinedDecimal >= 2) {
      showError('Combined tax rate equals or exceeds 200% — calculation not possible.');
      return;
    }

    var rho = r / (1 - tCombinedDecimal);
    if (rho < 0) rho = 0;
    var rhoPct = rho * 100;

    // Build breakdown rows
    var rows = [];
    rows.push(['Base equivalent capital income tax rate (t*)', fmtPct(tBase, 3)]);

    if (isFrance) {
      rows.push(['France capital gains rate', fmtPct(stateCapGainsRate * 100, 2)]);
    } else {
      if (cityRate > 0) {
        rows.push([cityLabel, fmtPct(cityRate * 100, 2)]);
      }
      rows.push(['Top state capital gains rate', fmtPct(actualStateRate * 100, 2)]);
      rows.push(['Top federal capital gains rate', '20%']);
      rows.push(['Net Investment Income Tax (NIIT)', '3.8%']);
    }

    var bodyHTML = '';
    for (var i = 0; i < rows.length; i++) {
      bodyHTML += '<tr><td>' + rows[i][0] + '</td><td>' + rows[i][1] + '</td></tr>';
    }
    bodyHTML += '<tr class="is-total"><td>Combined tax on capital income</td><td>' + fmtPct(combinedTax, 3) + '</td></tr>';

    breakdownEl.innerHTML = bodyHTML;
    headlineEl.textContent = fmtPct(combinedTax, 2);
    rhoEl.textContent = fmtPct(rhoPct, 2);
    resultEl.classList.add('is-visible');
  }

  function recalc() {
    // Live recalc on input change
    if (thetaEl.value !== '' && rEl.value !== '') {
      calculateAll();
    } else {
      clearError();
      resultEl.classList.remove('is-visible');
    }
  }

  function resetCalculator() {
    thetaEl.value = '';
    rEl.value = '';
    stateEl.selectedIndex = 0;
    clearError();
    resultEl.classList.remove('is-visible');
    fetchTreasuryYield();
  }

  // Initialize immediately — this script tag is positioned after the form,
  // so all referenced elements are already in the DOM.
  stateEl = document.getElementById('state');
  thetaEl = document.getElementById('theta1');
  rEl = document.getElementById('r1');
  errorEl = document.getElementById('error1');
  resultEl = document.getElementById('result1');
  headlineEl = document.getElementById('wtc-headline-value');
  breakdownEl = document.getElementById('wtc-breakdown-body');
  rhoEl = document.getElementById('wtc-rho-value');
  rStatusEl = document.getElementById('r1-status');

  stateEl.addEventListener('change', recalc);
  thetaEl.addEventListener('input', recalc);
  rEl.addEventListener('input', recalc);

  // Expose for inline onclick handlers on the buttons
  window.calculateAll = calculateAll;
  window.resetCalculator = resetCalculator;

  fetchTreasuryYield();
})();
</script>

<hr style="margin: 40px 0; border: 1px solid #ddd;">

<h2 style="text-align: center;">Background</h2>

<p>The recent interest in wealth taxes highlights the importance of clarifying their tradeoffs, since the absence of a familiar benchmark leads to misanchored judgments about their costs and benefits. The apparent simplicity of taxing accumulated assets conceals the effects these policies impose on economic behavior and property rights, ultimately trading short-term fiscal gains for long-term economic costs. For example, the "Zucman Tax," a 2 percent wealth tax in France and Washington state's recently proposed 1 percent wealth tax in the United States have gained traction by appealing to fairness and these taxes as a source of redistributive public sector revenue.</p>

<p>Surveys suggest that a non-trivial portion of the electorate would support a wealth tax levied on individuals with assets over a certain dollar threshold. However, extrapolation from that self-reported support generally rests on the assumption that citizens and business leaders are able to appropriately anchor the costs and benefits of a wealth tax, for which they do not have a comparable tax experience. The support for these measures therefore rests less on a concrete understanding of their incidence than on the perception that a wealth tax set at a seemingly low rate would impose minimal distortions, particularly when targeted at the wealthiest households. This disconnect between the political appeal of wealth taxes and the absence of a meaningful benchmark underscores the necessity of a framework that quantifies their true economic tradeoffs in a way that is relatable and tangible to a larger portion of citizens and policymakers.</p>

<p>This calculator provides that framework. For those interested in the theoretical foundation and detailed analysis behind these calculations, please refer to the accompanying academic paper (citation to paper).</p>

<h3 style="text-align: center;">Purpose</h3>

<p>This calculator quantifies the equivalent capital income tax rate (t*) of a wealth tax. It addresses the question: <em>What rate of income taxation on capital yields the same economic outcome as living under a wealth tax?</em></p>

<img src="{{ site.baseurl }}/assets/tstarformula.jpg" alt="t-star Formula" style="max-width: 100%; height: auto; display: block; margin: 0 auto;">

<h3 style="text-align: center;">Adjusting for State and Federal Capital Gains Taxes</h3>

<p>The calculator also allows for the application of capital gains rates by state and the federal tax on capital gains. It addresses: <em>What rate of income taxation on capital yields the same economic outcome as living under a wealth tax, when adjusting for the state those gains are realized in?</em></p>

<p><em>Note: Capital gains consists of the top capital gains rate per selected state plus the top federal capital gains rate of 20% plus the Net Investment Income Tax (NIIT) of 3.8% applied on all investment income exceeding $250,000 for taxpayers married filing jointly ($125,000 filing separately).</em></p>

<h3 style="text-align: center;">Required Returns</h3>

<p>Beyond calculating the equivalent capital income tax rate, the calculator also determines the required pre-tax return on assets (ρ) that investors would demand to compensate for the expropriation risk created by a wealth tax combined with the existing federal and state capital gains tax rates. This metric is critical for communicating investment tradeoffs to owners of capital in the adopting jurisdiction. The required return calculations support economic theory and historical experience that substantial industry outmigration becomes likely, as investors seek jurisdictions where their capital can earn competitive after-tax returns without the recurring burden of wealth confiscation.</p>

<h2 style="text-align: center;">Real-Life Wealth Taxes and Proposals</h2>

<p>Actual wealth taxes and proposals you can test in the calculator above:</p>

<div class="wtc-table-scroll">
<table>
    <tr>
        <th>Wealth tax</th>
        <th>Top wealth tax rate (θ)</th>
    </tr>
    <tr>
        <td>Norway's "Formuesskatt"</td>
        <td>1.1%</td>
    </tr>
    <tr>
        <td>Colombia's "Impuesto al Patrimonio"</td>
        <td>1.5%</td>
    </tr>
    <tr>
        <td>Spain's "Impuesto sobre el Patrimonio"</td>
        <td>3.5%</td>
    </tr>
    <tr>
        <td>Switzerland</td>
        <td>*</td>
    </tr>
</table>
</div>
<p><em>Note: Switzerland levies wealth taxes at the canton and municipal levels.</em></p>

<div class="wtc-table-scroll">
<table>
    <tr>
        <th>Proposal</th>
        <th>Wealth tax rate (θ)</th>
    </tr>
    <tr>
        <td>State of Washington's proposed wealth tax</td>
        <td>1%</td>
    </tr>
    <tr>
        <td>France's proposed "Zucman Tax"</td>
        <td>2%</td>
    </tr>
    <tr>
        <td>California ballot initiative's one-time "2026 Billionaire Tax Act"</td>
        <td>5%</td>
    </tr>
    <tr>
        <td>Bernie Sanders' proposed wealth tax top bracket</td>
        <td>8%</td>
    </tr>
</table>
</div>

<h2 style="text-align: center;">Understanding the Calculations</h2>

<p>For those interested in the mathematical framework behind the calculator, this section explains the two key formulas used.</p>

<h3 style="text-align: center;">Equivalent Capital Income Tax Rate (t*)</h3>

<p>The first calculation determines what rate of capital income taxation produces the same economic outcome as a wealth tax. This equivalence is captured by the following formula:</p>

<img src="{{ site.baseurl }}/assets/tstarformula.jpg" alt="t-star Formula" style="max-width: 100%; height: auto; display: block; margin: 0 auto;">

<p>Where:</p>
<ul>
  <li><strong>t*</strong> = the equivalent capital income tax rate</li>
  <li><strong>θ</strong> (theta) = the wealth tax rate</li>
  <li><strong>r</strong> = the risk-free rate of return</li>
</ul>

<p>This formula shows that even a seemingly small wealth tax translates into a much larger effective tax on capital income. When combined with existing state and federal capital gains taxes, the total tax burden can approach or exceed revenue-maximizing levels.</p>

<h3 style="text-align: center;">Required Return Analysis (ρ)</h3>

<p>The second calculation determines the pre-tax return that investors must demand to compensate for the expropriation risk created by a wealth tax:</p>

<img src="{{ site.baseurl }}/assets/rhoformula.jpg" alt="Rho Formula" style="max-width: 100%; height: auto; display: block; margin: 0 auto;">

<p>Where:</p>
<ul>
  <li><strong>ρ</strong> (rho) = the required pre-tax rate of return</li>
  <li><strong>r</strong> = the risk-free rate of return</li>
  <li><strong>t</strong> = the combined capital income tax rate (t* plus existing capital gains taxes)</li>
</ul>

<p>This formula reveals how wealth taxes fundamentally alter investment incentives by requiring higher returns to compensate for the recurring claim on accumulated assets. The insecurity of property rights generated under a wealth tax regime can functionally deter internal and external direct investment. For example, California's proposed 5 percent wealth tax would require investors to demand a 48.1 percent pre-tax return—nine to ten times the risk-free rate—to compensate for expropriation risk. This exorbitant required return dwarfs the total market return on invested capital of 7.64 percent and exceeds the returns of 91 out of 94 publicly traded industry asset classes, serving as a substantial barrier to capital investment in the adopting jurisdiction.</p>

<p><em>For a complete theoretical derivation and policy analysis, please refer to the accompanying academic paper.</em></p>

<details class="wtc-sources">
<summary>Data sources: capital gains tax rates by jurisdiction</summary>

<p>The capital gains rates used in the calculator dropdown are sourced as follows.</p>

<div class="wtc-table-scroll">
<table>
    <tr>
        <th>State</th>
        <th>Top Capital Gains Rate</th>
        <th>Source</th>
    </tr>
    <tr>
        <td>Alabama</td>
        <td>5%</td>
        <td><a href="https://www.revenue.alabama.gov/tax-types/individual-income-tax/">Alabama Code §§ 40-18-1 et seq.</a></td>
    </tr>
    <tr>
        <td>Alaska</td>
        <td>0%</td>
        <td></td>
    </tr>
    <tr>
        <td>Arizona</td>
        <td>2.5%</td>
        <td><a href="https://www.azleg.gov/ars/43/01011.htm">Arizona Revised Statutes § 43-1011</a></td>
    </tr>
    <tr>
        <td>Arkansas</td>
        <td>3.9%</td>
        <td><a href="https://www.arkansasedc.com/why-arkansas/business-climate/tax-structure/personal-income-tax">Tax Foundation</a></td>
    </tr>
    <tr>
        <td>California</td>
        <td>13.3%</td>
        <td><a href="https://leginfo.legislature.ca.gov/faces/codes_displaySection.xhtml?sectionNum=17041.&lawCode=RTC">California Revenue and Taxation Code §§ 17041-17043</a></td>
    </tr>
    <tr>
        <td>Colorado</td>
        <td>4.4%</td>
        <td><a href="https://tax.colorado.gov/sites/tax/files/documents/Individual_Income_Tax_Guide_Mar_2024.pdf">C.R.S § 39-22-104</a></td>
    </tr>
    <tr>
        <td>Connecticut</td>
        <td>9.6%</td>
        <td><a href="https://search.cga.state.ct.us/r/statute/dtsearch.asp?cmd=getdoc&DocId=8109&Index=I%3a%5czindex%5csurs&HitCount=2&hits=cf+d0+&hc=18&req=%28number+contains+12%2D506%2A%29&Item=0">Conn. Gen. Stat. § 12-506</a></td>
    </tr>
    <tr>
        <td>Delaware</td>
        <td>6.6%</td>
        <td><a href="https://delcode.delaware.gov/title30/c011/sc01/index.html">Delaware Code § 1124</a></td>
    </tr>
    <tr>
        <td>Florida</td>
        <td>0%</td>
        <td></td>
    </tr>
    <tr>
        <td>Georgia</td>
        <td>5.39%</td>
        <td><a href="https://www.legis.ga.gov/api/document/docs/default-source/legislative-counsel-document-library/25sumdoc.pdf?sfvrsn=95973fc9_4">Georgia Code § 48‑7‑20</a></td>
    </tr>
    <tr>
        <td>Hawaii</td>
        <td>7.25%</td>
        <td><a href="https://files.hawaii.gov/tax/legal/hrs/hrs_235.pdf">Hawaii Revised Stat. § 235‑51(f)</a></td>
    </tr>
    <tr>
        <td>Idaho</td>
        <td>5.3%</td>
        <td><a href="https://legislature.idaho.gov/statutesrules/idstat/title63/t63ch30/sect63-3024/">Idaho Code § 63‑3024</a></td>
    </tr>
    <tr>
        <td>Illinois</td>
        <td>4.95%</td>
        <td><a href="https://www.ilga.gov/Documents/legislation/ilcs/documents/003500050K201.htm">35 ILCS 5/201</a></td>
    </tr>
    <tr>
        <td>Indiana</td>
        <td>3%</td>
        <td><a href="https://iga.in.gov/laws/2024/ic/titles/6#6-3-2.1">Indiana Code § 6‑3‑2‑1</a></td>
    </tr>
    <tr>
        <td>Iowa</td>
        <td>3.8%</td>
        <td><a href="https://www.legis.iowa.gov/docs/ico/chapter/422.pdf">Iowa Code § 422.5</a></td>
    </tr>
    <tr>
        <td>Kansas</td>
        <td>5.58%</td>
        <td><a href="https://www.kslegislature.gov/li_2024/b2023_24/statute/079_000_0000_chapter/079_032_0000_article/079_032_0110_section/079_032_0110_k/">K.S.A. 79‑32,110</a></td>
    </tr>
    <tr>
        <td>Kentucky</td>
        <td>4%</td>
        <td><a href="https://apps.legislature.ky.gov/law/statutes/statute.aspx?id=56339">Kentucky Revised Statutes § 141.020</a></td>
    </tr>
    <tr>
        <td>Louisiana</td>
        <td>4.25%</td>
        <td><a href="https://www.legis.la.gov/legis/Law.aspx?p=y&d=101946">Louisiana Revised Statutes § 47:32</a></td>
    </tr>
    <tr>
        <td>Maine</td>
        <td>7.15%</td>
        <td><a href="https://legislature.maine.gov/statutes/36/title36sec5111.html">36 M.R.S.A. § 5111</a></td>
    </tr>
    <tr>
        <td>Maryland</td>
        <td>5.75%</td>
        <td><a href="https://mgaleg.maryland.gov/mgawebsite/Laws/StatuteText?article=gtg&section=10-105&enactments=false">Maryland Code Tax‑Gen. § 10‑105</a></td>
    </tr>
    <tr>
        <td>Massachusetts</td>
        <td>16%</td>
        <td><a href="https://malegislature.gov/Laws/GeneralLaws/PartI/TitleIX/Chapter62/section4">Massachusetts General Laws c. 62 § 4</a></td>
    </tr>
    <tr>
        <td>Michigan</td>
        <td>4.25%</td>
        <td><a href="https://www.legislature.mi.gov/Laws/MCL?objectName=mcl-206-51#:~:text=206.51%20Tax%20rate%20on%20taxable,including%20items%20of%20income%20and">Michigan Compiled Laws § 206.51</a></td>
    </tr>
    <tr>
        <td>Minnesota</td>
        <td>9.85%</td>
        <td><a href="https://www.revisor.mn.gov/statutes/cite/290.06">Minnesota Statutes § 290.06</a></td>
    </tr>
    <tr>
        <td>Mississippi</td>
        <td>4.4%</td>
        <td><a href="https://advance.lexis.com/documentpage/?pdmfid=1000516&crid=b59466b9-22c5-461b-86ed-22e7f848bff8&nodeid=AAPAAFAABAAD&nodepath=%2FROOT%2FAAP%2FAAPAAFAAB%2FAAPAAFAABAAD&level=4&haschildren=&populated=false&title=%C2%A7+27-7-5.+Imposition+of+the+tax.&config=00JABhZDIzMTViZS04NjcxLTQ1MDItOTllOS03MDg0ZTQxYzU4ZTQKAFBvZENhdGFsb2f8inKxYiqNVSihJeNKRlUp&pddocfullpath=%2Fshared%2Fdocument%2Fstatutes-legislation%2Furn%3AcontentItem%3A6FG8-VHX3-SBN1-P36K-00008-00&ecomp=6gf5kkk&prid=ef6cdf66-5f51-4584-bf45-0c3b636c1a0a">Mississippi Code § 27‑7‑5</a></td>
    </tr>
    <tr>
        <td>Missouri</td>
        <td>4.95%</td>
        <td><a href="https://revisor.mo.gov/main/OneSection.aspx?section=143.011">Missouri Revised Statutes § 143.011</a></td>
    </tr>
    <tr>
        <td>Montana</td>
        <td>4.1%</td>
        <td><a href="https://archive.legmt.gov/bills/mca/title_0150/chapter_0300/part_0210/section_0030/0150-0300-0210-0030.html">Montana Code Annotated § 15‑30‑2103</a></td>
    </tr>
    <tr>
        <td>Nebraska</td>
        <td>5.2%</td>
        <td><a href="https://www.nebraskalegislature.gov/laws/statutes.php?statute=77-2715.03">Nebraska Revised Statute § 77‑2715.03</a></td>
    </tr>
    <tr>
        <td>Nevada</td>
        <td>0%</td>
        <td></td>
    </tr>
    <tr>
        <td>New Hampshire</td>
        <td>0%</td>
        <td></td>
    </tr>
    <tr>
        <td>New Jersey</td>
        <td>10.75%</td>
        <td><a href="https://lis.njleg.state.nj.us/nxt/gateway.dll/statutes/1/53131/53135?f=templates$fn=document-frameset.htm$q=%5Brank,100%3A%5Bdomain%3A%5Band%3A54A%3A2-1%20Imposition%20of%20tax.%5D%5D%20%5Bsum%3A54A%3A2-1%20Imposition%20of%20tax.%5D%20%5D%20$x=server$3.0#LPHit1">N.J. Stat. § 54A:2‑1</a></td>
    </tr>
    <tr>
        <td>New Mexico</td>
        <td>5.9%</td>
        <td><a href="https://klvg4oyd4j.execute-api.us-west-2.amazonaws.com/prod/PublicFiles/34821a9573ca43e7b06dfad20f5183fd/fd8f3075-42e7-4cdd-88db-7cab84ef72de/PIT%20rates_2005_2025.pdf">N.M. Stat. Ann. § 7-2-7</a></td>
    </tr>
    <tr>
        <td>New York</td>
        <td>10.9%</td>
        <td><a href="https://www.nysenate.gov/legislation/laws/TAX/601">New York Tax Law § 601</a></td>
    </tr>
    <tr>
        <td>North Carolina</td>
        <td>4.5%</td>
        <td><a href=" https://www.ncleg.net/EnactedLegislation/Statutes/PDF/BySection/Chapter_105/GS_105-153.7.pdf">N.C. Gen. Stat. § 105‑153.7</a></td>
    </tr>
    <tr>
        <td>North Dakota</td>
        <td>2.5%</td>
        <td><a href="https://ndlegis.gov/cencode/t57c38.pdf">North Dakota Century Code § 57-38-30.3</a></td>
    </tr>
    <tr>
        <td>Ohio</td>
        <td>3.5%</td>
        <td><a href="https://codes.ohio.gov/ohio-revised-code/section-5747.02">Ohio Revised Code § 5747.02</a></td>
    </tr>
    <tr>
        <td>Oklahoma</td>
        <td>4.75%</td>
        <td><a href=" https://oksenate.gov/sites/default/files/2019-12/os68.pdf">Oklahoma Statutes § 68-2355</a></td>
    </tr>
    <tr>
        <td>Oregon</td>
        <td>9.9%</td>
        <td><a href="https://www.oregonlegislature.gov/bills_laws/ors/ors316.html">Oregon Revised Statutes § 316.037</a></td>
    </tr>
    <tr>
        <td>Pennsylvania</td>
        <td>3.07%</td>
        <td><a href="https://www.pa.gov/agencies/revenue/resources/tax-types-and-information/personal-income-tax">72 P.S. § 7302 (a)</a></td>
    </tr>
    <tr>
        <td>Rhode Island</td>
        <td>5.99%</td>
        <td><a href="https://tax.ri.gov/sites/g/files/xkgbur541/files/2024-10/ADV_2024_26_Inflation_Adjustments.pdf">Rhode Island General Laws § 44-30-2.6</a></td>
    </tr>
    <tr>
        <td>South Carolina</td>
        <td>3.58%</td>
        <td><a href="https://www.scstatehouse.gov/code/t12c006.php">South Carolina Code § 12‑6‑510</a></td>
    </tr>
    <tr>
        <td>South Dakota</td>
        <td>0%</td>
        <td></td>
    </tr>
    <tr>
        <td>Tennessee</td>
        <td>0%</td>
        <td></td>
    </tr>
    <tr>
        <td>Texas</td>
        <td>0%</td>
        <td></td>
    </tr>
    <tr>
        <td>Utah</td>
        <td>4.55%</td>
        <td><a href="https://le.utah.gov/xcode/Title59/Chapter10/59-10-S104.html">Utah Code § 59-10-104</a></td>
    </tr>
    <tr>
        <td>Vermont</td>
        <td>8.75%</td>
        <td><a href="https://legislature.vermont.gov/statutes/section/32/151/05822">32 V.S.A. § 5822</a></td>
    </tr>
    <tr>
        <td>Virginia</td>
        <td>5.75%</td>
        <td><a href="https://law.lis.virginia.gov/vacode/title58.1/chapter3/section58.1-320/#:~:text=Imposition%20of%20tax.&text=31%2C%201989%3B%20and-,Five%20and%20three%2Dquarters%20percent%20on%20income%20in%20excess%20of,%2D151.011%3B%201971%2C%20Ex.">Code of Virginia § 58.1-320</a></td>
    </tr>
    <tr>
        <td>Washington D.C.</td>
        <td>9%</td>
        <td><a href="https://code.dccouncil.gov/us/dc/council/code/sections/47-1806.03">D.C. Code § 47‑1806.03</a></td>
    </tr>
    <tr>
        <td>Washington</td>
        <td>9.9%</td>
        <td><a href="https://app.leg.wa.gov/RCW/default.aspx?cite=82.87.040">RCW 82.87.040</a></td>
    </tr>
    <tr>
        <td>West Virginia</td>
        <td>5.12%</td>
        <td><a href="https://code.wvlegislature.gov/11-21-4I/">West Virginia Code § 11‑21‑4i</a></td>
    </tr>
    <tr>
        <td>Wisconsin</td>
        <td>7.65%</td>
        <td><a href="https://docs.legis.wisconsin.gov/statutes/statutes/71/iv/27">Wis. Stat. § 71.01</a></td>
    </tr>
    <tr>
        <td>Wyoming</td>
        <td>0%</td>
        <td></td>
    </tr>
</table>
</div>

<div class="wtc-table-scroll">
<table>
    <tr>
        <th>City</th>
        <th>Top Capital Gains Rate</th>
        <th>Source</th>
    </tr>
    <tr>
        <td>New York City</td>
        <td>3.4%</td>
        <td><a href="https://www.nysenate.gov/legislation/laws/TAX/1304">N.Y. Tax Law § 1304</a></td>
    </tr>
    <tr>
        <td>Portland, Oregon</td>
        <td>4.0%</td>
        <td><a href="https://www.oregonmetro.gov/sites/default/files/2025/10/16/Metro-Code-complete-effective-20250924.pdf">Metro Code § 7.06.040</a>; <a href="https://multco.us/file/preschool_for_all_personal_income_tax_code/download">Multnomah County Code § 11.512</a></td>
    </tr>
</table>
</div>

<div class="wtc-table-scroll">
<table>
    <tr>
        <th>International</th>
        <th>Capital Gains</th>
        <th>Source</th>
    </tr>
    <tr>
        <td>France — Financial Assets</td>
        <td>30%</td>
        <td><a href="https://www.service-public.gouv.fr/particuliers/vosdroits/F21618?lang=en">Service-Public.fr</a></td>
    </tr>
    <tr>
        <td>France — Real Estate (under 22 years)</td>
        <td>36.2%</td>
        <td><a href="https://www.service-public.gouv.fr/particuliers/vosdroits/F21618?lang=en">Service-Public.fr</a></td>
    </tr>
</table>
</div>

</details>

<p style="margin-top: 2rem; font-size: 0.9rem; color: #666;">The academic content, calculator methodology, and associated research are © 2025 William Dougan and Benjamin Jaros. For inquiries regarding the research or calculator, please contact: <a href="mailto:hooverfpi@stanford.edu">hooverfpi@stanford.edu</a>.</p>
