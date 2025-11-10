---
layout: page
title: Wealth Tax Calculator
permalink: /wealthtaxcalculator/
main_nav: true
---
<h2 style="text-align: center;">Purpose</h2>
This calculator quantifies the equivalent capital income tax rate (t*) of a wealth tax.
It addresses the question: What rate of income taxation on capital yields the same economic outcome as living under a wealth tax?
<img src="{{ site.baseurl }}/assets/tstarformula.jpg" alt="t-star Formula" style="width: 200%;">
<h2 style="text-align: center;">Try It</h2>
Input values for:
<p><strong>Expropriation Risk - Wealth Tax Rate (θ):</strong> A wealth tax of 1% should be entered as 1. Acceptable range of values is between 0 and 100 (0-100%).</p>
<p><strong>Risk Free Rate (r):</strong> This reflects the return to capital in the economy. For reference, the risk free rate of return seldom exceeds 5 (e.g., yield of 30-year U.S. Treasury bond). Returns vary more widely among sectors. A Risk Free Rate of 5% should be entered as 5. Acceptable range of values is between -100 and 100 (-100%-100%). </p>
<p>*Note: Output exceeding 100% is impossible given Calculator constraints.</p>

Or try a real-life proposal:
<table>
    <tr>
        <th>Example</th>
        <th>Wealth Tax Rate (θ)</th>
    </tr>
    <tr>
        <th>State of Washington's Proposed Wealth Tax</th>
        <th>1%</th>
    </tr>
    <tr>
        <th>France's Proposed "Zucman Tax"</th>
        <th>2%</th>
    </tr>
    <tr>
        <th>California Ballot Initiative, "2026 Billionare Tax Act"</th>
        <th>5%</th>
    </tr>
    <tr>
        <th>Bernie Sander's Proposed Wealth Tax Top Bracket</th>
        <th>8%</th>
    </tr>
</table>

<p> This calculator also allows for the application of capital gains rates by state and the Federal tax on capital gains.
It addresses the question: What rate of income taxation on capital yields the same economic outcome as living under a wealth tax, when adjusting for the state I pay taxes in?</p>
<p>*Note: Capital gains in this calculator consists of the top capital gains rate per selected state plus the top federal capital gains rate of 20% plus the Net Investment Income Tax (NIIT) of 3.8% applied on all investment income exceeding $250,000 for taxpayers married filing jointly ($125,000 filing separately).</p>
<hr style="margin: 40px 0; border: 1px solid #ddd;">

<div style="max-width: 600px; margin: 0 auto; padding: 20px;">
  <h2 style="text-align: center;">Input Your Parameters Below</h2>
  
  <div style="margin: 20px 0;">
    <label for="state" style="display: block; margin-bottom: 5px;">
      <strong>Select State:</strong>
    </label>
    <select id="state" style="width: 100%; padding: 8px; font-size: 16px;">
      <option value="0.2">United States (Federal Only)</option>
      <option value="0.491">National Average</option>
      <option value="0.288">Alabama</option>
      <option value="0.238">Alaska</option>
      <option value="0.25675">Arizona</option>
      <option value="0.26">Arkansas</option>
      <option value="0.371">California</option>
      <option value="0.282">Colorado</option>
      <option value="0.2855">Connecticut</option>
      <option value="0.304">Delaware</option>
      <option value="0.238">Florida</option>
      <option value="0.2929">Georgia</option>
      <option value="0.3105">Hawaii</option>
      <option value="0.296">Idaho</option>
      <option value="0.2875">Illinois</option>
      <option value="0.2685">Indiana</option>
      <option value="0.295">Iowa</option>
      <option value="0.295">Kansas</option>
      <option value="0.278">Kentucky</option>
      <option value="0.2805">Louisiana</option>
      <option value="0.3095">Maine</option>
      <option value="0.2955">Maryland</option>
      <option value="0.328">Massachusetts</option>
      <option value="0.2805">Michigan</option>
      <option value="0.3465">Minnesota</option>
      <option value="0.285">Mississippi</option>
      <option value="0.286">Missouri</option>
      <option value="0.279">Montana</option>
      <option value="0.2964">Nebraska</option>
      <option value="0.238">Nevada</option>
      <option value="0.238">New Hampshire</option>
      <option value="0.3455">New Jersey</option>
      <option value="0.2734">New Mexico</option>
      <option value="0.347">New York</option>
      <option value="0.283">North Carolina</option>
      <option value="0.253">North Dakota</option>
      <option value="0.273">Ohio</option>
      <option value="0.2855">Oklahoma</option>
      <option value="0.337">Oregon</option>
      <option value="0.2687">Pennsylvania</option>
      <option value="0.2979">Rhode Island</option>
      <option value="0.2772">South Carolina</option>
      <option value="0.238">South Dakota</option>
      <option value="0.238">Tennessee</option>
      <option value="0.238">Texas</option>
      <option value="0.2835">Utah</option>
      <option value="0.3255">Vermont</option>
      <option value="0.2955">Virginia</option>
      <option value="0.3455">Washington D.C.</option>
      <option value="0.308">Washington State</option>
      <option value="0.2892">West Virginia</option>
      <option value="0.29155">Wisconsin</option>
      <option value="0.238">Wyoming</option>      
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
           style="width: 100%; padding: 8px; font-size: 16px;" oninput="document.getElementById('r2').value = this.value;">
  </div>

  <button onclick="calculateWithCapGains()" 
          style="width: 100%; padding: 12px; font-size: 18px; background-color: #0DAC50; color: white; border: none; cursor: pointer; margin: 20px 0;">
    Calculate
  </button>

  <div id="error1" style="margin-top: 20px; padding: 20px; background-color: #ffcccc; border-radius: 5px; display: none; color: #cc0000;">
    <strong>Unacceptable values entered.</strong>
  </div>

  <div id="result1" style="margin-top: 20px; padding: 20px; background-color: #f0f0f0; border-radius: 5px; display: none;">
    <h3 style="margin-top: 0;">Result:</h3>
    <p id="resultText1" style="font-size: 18px;"></p>
  </div>
</div>

<script>
function calculateWithCapGains() {
  // Get input values and convert percentages to decimals
  var theta = parseFloat(document.getElementById('theta1').value) / 100;
  var r = parseFloat(document.getElementById('r1').value) / 100;
  var capGainsRate = parseFloat(document.getElementById('state').value);
  
  // Hide previous messages
  document.getElementById('error1').style.display = 'none';
  document.getElementById('result1').style.display = 'none';
  
  // Validate inputs
  if (isNaN(theta) || isNaN(r) || theta < 0 || theta > 1 || r < -1 || r > 1) {
    document.getElementById('error1').style.display = 'block';
    return;
  }
  
  // Calculate equivalent tax rate
  var t = (1 - ((r * (1 - theta)) / (r + theta))) * 100;
  
  // Add capital gains tax rate (convert to percentage)
  var tWithCapGains = t + (capGainsRate * 100);
  
  // Round to 3 decimal places
  t = Math.round(t * 1000) / 1000;
  tWithCapGains = Math.round(tWithCapGains * 1000) / 1000;
  
  // Display result
  document.getElementById('resultText1').innerHTML = 
    "Base equivalent capital income tax rate: <strong>" + t + "%</strong><br>" +
    "With capital gains tax: <strong>" + tWithCapGains + "%</strong>";
  document.getElementById('result1').style.display = 'block';
}
</script>



<h2 style="text-align: center;">Required Return Analysis</h2>
<p>Having established the equivalence between taxation and expropriation (t), the required rate of return (ρ) investors must demand to compensate for expropriation risk can be derived.</p>
<img src="{{ site.baseurl }}/assets/rhoformula.jpg" alt="Rho Formula" style="width: 200%;">

<hr style="margin: 40px 0; border: 1px solid #ddd;">

<div style="max-width: 600px; margin: 0 auto; padding: 20px;">
  <h2 style="text-align: center;">Rho (&rho;) Calculator</h2>
  
  <div style="margin: 20px 0;">
    <label for="r2" style="display: block; margin-bottom: 5px;">
      <strong>Risk Free Rate (r) in %:</strong>
    </label>
    <input type="number" id="r2" step="0.001" value="" min="-100" max="100"
           style="width: 100%; padding: 8px; font-size: 16px;">
  </div>

  <div style="margin: 20px 0;">
    <label for="t2" style="display: block; margin-bottom: 5px;">
      <strong>Equivalent Capital Income Tax Rate (t) in %:</strong>
    </label>
    <input type="number" id="t2" step="0.001" value=""
           style="width: 100%; padding: 8px; font-size: 16px;">
  </div>

  <button onclick="calculateRho()" 
          style="width: 100%; padding: 12px; font-size: 18px; background-color: #0DAC50; color: white; border: none; cursor: pointer; margin: 20px 0;">
    Calculate
  </button>

  <div id="error2" style="margin-top: 20px; padding: 20px; background-color: #ffcccc; border-radius: 5px; display: none; color: #cc0000;">
    <strong>Unacceptable values entered.</strong>
  </div>

  <div id="result2" style="margin-top: 20px; padding: 20px; background-color: #f0f0f0; border-radius: 5px; display: none;">
    <h3 style="margin-top: 0;">Result:</h3>
    <p id="resultText2" style="font-size: 18px;"></p>
  </div>
</div>

<script>
function calculateRho() {
  // Get input values and convert percentages to decimals
  var r = parseFloat(document.getElementById('r2').value) / 100;
  var t = parseFloat(document.getElementById('t2').value) / 100;
  
  // Hide previous messages
  document.getElementById('error2').style.display = 'none';
  document.getElementById('result2').style.display = 'none';
  
  // Validate inputs
  if (isNaN(r) || isNaN(t) || r < -1 || r > 1) {
    document.getElementById('error2').style.display = 'block';
    return;
  }
  
  // Check for division by zero
  if (t === 1) {
    document.getElementById('error2').style.display = 'block';
    document.getElementById('error2').innerHTML = '<strong>Error: t cannot equal 100% (division by zero).</strong>';
    return;
  }
  
  // Calculate rho
  var rho = r / (1 - t);
  
  // Round to 3 decimal places
  rho = Math.round(rho * 1000) / 1000;
  
  // Display result (convert back to percentage for display)
  document.getElementById('resultText2').innerHTML = 
    "A required pre-tax return on assets of <strong>" + (rho * 100) + "%</strong> is needed to compensate for the expropriation risk.";
  document.getElementById('result2').style.display = 'block';
}
</script>


<table>
    <tr>
        <th>State</th>
        <th>Top Capital Gains Rate</th>
        <th>Source</th>
    </tr>
    <tr>
        <td>Alabama</td>
        <td>5%</td>
        <td></td>
    </tr>
    <tr>
        <td>Alaska</td>
        <td>0%</td>
        <td></td>
    </tr>
    <tr>
        <td>Arizona</td>
        <td>1.875%</td>
        <td></td>
    </tr>
    <tr>
        <td>Arkansas</td>
        <td>2.2%</td>
        <td></td>
    </tr>
    <tr>
        <td>California</td>
        <td>13.3%</td>
        <td></td>
    </tr>
    <tr>
        <td>Colorado</td>
        <td>4.4%</td>
        <td></td>
    </tr>
    <tr>
        <td>Connecticut</td>
        <td>4.75%</td>
        <td></td>
    </tr>
    <tr>
        <td>Delaware</td>
        <td>6.6%</td>
        <td></td>
    </tr>
    <tr>
        <td>Florida</td>
        <td>0%</td>
        <td></td>
    </tr>
    <tr>
        <td>Georgia</td>
        <td>5.49%</td>
        <td></td>
    </tr>
    <tr>
        <td>Hawaii</td>
        <td>7.25%</td>
        <td></td>
    </tr>
    <tr>
        <td>Idaho</td>
        <td>5.8%</td>
        <td></td>
    </tr>
    <tr>
        <td>Illinois</td>
        <td>4.95%</td>
        <td></td>
    </tr>
    <tr>
        <td>Indiana</td>
        <td>3.05%</td>
        <td></td>
    </tr>
    <tr>
        <td>Iowa</td>
        <td>5.7%</td>
        <td></td>
    </tr>
    <tr>
        <td>Kansas</td>
        <td>5.7%</td>
        <td></td>
    </tr>
    <tr>
        <td>Kentucky</td>
        <td>4%</td>
        <td></td>
    </tr>
    <tr>
        <td>Louisiana</td>
        <td>4.25%</td>
        <td></td>
    </tr>
    <tr>
        <td>Maine</td>
        <td>7.15%</td>
        <td></td>
    </tr>
    <tr>
        <td>Maryland</td>
        <td>5.75%</td>
        <td></td>
    </tr>
    <tr>
        <td>Massachusetts</td>
        <td>9%</td>
        <td></td>
    </tr>
    <tr>
        <td>Michigan</td>
        <td>4.25%</td>
        <td></td>
    </tr>
    <tr>
        <td>Minnesota</td>
        <td>10.85%</td>
        <td></td>
    </tr>
    <tr>
        <td>Mississippi</td>
        <td>4.7%</td>
        <td></td>
    </tr>
    <tr>
        <td>Missouri</td>
        <td>4.8%</td>
        <td></td>
    </tr>
    <tr>
        <td>Montana</td>
        <td>4.1%</td>
        <td></td>
    </tr>
    <tr>
        <td>Nebraska</td>
        <td>5.84%</td>
        <td></td>
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
        <td></td>
    </tr>
    <tr>
        <td>New Mexico</td>
        <td>3.54%</td>
        <td></td>
    </tr>
    <tr>
        <td>New York</td>
        <td>10.9%</td>
        <td></td>
    </tr>
    <tr>
        <td>North Carolina</td>
        <td>4.5%</td>
        <td></td>
    </tr>
    <tr>
        <td>North Dakota</td>
        <td>1.5%</td>
        <td></td>
    </tr>
    <tr>
        <td>Ohio</td>
        <td>3.5%</td>
        <td></td>
    </tr>
    <tr>
        <td>Oklahoma</td>
        <td>4.75%</td>
        <td></td>
    </tr>
    <tr>
        <td>Oregon</td>
        <td>9.9%</td>
        <td></td>
    </tr>
    <tr>
        <td>Pennsylvania</td>
        <td>3.07%</td>
        <td></td>
    </tr>
    <tr>
        <td>Rhode Island</td>
        <td>5.99%</td>
        <td></td>
    </tr>
    <tr>
        <td>South Carolina</td>
        <td>3.92%</td>
        <td></td>
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
        <td></td>
    </tr>
    <tr>
        <td>Vermont</td>
        <td>8.75%</td>
        <td></td>
    </tr>
    <tr>
        <td>Virginia</td>
        <td>5.75%</td>
        <td></td>
    </tr>
    <tr>
        <td>Washington D.C.</td>
        <td>10.75%</td>
        <td></td>
    </tr>
    <tr>
        <td>Washington</td>
        <td>7%</td>
        <td></td>
    </tr>
    <tr>
        <td>West Virginia</td>
        <td>5.12%</td>
        <td></td>
    </tr>
    <tr>
        <td>Wisconsin</td>
        <td>5.355%</td>
        <td></td>
    </tr>
    <tr>
        <td>Wyoming</td>
        <td>0%</td>
        <td></td>
    </tr>
</table>