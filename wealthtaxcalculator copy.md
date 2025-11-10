---
layout: page
title: Wealth Tax Calculator (Base)
permalink: /wealthtaxcalculatorbase/
main_nav: true
---

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