---
layout: page
title: Wealth Tax Calculator
permalink: /wealthtaxcalculator/
main_nav: true
---
<h2 style="text-align: center;">Purpose</h2>
This calculator quantifies the equivalent capital income tax rate (t*) of a wealth tax.
It addresses the question: What rate of income taxation on capital yields the same economic outcome as living under a wealth tax?
![alt text]({{ site.baseurl }}/assets/tstarformula.jpg "Profile Picture"){:.profile}
<h2 style="text-align: center;">Try It</h2>
Input values for:
<p><strong>Expropriation Risk - Wealth Tax Rate (θ):</strong> A wealth tax of 1% should be entered as 0.01. Acceptable range of values is between 0 and 1 (0-100%).</p>
<p><strong>Risk Free Rate (r):</strong> This reflects the return to capital in the economy. For reference, the risk free rate of return seldom exceeds 0.05 (e.g., yield of 30-year U.S. Treasury bond). Returns vary more widely among sectors. A Risk Free Rate of 5% should be entered as 0.05. Acceptable range of values is between -1 and 1 (-100%-100%). </p>
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

<div style="max-width: 600px; margin: 0 auto; padding: 20px;">
  <h2 style="text-align: center;">Input Parameters Below</h2>
  
  <div style="margin: 20px 0;">
    <label for="theta" style="display: block; margin-bottom: 5px;">
      <strong>Expropriation Risk - Wealth Tax Rate (θ):</strong>
    </label>
    <input type="number" id="theta" step="0.001" value="" min="0" max="1"
           style="width: 100%; padding: 8px; font-size: 16px;">
  </div>

  <div style="margin: 20px 0;">
    <label for="r" style="display: block; margin-bottom: 5px;">
      <strong>Risk Free Rate (r):</strong>
    </label>
    <input type="number" id="r" step="0.001" value="" min="-1" max="1"
           style="width: 100%; padding: 8px; font-size: 16px;">
  </div>

  <button onclick="calculate()" 
          style="width: 100%; padding: 12px; font-size: 18px; background-color: #0DAC50; color: white; border: none; cursor: pointer; margin: 20px 0;">
    Calculate
  </button>

  <div id="error" style="margin-top: 20px; padding: 20px; background-color: #ffcccc; border-radius: 5px; display: none; color: #cc0000;">
    <strong>Unacceptable values entered.</strong>
  </div>

  <div id="result" style="margin-top: 20px; padding: 20px; background-color: #f0f0f0; border-radius: 5px; display: none;">
    <h3 style="margin-top: 0;">Result:</h3>
    <p id="resultText" style="font-size: 18px;"></p>
  </div>
</div>

<script>
function calculate() {
  // Get input values
  var theta = parseFloat(document.getElementById('theta').value);
  var r = parseFloat(document.getElementById('r').value);
  
  // Hide previous messages
  document.getElementById('error').style.display = 'none';
  document.getElementById('result').style.display = 'none';
  
  // Validate inputs
  if (isNaN(theta) || isNaN(r) || theta < 0 || theta > 1 || r < -1 || r > 1) {
    document.getElementById('error').style.display = 'block';
    return;
  }
  
  // Calculate equivalent tax rate
  var t = (1 - ((r * (1 - theta)) / (r + theta))) * 100;
  
  // Round to 3 decimal places
  t = Math.round(t * 1000) / 1000;
  
  // Display result
  document.getElementById('resultText').innerHTML = 
    "The equivalent capital income tax rate is <strong>" + t + "%</strong>";
  document.getElementById('result').style.display = 'block';
}
</script>


<h2 style="text-align: center;">State Tax Burden Simulator</h2>
<p> This calculator quantifies the equivalent capital income tax rate (t*) of a wealth tax while also allowing for the application of capital gains rates by state.
It addresses the question: What rate of income taxation on capital yields the same economic outcome as living under a wealth tax, when adjusting for the state I pay taxes in?
</p>
<hr style="margin: 40px 0; border: 1px solid #ddd;">

<div style="max-width: 600px; margin: 0 auto; padding: 20px;">
  <h2 style="text-align: center;">Wealth Tax Calculator with Capital Gains Tax</h2>
  
  <div style="margin: 20px 0;">
    <label for="state" style="display: block; margin-bottom: 5px;">
      <strong>Select State:</strong>
    </label>
    <select id="state" style="width: 100%; padding: 8px; font-size: 16px;">
      <option value="0.2">United States (Federal Only)</option>
      <option value="0.308">Washington State</option>
      <option value="0.371">California</option>
    </select>
  </div>

  <div style="margin: 20px 0;">
    <label for="theta1" style="display: block; margin-bottom: 5px;">
      <strong>Expropriation Risk - Wealth Tax Rate (θ):</strong>
    </label>
    <input type="number" id="theta1" step="0.001" value="" min="0" max="1"
           style="width: 100%; padding: 8px; font-size: 16px;">
  </div>

  <div style="margin: 20px 0;">
    <label for="r1" style="display: block; margin-bottom: 5px;">
      <strong>Risk Free Rate (r):</strong>
    </label>
    <input type="number" id="r1" step="0.001" value="" min="-1" max="1"
           style="width: 100%; padding: 8px; font-size: 16px;">
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
  // Get input values
  var theta = parseFloat(document.getElementById('theta1').value);
  var r = parseFloat(document.getElementById('r1').value);
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
![alt text]({{ site.baseurl }}/assets/rhoformula.jpg "Profile Picture"){:.profile}

<hr style="margin: 40px 0; border: 1px solid #ddd;">

<div style="max-width: 600px; margin: 0 auto; padding: 20px;">
  <h2 style="text-align: center;">Rho (&rho;) Calculator</h2>
  
  <div style="margin: 20px 0;">
    <label for="r2" style="display: block; margin-bottom: 5px;">
      <strong>Baseline Return (r):</strong>
    </label>
    <input type="number" id="r2" step="0.001" value="" min="-1" max="1"
           style="width: 100%; padding: 8px; font-size: 16px;">
  </div>

  <div style="margin: 20px 0;">
    <label for="t2" style="display: block; margin-bottom: 5px;">
      <strong>Equivalent Capital Income Tax Rate (t):</strong>
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
  // Get input values
  var r = parseFloat(document.getElementById('r2').value);
  var t = parseFloat(document.getElementById('t2').value);
  
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
    document.getElementById('error2').innerHTML = '<strong>Error: t cannot equal 1 (division by zero).</strong>';
    return;
  }
  
  // Calculate rho
  var rho = r / (1 - t);
  
  // Round to 3 decimal places
  rho = Math.round(rho * 1000) / 1000;
  
  // Display result
  document.getElementById('resultText2').innerHTML = 
    "A required pre-tax return on assets of <strong>" + rho + "</strong> is needed to compensate for the expropriation risk.";
  document.getElementById('result2').style.display = 'block';
}
</script>