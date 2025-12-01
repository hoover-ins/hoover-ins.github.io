---
layout: page
title: TaxCalc
permalink: /taxcalc/
main_nav: true
---
<h2 style="text-align: center;">Purpose</h2>

<p>The Fiscal Policy Initiative's TaxCalc estimates the aggregate revenue and distributional effects of tax reforms using sample data that represents the United States population.TaxCalc is adapted from <a href="https://taxcalc.pslmodels.org/">Policy Simulation Library's open-source Tax-Calculator model</a> and has over 200 adjustable parameters that can be changed by users without doing any programming.</p>

<h2 style="text-align: center;">TaxCalc Data</h2>

<p>TaxCalc can be used with two different datasets: the Current Population Survey (CPS) and the 2011 IRS Public Use File (PUF)</p>




<h2 style="text-align: center;">Policy Parameters</h2>


<hr style="margin: 40px 0; border: 1px solid #ddd;">

<div style="max-width: 600px; margin: 0 auto; padding: 20px;">
  <h2 style="text-align: center;">Parameter Dictionary</h2>
  
  <div style="margin: 20px 0;">
    <label for="state" style="display: block; margin-bottom: 5px;">
      <strong>View Parameter Type:</strong>
    </label>
    <select id="state" style="width: 100%; padding: 8px; font-size: 16px;">
      <option value="">Select a parameter type...</option>
      <option value="indexing">Parameter Indexing</option>
      <option value="payroll">Payroll Taxes</option>
      <option value="ss-taxability">Social Security Taxability</option>
      <option value="above-line-deductions">Above the Line Deductions</option>
      <option value="personal-exemp">Personal Exemptions</option>
      <option value="standard-deduct">Standard Deduction</option>
      <option value="nonrefund-credits">Nonrefundable Credits</option>
      <option value="child-dep-credits">Child/Dependent Credits</option>
      <option value="item-deductions">Itemized Deductions</option>
      <option value="cap-gains-and-dividends">Capital Gains and Dividends</option>
      <option value="personal-income">Personal Income</option>
      <option value="other-tax">Other Taxes</option>
      <option value="refund-credits">Refundable Credits</option>
      <option value="surtaxes">Surtaxes</option>
      <option value="ubi">Universal Basic Income</option>
      <option value="benefits">Benefits</option>
      <option value="other">Other Parameters</option>
    </select>
  </div>

  <div id="paramContent" style="margin-top: 30px; padding: 20px; background-color: #f9f9f9; border-radius: 8px; display: none;">
    <div id="indexing" class="param-section" style="display: none;">
      <h3>Parameter Indexing</h3>
      <p>Description: Values are zero before 2017; reforms that introduce indexing with chained CPI would have values around -0.0025 beginning in the year before the first year policy parameters will have values computed with chained CPI.</p>
    </div>
    <div id="payroll" class="param-section" style="display: none;">
      <h3></h3>
      <p>Description: </p>
    </div>
    <div id="ss-taxability" class="param-section" style="display: none;">
      <h3></h3>
      <p>Description: </p>
    </div>
    <div id="above-line-deductions" class="param-section" style="display: none;">
      <h3></h3>
      <p>Description: </p>
    </div>
    <div id="personal-exemp" class="param-section" style="display: none;">
      <h3></h3>
      <p>Description: </p>
    </div>
    <div id="standard-deduct" class="param-section" style="display: none;">
      <h3></h3>
      <p>Description: </p>
    </div>
    <div id="nonrefund-credits" class="param-section" style="display: none;">
      <h3></h3>
      <p>Description: </p>
    </div>
    <div id="child-dep-credits" class="param-section" style="display: none;">
      <h3></h3>
      <p>Description: </p>
    </div>
    <div id="item-deductions" class="param-section" style="display: none;">
      <h3></h3>
      <p>Description: </p>
    </div>
    <div id="cap-gains-and-dividends" class="param-section" style="display: none;">
      <h3></h3>
      <p>Description: </p>
    </div>
    <div id="personal-income" class="param-section" style="display: none;">
      <h3></h3>
      <p>Description: </p>
    </div>
    <div id="other-tax" class="param-section" style="display: none;">
      <h3></h3>
      <p>Description: </p>
    </div>
    <div id="refund-credits" class="param-section" style="display: none;">
      <h3></h3>
      <p>Description: </p>
    </div>
    <div id="surtaxes" class="param-section" style="display: none;">
      <h3></h3>
      <p>Description: </p>
    </div>
    <div id="ubi" class="param-section" style="display: none;">
      <h3></h3>
      <p>Description: </p>
    </div>
    <div id="benefits" class="param-section" style="display: none;">
      <h3></h3>
      <p>Description: </p>
    </div>
    <div id="other" class="param-section" style="display: none;">
      <h3></h3>
      <p>Description: </p>
    </div>
  </div>
</div>

<script>
  document.getElementById('state').addEventListener('change', function() {
    const selectedValue = this.value;
    const contentDiv = document.getElementById('paramContent');
    const allSections = document.querySelectorAll('.param-section');
        
  // Hide all sections at first
  allSections.forEach(section => section.style.display = 'none');
  if (selectedValue) {
    // Show the container and selected section
    contentDiv.style.display = 'block';
    document.getElementById(selectedValue).style.display = 'block';
  } else {
    // Hide container if nothing selected
    contentDiv.style.display = 'none';
  }
});
</script>

The academic content, calculator methodology, and associated research are © 2025 Benjamin Jaros. For inquiries regarding the research or calculator, please contact: hooverfpi@stanford.edu.

<p>Page last updated December 1, 2025.</p>
