---
layout: page
title: Wealth Tax Calculator
permalink: /wealthtaxcalculator/
main_nav: true
---
<h2 style="text-align: center;">Purpose</h2>
This calculator quantifies the equivalent capital income tax rate of a wealth tax.
It addresses the question: What rate of income taxation on capital yields the same economic outcome as living under a wealth tax?
<h2 style="text-align: center;">Try It</h2>
Input values for:
<p><strong>Expropriation Risk - Wealth Tax Rate (θ):</strong> A wealth tax of 1% may be entered as 0.01.</p>
<p><strong>Baseline Return (r):</strong> This reflects the return to capital in the economy. For reference, the average return to capital in advanced economies is between 4% and 8%. Returns vary more widely among sectors. A baseline return of 5% may be entered as 0.5.</p>

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
<table>

<div style="max-width: 600px; margin: 0 auto; padding: 20px;">
  <h2 style="text-align: center;">Input your parameters below</h2>
  
  <div style="margin: 20px 0;">
    <label for="theta" style="display: block; margin-bottom: 5px;">
      <strong>Expropriation Risk - Wealth Tax Rate (θ):</strong>
    </label>
    <input type="number" id="theta" step="0.001" value=""
           style="width: 100%; padding: 8px; font-size: 16px;">
  </div>

  <div style="margin: 20px 0;">
    <label for="r" style="display: block; margin-bottom: 5px;">
      <strong>Baseline Return (r):</strong>
    </label>
    <input type="number" id="r" step="0.001" value="" 
           style="width: 100%; padding: 8px; font-size: 16px;">
  </div>

  <button onclick="calculate()" 
          style="width: 100%; padding: 12px; font-size: 18px; background-color: #B3173C; color: white; border: none; cursor: pointer; margin: 20px 0;">
    Calculate
  </button>

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
  
  // Calculate equivalent tax rate
  var t = (1 - ((r * (1 - theta)) / (r + theta))) * 100;
  
  // Round to 3 decimal places
  t = Math.round(t * 1000) / 1000;
  
  // Display result
  document.getElementById('resultText').innerHTML = 
    "The equivalent capital income tax rate is <strong>" + t + "%.</strong>";
  document.getElementById('result').style.display = 'block';
}
</script>
