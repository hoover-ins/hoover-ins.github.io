---
layout: page
title: Wealth Tax Calculator
permalink: /wealthtaxcalculator/
main_nav: true
---

---
layout: page
title: Tax Calculator
permalink: /tax-calculator/
main_nav: true
---

<div style="max-width: 600px; margin: 0 auto; padding: 20px;">
  <h2 style="text-align: center;">Equivalent Capital Income Tax Calculator</h2>
  
  <div style="margin: 20px 0;">
    <label for="theta" style="display: block; margin-bottom: 5px;">
      <strong>Expropriation Risk (Wealth Tax Rate) θ:</strong>
    </label>
    <input type="number" id="theta" step="0.001" value="0.01" 
           style="width: 100%; padding: 8px; font-size: 16px;">
  </div>

  <div style="margin: 20px 0;">
    <label for="r" style="display: block; margin-bottom: 5px;">
      <strong>Baseline Return (r):</strong>
    </label>
    <input type="number" id="r" step="0.001" value="0.015" 
           style="width: 100%; padding: 8px; font-size: 16px;">
  </div>

  <button onclick="calculate()" 
          style="width: 100%; padding: 12px; font-size: 18px; background-color: #0074D9; color: white; border: none; cursor: pointer; margin: 20px 0;">
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
    "The equivalent capital income tax rate is <strong>" + t + "%</strong>";
  document.getElementById('result').style.display = 'block';
}
</script>
