---
layout: page
title: Wealth Tax Calculator
permalink: /wealthtaxcalculator/
main_nav: true
---
<h2 style="text-align: center;">Introduction</h2>

<p>The recent interest in wealth taxes highlights the importance of clarifying their tradeoffs, since the absence of a familiar benchmark leads to misanchored judgments about their costs and benefits. The apparent simplicity of taxing accumulated assets conceals the effects these policies impose on economic behavior and property rights, ultimately trading short-term fiscal gains for long-term economic costs. For example, the "Zucman Tax," a 2 percent wealth tax in France and Washington state's recently proposed 1 percent wealth tax in the United States have gained traction by appealing to fairness and these taxes as a source of redistributive public sector revenue.</p>

<p>Surveys suggest that a non-trivial portion of the electorate would support a wealth tax levied on individuals with assets over a certain dollar threshold. However, extrapolation from that self-reported support generally rests on the assumption that citizens and business leaders are able to appropriately anchor the costs and benefits of a wealth tax, for which they do not have a comparable tax experience. The support for these measures therefore rests less on a concrete understanding of their incidence than on the perception that a wealth tax set at a seemingly low rate would impose minimal distortions, particularly when targeted at the wealthiest households. This disconnect between the political appeal of wealth taxes and the absence of a meaningful benchmark underscores the necessity of a framework that quantifies their true economic tradeoffs in a way that is relatable and tangible to a larger portion of citizens and policymakers.</p>

This calculator provides that framework. For those interested in the theoretical foundation and detailed analysis behind these calculations, please refer to the accompanying academic paper (citation to paper). For everyone else, the calculator below makes the economic tradeoffs of wealth taxation transparent and tangible.

<h2 style="text-align: center;">Purpose</h2>

This calculator quantifies the equivalent capital income tax rate (t*) of a wealth tax. It addresses the question: What rate of income taxation on capital yields the same economic outcome as living under a wealth tax?

<img src="{{ site.baseurl }}/assets/tstarformula.jpg" alt="t-star Formula" style="width: 200%;">

<h2 style="text-align: center;">Real-Life Proposals</h2>

To see how this works in practice, here are actual wealth tax proposals you can test in the calculator:

<table>
    <tr>
        <th>Proposal</th>
        <th>Wealth Tax Rate (θ)</th>
    </tr>
    <tr>
        <td>State of Washington's Proposed Wealth Tax</td>
        <td>1%</td>
    </tr>
    <tr>
        <td>France's Proposed "Zucman Tax"</td>
        <td>2%</td>
    </tr>
    <tr>
        <td>California Ballot Initiative, "2026 Billionaire Tax Act"</td>
        <td>5%</td>
    </tr>
    <tr>
        <td>Bernie Sanders' Proposed Wealth Tax Top Bracket</td>
        <td>8%</td>
    </tr>
</table>

<h2 style="text-align: center;">How to Use the Calculator</h2>

Input values for the following parameters:

<p><strong>Expropriation Risk - Wealth Tax Rate (θ):</strong> A wealth tax of 1% should be entered as 1. Acceptable range of values is between 0 and 100 (0-100%).</p>

<p><strong>Risk Free Rate (r):</strong> This reflects the return to capital in the economy. For reference, the risk-free rate of return seldom exceeds 5 (e.g., yield of 30-year U.S. Treasury bond). Returns vary more widely among sectors. A risk-free rate of 5% should be entered as 5. Acceptable range of values is between -100 and 100 (-100% to 100%).</p>

<h3 style="text-align: center;">Adjusting for State and Federal Capital Gains Taxes</h3>

<p>This calculator also allows for the application of capital gains rates by state and the federal tax on capital gains. It addresses the question: What rate of income taxation on capital yields the same economic outcome as living under a wealth tax, when adjusting for the state those gains are realized in?</p>

<p><em>Note: Capital gains consists of the top capital gains rate per selected state plus the top federal capital gains rate of 20% plus the Net Investment Income Tax (NIIT) of 3.8% applied on all investment income exceeding $250,000 for taxpayers married filing jointly ($125,000 filing separately).</em></p>





<h2 style="text-align: center;">Understanding Required Returns</h2>

<p>Beyond calculating the equivalent capital income tax rate, this calculator also determines the required pre-tax return on assets (ρ) that investors would demand to compensate for the expropriation risk created by a wealth tax combined with the existing federal and state capital gains tax rates. This metric is critical for communicating investment tradeoffs to owners of capital in the adopting jurisdiction. The required return calculations are meant to support economic theory and historical experience that substantial industry outmigration becomes likely, as investors seek jurisdictions where their capital can earn competitive after-tax returns without the recurring burden of wealth confiscation.</p>

<hr style="margin: 40px 0; border: 1px solid #ddd;">

<div style="max-width: 600px; margin: 0 auto; padding: 20px;">
  <h2 style="text-align: center;">Input Your Parameters Below</h2>
  
  <div style="margin: 20px 0;">
    <label for="state" style="display: block; margin-bottom: 5px;">
      <strong>Select State:</strong>
    </label>
    <select id="state" style="width: 100%; padding: 8px; font-size: 16px;">
      <option value="0">United States (Federal Only)</option>
      <option value="0.0486">National Average</option>
      <option value="0.05">Alabama</option>
      <option value="0">Alaska</option>
      <option value="0.025">Arizona</option>
      <option value="0.039">Arkansas</option>
      <option value="0.133">California</option>
      <option value="0.044">Colorado</option>
      <option value="0.0699">Connecticut</option>
      <option value="0.066">Delaware</option>
      <option value="0">Florida</option>
      <option value="0.0539">Georgia</option>
      <option value="0.0725">Hawaii</option>
      <option value="0.0569">Idaho</option>
      <option value="0.0495">Illinois</option>
      <option value="0.03">Indiana</option>
      <option value="0.038">Iowa</option>
      <option value="0.0558">Kansas</option>
      <option value="0.04">Kentucky</option>
      <option value="0.03">Louisiana</option>
      <option value="0.0715">Maine</option>
      <option value="0.0575">Maryland</option>
      <option value="0.09">Massachusetts</option>
      <option value="0.0425">Michigan</option>
      <option value="0.0985">Minnesota</option>
      <option value="0.044">Mississippi</option>
      <option value="0.047">Missouri</option>
      <option value="0.059">Montana</option>
      <option value="0.052">Nebraska</option>
      <option value="0">Nevada</option>
      <option value="0">New Hampshire</option>
      <option value="0.1075">New Jersey</option>
      <option value="0.059">New Mexico</option>
      <option value="0.109">New York</option>
      <option value="0.0425">North Carolina</option>
      <option value="0.025">North Dakota</option>
      <option value="0.035">Ohio</option>
      <option value="0.0475">Oklahoma</option>
      <option value="0.099">Oregon</option>
      <option value="0.0307">Pennsylvania</option>
      <option value="0.0599">Rhode Island</option>
      <option value="0.062">South Carolina</option>
      <option value="0">South Dakota</option>
      <option value="0">Tennessee</option>
      <option value="0">Texas</option>
      <option value="0.0455">Utah</option>
      <option value="0.0875">Vermont</option>
      <option value="0.0575">Virginia</option>
      <option value="0.1075">Washington D.C.</option>
      <option value="0.07">Washington State</option>
      <option value="0.0482">West Virginia</option>
      <option value="0.0765">Wisconsin</option>
      <option value="0">Wyoming</option>
      <option value="0.3">France - Financial Assets</option>
      <option value="0.362">France - Real Estate (under 22 years)</option>   
    </select>
  </div>

  <div style="margin: 20px 0;">
    <label for="theta1" style="display: block; margin-bottom: 5px;">
      <strong>Expropriation Risk - Wealth Tax Rate (θ) in %:</strong>
    </label>
    <input type="number" id="theta1" step="0.001" value="" min="0" max="100"
           style="width: 100%; padding: 8px; font-size: 16px;">
  </div>

  <div style="margin: 20px 0;">
    <label for="r1" style="display: block; margin-bottom: 5px;">
      <strong>Risk Free Rate (r) in %:</strong>
    </label>
    <input type="number" id="r1" step="0.001" value="" min="-100" max="100"
           style="width: 100%; padding: 8px; font-size: 16px;">
  </div>

  <button onclick="calculateAll()" 
          style="width: 100%; padding: 12px; font-size: 18px; background-color: #0DAC50; color: white; border: none; cursor: pointer; margin: 20px 0;">
    Calculate
  </button>

  <div id="error1" style="margin-top: 20px; padding: 20px; background-color: #ffcccc; border-radius: 5px; display: none; color: #cc0000;">
    <strong>Unacceptable values entered.</strong>
  </div>

  <div id="result1" style="margin-top: 20px; padding: 20px; background-color: #f0f0f0; border-radius: 5px; display: none;">
    <h3 style="margin-top: 0;">Results:</h3>
    <p id="resultText1" style="font-size: 18px;"></p>
  </div>
</div>

<script>
function calculateAll() {
  // Get input values and convert percentages to decimals
  var theta = parseFloat(document.getElementById('theta1').value) / 100;
  var r = parseFloat(document.getElementById('r1').value) / 100;
  var stateCapGainsRate = parseFloat(document.getElementById('state').value);
  
  // Get selected state name
  var stateSelect = document.getElementById('state');
  var selectedStateName = stateSelect.options[stateSelect.selectedIndex].text;
  
  // Check if France is selected
  var isFrance = selectedStateName.indexOf("France") !== -1;
  
  // Federal capital gains and NIIT (constants) - only for US
  var federalCapGains = isFrance ? 0 : 0.20;
  var niit = isFrance ? 0 : 0.038;
  
  // Hide previous messages
  document.getElementById('error1').style.display = 'none';
  document.getElementById('result1').style.display = 'none';
  
  // Validate inputs
  if (isNaN(theta) || isNaN(r) || theta < 0 || theta > 1 || r < -1 || r > 1) {
    document.getElementById('error1').style.display = 'block';
    return;
  }
  
  // Calculate base equivalent tax rate
  var tBase = (1 - ((r * (1 - theta)) / (r + theta))) * 100;
  
  // Calculate combined tax (base + state + federal + NIIT, all in percentage)
  var combinedTax = tBase + (stateCapGainsRate * 100) + (federalCapGains * 100) + (niit * 100);
  
  // Calculate rho using the combined tax rate
  var tCombinedDecimal = combinedTax / 100;
  
  // Check for division by zero
  if (tCombinedDecimal >= 1) {
    document.getElementById('error1').style.display = 'block';
    document.getElementById('error1').innerHTML = '<strong>Error: Combined tax rate equals or exceeds 100% (calculation not possible).</strong>';
    return;
  }
  
  var rho = r / (1 - tCombinedDecimal);
  
  // Round to 3 decimal places
  tBase = Math.round(tBase * 1000) / 1000;
  combinedTax = Math.round(combinedTax * 1000) / 1000;
  rho = Math.round((rho * 100) * 1000) / 1000;
  
  // Display results - different format for France
  var resultHTML = "<strong>Base Equivalent Capital Income Tax Rate:</strong> " + tBase + "%<br>";
  
  if (isFrance) {
    resultHTML += "<strong>France Capital Gains Tax Rate:</strong> " + Math.round((stateCapGainsRate * 100) * 100) / 100 + "%<br>";
    resultHTML += "<strong>Comparable Combined Tax on Capital Income:</strong> " + combinedTax + "%<br><br>";
  } else {
    resultHTML += "<strong>Top State Capital Gains Tax Rate:</strong> " + Math.round((stateCapGainsRate * 100) * 100) / 100 + "%<br>";
    resultHTML += "<strong>Top Federal Capital Gains Tax Rate:</strong> 20%<br>";
    resultHTML += "<strong>Net Investment Income Tax:</strong> 3.8%<br>";
    resultHTML += "<strong>Comparable Combined Tax on Capital Income:</strong> " + combinedTax + "%<br><br>";
  }
  
  resultHTML += "A required pre-tax return on assets of <strong>" + rho + "%</strong> is needed to compensate for the expropriation risk.";
  
  document.getElementById('resultText1').innerHTML = resultHTML;
  document.getElementById('result1').style.display = 'block';
}
</script>



<hr style="margin: 40px 0; border: 1px solid #ddd;">

<h2 style="text-align: center;">Understanding the Calculations</h2>

<p>For those interested in the mathematical framework behind the calculator, this section explains the two key formulas used.</p>

<h3 style="text-align: center;">Equivalent Capital Income Tax Rate (t*)</h3>

<p>The first calculation determines what rate of capital income taxation produces the same economic outcome as a wealth tax. This equivalence is captured by the following formula:</p>

<img src="{{ site.baseurl }}/assets/tstarformula.jpg" alt="t-star Formula" style="width: 200%; max-width: 600px; display: block; margin: 20px auto;">

<p>Where:</p>
<ul>
  <li><strong>t*</strong> = the equivalent capital income tax rate</li>
  <li><strong>θ</strong> (theta) = the wealth tax rate</li>
  <li><strong>r</strong> = the risk-free rate of return</li>
</ul>

<p>This formula shows that even a seemingly small wealth tax translates into a much larger effective tax on capital income. When combined with existing state and federal capital gains taxes, the total tax burden can approach or exceed revenue-maximizing levels.</p>

<h3 style="text-align: center;">Required Return Analysis (ρ)</h3>

<p>The second calculation determines the pre-tax return that investors must demand to compensate for the expropriation risk created by a wealth tax:</p>

<img src="{{ site.baseurl }}/assets/rhoformula.jpg" alt="Rho Formula" style="width: 200%; max-width: 600px; display: block; margin: 20px auto;">

<p>Where:</p>
<ul>
  <li><strong>ρ</strong> (rho) = the required pre-tax rate of return</li>
  <li><strong>r</strong> = the risk-free rate of return</li>
  <li><strong>t</strong> = the combined capital income tax rate (t* plus existing capital gains taxes)</li>
</ul>

<p>This formula reveals how wealth taxes fundamentally alter investment incentives by requiring higher returns to compensate for the recurring claim on accumulated assets. When combined tax rates approach 100%, the required return becomes impossibly high, effectively discouraging investment in that jurisdiction.</p>

<p><em>For a complete theoretical derivation and policy analysis, please refer to the accompanying academic paper.</em></p>

<table>
    <tr>
        <th>State</th>
        <th>Top Capital Gains Rate</th>
        <th>Source</th>
    </tr>
    <tr>
        <td>Alabama</td>
        <td>5%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Alaska</td>
        <td>0%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Arizona</td>
        <td>2.5%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Arkansas</td>
        <td>3.9%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>California</td>
        <td>13.3%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Colorado</td>
        <td>4.4%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Connecticut</td>
        <td>6.99%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Delaware</td>
        <td>6.6%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Florida</td>
        <td>0%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Georgia</td>
        <td>5.39%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Hawaii</td>
        <td>7.25%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Idaho</td>
        <td>5.69%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Illinois</td>
        <td>4.95%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Indiana</td>
        <td>3%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Iowa</td>
        <td>3.8%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Kansas</td>
        <td>5.58%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Kentucky</td>
        <td>4%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Louisiana</td>
        <td>3%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Maine</td>
        <td>7.15%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Maryland</td>
        <td>5.75%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Massachusetts</td>
        <td>9%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Michigan</td>
        <td>4.25%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Minnesota</td>
        <td>9.85%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Mississippi</td>
        <td>4.4%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Missouri</td>
        <td>4.7%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Montana</td>
        <td>5.9%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Nebraska</td>
        <td>5.2%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Nevada</td>
        <td>0%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>New Hampshire</td>
        <td>0%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>New Jersey</td>
        <td>10.75%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>New Mexico</td>
        <td>5.9%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>New York</td>
        <td>10.9%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>North Carolina</td>
        <td>4.25%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>North Dakota</td>
        <td>2.5%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Ohio</td>
        <td>3.5%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Oklahoma</td>
        <td>4.75%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Oregon</td>
        <td>9.9%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Pennsylvania</td>
        <td>3.07%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Rhode Island</td>
        <td>5.99%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>South Carolina</td>
        <td>6.2%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>South Dakota</td>
        <td>0%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Tennessee</td>
        <td>0%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Texas</td>
        <td>0%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Utah</td>
        <td>4.55%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Vermont</td>
        <td>8.75%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Virginia</td>
        <td>5.75%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Washington D.C.</td>
        <td>10.75%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Washington</td>
        <td>7%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>West Virginia</td>
        <td>4.82%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Wisconsin</td>
        <td>7.65%</td>
        <td>Tax Foundation</td>
    </tr>
    <tr>
        <td>Wyoming</td>
        <td>0%</td>
        <td>Tax Foundation</td>
    </tr>
</table>

The academic content, calculator methodology, and associated research are © 2025 William Dougan and Benjamin Jaros. For inquiries regarding the research or calculator, please contact: hooverfpi@stanford.edu.
