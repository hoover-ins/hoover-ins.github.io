---
layout: page
title: TaxCalc
permalink: /taxcalc/
main_nav: true
---
<h2 style="text-align: center;">Purpose</h2>

<p>The Fiscal Policy Initiative's TaxCalc estimates the aggregate revenue and distributional effects of tax reforms using sample data that represents the United States population. TaxCalc is adapted from <a href="https://taxcalc.pslmodels.org/">Policy Simulation Library's open-source Tax-Calculator model</a> and has over 200 adjustable parameters that can be changed by users without doing any programming.</p>

<h2 style="text-align: center;">TaxCalc Data</h2>

<p>TaxCalc can be used with two different datasets: the Current Population Survey (CPS) and the 2011 IRS Public Use File (PUF).</p>

<h4 style="text-align: center;">Current Population Survey (cps.csv)</h4>
<p>This file is based on publicly available survey data, which is weighted to hit IRS Statistics of Income targets. The data are then grown out to hit aggregate forecasts through the time horizon available in Tax-Calculator (approximately the next 10 years). All the files required to use this prepared data option are included in the Tax-Calculator package.</p>


<h4 style="text-align: center;">2011 IRS Public Use File (puf.csv)</h4>
<p>The taxdata repository also produces a weights file and growth factors file for use with the 2011 IRS-SOI Public Use File (PUF). For users who have purchased their own version of the 2011 PUF, the puf.csv, puf_weights.csv.gz and puf_ratios.csv files from the taxdata repository, can be used by Tax-Calculator using the Records.puf_constructor(...) static method.</p>

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
      <h4>Offsets</h4>
      <p><strong>parameter_indexing_CPI_offset:</strong> Values are zero before 2017; reforms that introduce indexing with chained CPI would have values around -0.0025 beginning in the year before the first year policy parameters will have values computed with chained CPI.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: -0.0025 2018: -0.0025 2019: -0.0025 2020: -0.0025 2021: -0.0025 2022: -0.0025 2023: -0.0025 2024: -0.0025 2025: -0.0025 2026: -0.0025 Valid Range: min = -0.005 and max = 0.005 Out-of-Range Action: error</p>
    </div>
    <div id="payroll" class="param-section" style="display: none;">
      <h3>Payroll Taxes</h3>
      <h4>Additional Medicare FICA</h4>
      <p><strong>AMEDT_ec:</strong> The Additional Medicare Tax rate, AMEDT_rt, applies to all earnings in excess of this excluded amount.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [200000.0, 250000.0, 125000.0, 200000.0, 200000.0] 2014: [200000.0, 250000.0, 125000.0, 200000.0, 200000.0] 2015: [200000.0, 250000.0, 125000.0, 200000.0, 200000.0] 2016: [200000.0, 250000.0, 125000.0, 200000.0, 200000.0] 2017: [200000.0, 250000.0, 125000.0, 200000.0, 200000.0] 2018: [200000.0, 250000.0, 125000.0, 200000.0, 200000.0] 2019: [200000.0, 250000.0, 125000.0, 200000.0, 200000.0] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>AMEDT_rt:</strong> This is the rate applied to the portion of Medicare wages, RRTA compensation and self-employment income exceeding the Additional Medicare Tax earning exclusion.</p>
      <p>Known Values: 2013: 0.009 2014: 0.009 2015: 0.009 2016: 0.009 2017: 0.009 2018: 0.009 2019: 0.009 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <h4>Medicare FICA</h4>
      <p><strong>FICA_mc_trt_employer:</strong> Employer side Medicare FICA rate.</p>
      <p>Known Values: 2013: 0.0145 2014: 0.0145 2015: 0.0145 2016: 0.0145 2017: 0.0145 2018: 0.0145 2019: 0.0145 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>FICA_mc_trt_employee:</strong> Employee side Medicare FICA rate.</p>
      <p>Known Values: 2013: 0.0145 2014: 0.0145 2015: 0.0145 2016: 0.0145 2017: 0.0145 2018: 0.0145 2019: 0.0145 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <h4>Social Security FICA</h4>
      <p><strong>FICA_ss_trt_employer:</strong> Employee side Social Security FICA rate.</p>
      <p>Known Values: 2013: 0.062 2014: 0.062 2015: 0.062 2016: 0.062 2017: 0.062 2018: 0.062 2019: 0.062 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>SS_Earnings_c:</strong> Individual earnings below this amount are subjected to Social Security (OASDI) payroll tax.</p>
      <p>Known Values: 2013: 113700.0 2014: 117000.0 2015: 118500.0 2016: 118500.0 2017: 127200.0 2018: 128400.0 2019: 132900.0 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>SS_Earnings_thd:</strong> Individual earnings above this threshold are subjected to Social Security (OASDI) payroll tax, in addition to earnings below the maximum taxable earnings threshold.</p>
      <p>Known Values: 2013: 9e+99 2014: 9e+99 2015: 9e+99 2016: 9e+99 2017: 9e+99 2018: 9e+99 2019: 9e+99 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
    </div>
    <div id="ss-taxability" class="param-section" style="display: none;">
      <h3>Social Security Taxability</h3>
      <h4>Social Security Benefit Taxability</h4>
      <p><strong>SS_thd1:</strong> The first threshold for Social Security benefit taxability: if taxpayers have provisional income greater than this threshold, up to rate 1 of their Social Security benefit will be subject to tax under current law.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [25000.0, 32000.0, 25000.0, 25000.0, 25000.0] 2014: [25000.0, 32000.0, 25000.0, 25000.0, 25000.0] 2015: [25000.0, 32000.0, 25000.0, 25000.0, 25000.0] 2016: [25000.0, 32000.0, 25000.0, 25000.0, 25000.0] 2017: [25000.0, 32000.0, 25000.0, 25000.0, 25000.0] 2018: [25000.0, 32000.0, 25000.0, 25000.0, 25000.0] 2019: [25000.0, 32000.0, 25000.0, 25000.0, 25000.0] Valid Range: min = 0 and max = SS_thd85 Out-of-Range Action: error</p>
      <p><strong>SS_percentage1:</strong> Under current law if their provisional income is above the first threshold for Social Security taxability but below the second threshold, taxpayers need to apply this fraction to both the excess of their provisional income over the first threshold and their Social Security benefits, and then include the smaller one in their AGI.</p>
      <p>Known Values: 2013: 0.5 2014: 0.5 2015: 0.5 2016: 0.5 2017: 0.5 2018: 0.5 2019: 0.5 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>SS_thd2:</strong> The second threshold for Social Security taxability: if taxpayers have provisional income greater than this threshold, up to rate 2 of their Social Security benefit will be subject to tax under current law.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [34000.0, 44000.0, 34000.0, 34000.0, 34000.0] 2014: [34000.0, 44000.0, 34000.0, 34000.0, 34000.0] 2015: [34000.0, 44000.0, 34000.0, 34000.0, 34000.0] 2016: [34000.0, 44000.0, 34000.0, 34000.0, 34000.0] 2017: [34000.0, 44000.0, 34000.0, 34000.0, 34000.0] 2018: [34000.0, 44000.0, 34000.0, 34000.0, 34000.0] 2019: [34000.0, 44000.0, 34000.0, 34000.0, 34000.0] Valid Range: min = SS_thd50 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>SS_percentage2:</strong> Under current law if their provisional income is above the second threshold for Social Security taxability, taxpayers need to apply this fraction to both the excess of their provisional income over the second threshold and their social security benefits, and then include the smaller one in their AGI.</p>
      <p>Known Values: 2013: 0.85 2014: 0.85 2015: 0.85 2016: 0.85 2017: 0.85 2018: 0.85 2019: 0.85 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
    </div>
    <div id="above-line-deductions" class="param-section" style="display: none;">
      <h3>Above The Line Deductions</h3>
      <h4>Child And Elderly Care</h4>
      <p><strong>ALD_Dependents_hc:</strong> This decimal fraction, if greater than zero, reduces the portion of childcare costs that can be deducted from AGI.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>ALD_Dependents_Child_c:</strong> The weighted average of childcare costs in the US. 7165 is the weighted average from the ‘Child Care in America: 2016 State Fact Sheets’.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>ALD_Dependents_Elder_c:</strong> A taxpayer can take an above the line deduction up to this amount if they have an elderly dependent. The Trump 2016 campaign proposal was for $5000.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>ALD_Dependents_thd:</strong> A taxpayer can only claim the dependent care deduction if their total income is below this level. The Trump 2016 campaign proposal was for 250000 single, 500000 joint, 250000 separate, 500000 head of household</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [0.0, 0.0, 0.0, 0.0, 0.0] 2014: [0.0, 0.0, 0.0, 0.0, 0.0] 2015: [0.0, 0.0, 0.0, 0.0, 0.0] 2016: [0.0, 0.0, 0.0, 0.0, 0.0] 2017: [0.0, 0.0, 0.0, 0.0, 0.0] 2018: [0.0, 0.0, 0.0, 0.0, 0.0] 2019: [0.0, 0.0, 0.0, 0.0, 0.0] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <h4>Misc. Adjustment Haircuts</h4>
      <p><strong>ALD_StudentLoan_hc:</strong> This decimal fraction can be applied to limit the student loan interest adjustment allowed. Notes: The final adjustment amount will be (1-Haircut)*StudentLoanInterest.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>ALD_SelfEmploymentTax_hc:</strong> This decimal fraction, if greater than zero, reduces the employer equivalent portion of self-employment adjustment.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>ALD_SelfEmp_HealthIns_hc:</strong> This decimal fraction, if greater than zero, reduces the health insurance adjustment for self-employed taxpayers.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>ALD_KEOGH_SEP_hc:</strong> Under current law, contributions to Keogh or SEP plans can be fully deducted from gross income. This haircut can be used to limit the adjustment allowed.</p>
      <p>2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>ALD_EarlyWithdraw_hc:</strong> Under current law, early withdraw penalty can be fully deducted from gross income. This haircut can be used to limit the adjustment allowed.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>ALD_AlimonyPaid_hc:</strong> Under pre-TCJA law, the full amount of alimony paid is taken as an adjustment from gross income in arriving at AGI. This haircut can be used to change the deduction allowed.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 1.0 2020: 1.0 2021: 1.0 2022: 1.0 2023: 1.0 2024: 1.0 2025: 1.0 2026: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>ALD_AlimonyReceived_hc:</strong> Under pre-TCJA law, none of alimony received is taken as an adjustment from gross income in arriving at AGI. This haircut can be used to change the deduction allowed.</p>
      <p>Known Values: 2013: 1.0 2014: 1.0 2015: 1.0 2016: 1.0 2017: 1.0 2018: 1.0 2019: 0.0 2020: 0.0 2021: 0.0 2022: 0.0 2023: 0.0 2024: 0.0 2025: 0.0 2026: 1.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>ALD_EducatorExpenses_hc:</strong> If greater than zero, this decimal fraction reduces the portion of educator expenses that can be deducted from AGI.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>ALD_HSADeduction_hc:</strong> If greater than zero, this decimal fraction reduces the portion of a taxpayer’s HSA deduction that can be deducted from AGI.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>ALD_IRAContributions_hc:</strong> If greater than zero, this decimal fraction reduces the portion of IRA contributions that can be deducted from AGI.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>ALD_DomesticProduction_hc:</strong> If greater than zero, this decimal fraction reduces the portion of domestic production activity that can be deducted from AGI.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 1.0 2019: 1.0 2020: 1.0 2021: 1.0 2022: 1.0 2023: 1.0 2024: 1.0 2025: 1.0 2026: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>ALD_Tuition_hc:</strong> If greater than zero, this decimal fraction reduces the portion of tuition and fees that can be deducted from AGI.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 1.0 2019: 1.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <h4>Misc. Exclusions</h4>
      <p><strong>ALD_InvInc_ec_rt:</strong> Decimal fraction of investment income base that can be excluded from AGI.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>ALD_BusinessLosses_c:</strong> Business losses in excess of this amount may not be deducted from AGI.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2014: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2015: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2016: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2017: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2018: [250000.0, 500000.0, 250000.0, 250000.0, 500000.0] 2019: [255000.0, 510000.0, 255000.0, 255000.0, 510000.0] 2020: [258927.0, 517854.0, 258927.0, 258927.0, 517854.0] 2021: [260817.17, 521634.33, 260817.17, 260817.17, 521634.33] 2022: [263294.93, 526589.86, 263294.93, 263294.93, 526589.86] 2023: [267454.99, 534909.98, 267454.99, 267454.99, 534909.98] 2024: [272616.87, 545233.74, 272616.87, 272616.87, 545233.74] 2025: [278069.21, 556138.41, 278069.21, 278069.21, 556138.41] 2026: [283535.22, 567070.42, 283535.22, 283535.22, 567070.42] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
    </div>
    <div id="personal-exemp" class="param-section" style="display: none;">
      <h3>Personal Exemptions</h3>
      <h4>Personal And Dependent Exemption Amount</h4>
      <p><strong>II_em:</strong> Subtracted from AGI in the calculation of taxable income, per taxpayer and dependent.</p>
      <p>Known Values: 2013: 3900.0 2014: 3950.0 2015: 4000.0 2016: 4050.0 2017: 4050.0 2018: 0.0 2019: 0.0 2020: 0.0 2021: 0.0 2022: 0.0 2023: 0.0 2024: 0.0 2025: 0.0 2026: 4691.0 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <h4>Personal Exemption Phaseout</h4>
      <p><strong>II_prt:</strong> Personal exemption amount will decrease by this rate for each dollar of AGI exceeding exemption phaseout start.</p>
      <p>Known Values: 2013: 0.02 2014: 0.02 2015: 0.02 2016: 0.02 2017: 0.02 2018: 0.02 2019: 0.02 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <h4>Repeal for Dependents Under Age 18</h4>
      <p><strong>II_no_em_nu18:</strong> Total personal exemptions will be decreased by the number of dependents under the age of 18.</p>
      <p>Known Values: 2013: False 2014: False 2015: False 2016: False 2017: False 2018: False 2019: False Valid Range: min = False and max = True Out-of-Range Action: error</p>
    </div>
    <div id="standard-deduct" class="param-section" style="display: none;">
      <h3>Standard Deduction</h3>
      <h4>Additional Standard Deduction For Blind And Aged</h4>
      <p><strong>STD_Aged:</strong> To get the standard deduction for aged or blind individuals, taxpayers need to add this value to regular standard deduction.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [1500.0, 1200.0, 1200.0, 1500.0, 1200.0] 2014: [1550.0, 1200.0, 1200.0, 1550.0, 1200.0] 2015: [1550.0, 1250.0, 1250.0, 1550.0, 1250.0] 2016: [1550.0, 1250.0, 1250.0, 1550.0, 1250.0] 2017: [1550.0, 1250.0, 1250.0, 1550.0, 1250.0] 2018: [1600.0, 1300.0, 1300.0, 1600.0, 1300.0] 2019: [1650.0, 1300.0, 1300.0, 1650.0, 1300.0] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <h4>Standard Deduction Amount</h4>
      <p><strong>STD:</strong> Amount filing unit can use as a standard deduction.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [6100.0, 12200.0, 6100.0, 8950.0, 12200.0] 2014: [6200.0, 12400.0, 6200.0, 9100.0, 12400.0] 2015: [6300.0, 12600.0, 6300.0, 9250.0, 12600.0] 2016: [6300.0, 12600.0, 6300.0, 9300.0, 12600.0] 2017: [6350.0, 12700.0, 6350.0, 9350.0, 12700.0] 2018: [12000.0, 24000.0, 12000.0, 18000.0, 24000.0] 2019: [12200.0, 24400.0, 12200.0, 18350.0, 24400.0] 2020: [12387.88, 24775.76, 12387.88, 18632.59, 24775.76] 2021: [12478.31, 24956.62, 12478.31, 18768.61, 24956.62] 2022: [12596.85, 25193.71, 12596.85, 18946.91, 25193.71] 2023: [12795.88, 25591.77, 12795.88, 19246.27, 25591.77] 2024: [13042.84, 26085.69, 13042.84, 19617.72, 26085.69] 2025: [13303.7, 26607.4, 13303.7, 20010.07, 26607.4] 2026: [7355.0, 14711.0, 7355.0, 10831.0, 14711.0] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
    </div>
    <div id="nonrefund-credits" class="param-section" style="display: none;">
      <h3>Nonrefundable Credits</h3>
      <h4>Child And Dependent Care</h4>
      <p><strong>CDCC_c:</strong> The maximum amount of expenses allowed for each qualifying dependent.</p>
      <p>Known Values: 2013: 3000.0 2014: 3000.0 2015: 3000.0 2016: 3000.0 2017: 3000.0 2018: 3000.0 2019: 3000.0 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>CDCC_ps:</strong> For taxpayers with AGI over this amount, the rate of the credit is reduced by one percentage point each $2,000 of AGI over this amount.</p>
      <p>Known Values: 2013: 15000.0 2014: 15000.0 2015: 15000.0 2016: 15000.0 2017: 15000.0 2018: 15000.0 2019: 15000.0 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>CDCC_ps2:</strong> For taxpayers with AGI over this amount, the rate of the credit is reduced by one percentage point each $2,000 of AGI over this amount.</p>
      <p>Known Values: 2013: 9e+99 2014: 9e+99 2015: 9e+99 2016: 9e+99 2017: 9e+99 2018: 9e+99 2019: 9e+99 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>CDCC_crt:</strong> The maximum rate for the CDCC; this rate decreases as AGI rises above the CDCC_ps level.</p>
      <p>Known Values: 2013: 0.35 2014: 0.35 2015: 0.35 2016: 0.35 2017: 0.35 2018: 0.35 2019: 0.35 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>CDCC_frt:</strong> The minimum rate for the first AGI phaseout of the CDCC.</p>
      <p>Known Values: 2013: 0.20 2014: 0.20 2015: 0.20 2016: 0.20 2017: 0.20 2018: 0.20 2019: 0.20 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>CDCC_prt:</strong> The CDCC credit rate is reduced by this many percentage points for each dollar of AGI over the phase-out thresholds.</p>
      <p>Known Values: 2013: 0.0005 2014: 0.0005 2015: 0.0005 2016: 0.0005 2017: 0.0005 2018: 0.0005 2019: 0.0005 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>CDCC_refundable:</strong> If true, the CDCC is fully refundable.</p>
      <p>Known Values: 2013: False 2014: False 2015: False 2016: False 2017: False 2018: False 2019: False Valid Range: min = False and max = True Out-of-Range Action: error</p>
      <h4>Misc. Credit Limits</h4>
      <p><strong>CR_RetirementSavings_hc:</strong> If greater than zero, this decimal fraction reduces the portion of the retirement savings credit that can be claimed.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>CR_ForeignTax_hc:</strong> If greater than zero, this decimal fraction reduces the portion of the foreign tax credit that can be claimed.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>CR_ResidentialEnergy_hc:</strong> If greater than zero, this decimal fraction reduces the portion of the residential energy credit that can be claimed.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>CR_GeneralBusiness_hc:</strong> If greater than zero, this decimal fraction reduces the portion of the general business credit that can be claimed.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>CR_MinimumTax_hc:</strong> If greater than zero, this decimal fraction reduces the portion of the previous year minimum tax credit that can be claimed.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>CR_AmOppRefundable_hc:</strong> If greater than zero, this decimal fraction reduces the portion of the refundable American Opportunity credit that can be claimed.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>CR_AmOppNonRefundable_hc:</strong> If greater than zero, this decimal fraction reduces the portion of the nonrefundable American Opportunity credit that can be claimed.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>CR_SchR_hc:</strong> If greater than zero, this decimal fraction reduces the portion of Schedule R credit that can be claimed.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>CR_OtherCredits_hc:</strong> If greater than zero, this decimal fraction reduces the portion of other credit that can be claimed.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>CR_Education_hc:</strong> If greater than zero, this decimal fraction reduces the portion of education credits that can be claimed.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <h4>Personal Nonrefundable Credit</h4>
      <p><strong>II_credit_nr:</strong> This credit amount is not refundable and is phased out based on AGI.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [0.0, 0.0, 0.0, 0.0, 0.0] 2014: [0.0, 0.0, 0.0, 0.0, 0.0] 2015: [0.0, 0.0, 0.0, 0.0, 0.0] 2016: [0.0, 0.0, 0.0, 0.0, 0.0] 2017: [0.0, 0.0, 0.0, 0.0, 0.0] 2018: [0.0, 0.0, 0.0, 0.0, 0.0] 2019: [0.0, 0.0, 0.0, 0.0, 0.0] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>II_credit_nr_ps:</strong> The personal nonrefundable credit amount will be reduced for taxpayers with AGI higher than this threshold level.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [0.0, 0.0, 0.0, 0.0, 0.0] 2014: [0.0, 0.0, 0.0, 0.0, 0.0] 2015: [0.0, 0.0, 0.0, 0.0, 0.0] 2016: [0.0, 0.0, 0.0, 0.0, 0.0] 2017: [0.0, 0.0, 0.0, 0.0, 0.0] 2018: [0.0, 0.0, 0.0, 0.0, 0.0] 2019: [0.0, 0.0, 0.0, 0.0, 0.0] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>II_credit_nr_prt:</strong> The personal nonrefundable credit amount will be reduced at this rate for each dollar of AGI exceeding the II_credit_nr_ps threshold.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
    </div>
    <div id="child-dep-credits" class="param-section" style="display: none;">
      <h3>Child/Dependent Credits</h3>
      <h4>Additional Child Tax Credit</h4>
      <p><strong>ACTC_c:</strong> This refundable credit is applied to child dependents and phases out exactly like the CTC amount.</p>
      <p>Known Values: 2013: 1000.0 2014: 1000.0 2015: 1000.0 2016: 1000.0 2017: 1000.0 2018: 1400.0 2019: 1400.0 2020: 1400.0 2021: 1400.0 2022: 1500.0 2023: 1500.0 2024: 1500.0 2025: 1600.0 2026: 1000.0 Valid Range: min = 0 and max = CTC_c Out-of-Range Action: error</p>
      <p><strong>ACTC_rt:</strong> This is the fraction of earnings used in calculating the ACTC, which is a partially refundable credit that supplements the CTC for some taxpayers.</p>
      <p>Known Values: 2013: 1000.0 2014: 1000.0 2015: 1000.0 2016: 1000.0 2017: 1000.0 2018: 1400.0 2019: 1400.0 2020: 1400.0 2021: 1400.0 2022: 1500.0 2023: 1500.0 2024: 1500.0 2025: 1600.0 2026: 1000.0 Valid Range: min = 0 and max = CTC_c Out-of-Range Action: error</p>
      <p><strong>ACTC_rt:</strong> This is the fraction of earnings used in calculating the ACTC, which is a partially refundable credit that supplements the CTC for some taxpayers.</p>
      <p>Known Values: 2013: 0.15 2014: 0.15 2015: 0.15 2016: 0.15 2017: 0.15 2018: 0.15 2019: 0.15 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>ACTC_rt_bonus_under6family:</strong> For families with qualifying children under 6 years old, this bonus rate is added to the fraction of earnings (additional child tax credit rate) used in calculating the ACTC.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>ACTC_Income_thd:</strong> The portion of earned income below this threshold does not count as base for the Additional Child Tax Credit.</p>
      <p>Known Values: 2013: 3000.0 2014: 3000.0 2015: 3000.0 2016: 3000.0 2017: 3000.0 2018: 2500.0 2019: 2500.0 2020: 2500.0 2021: 2500.0 2022: 2500.0 2023: 2500.0 2024: 2500.0 2025: 2500.0 2026: 3000.0 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>ACTC_ChildNum:</strong> Families with this number of qualified children or more may qualify for a different formula to calculate the Additional Child Tax Credit, which is a partially refundable credit that supplements the Child Tax Credit for some taxpayers.</p>
      <p>Known Values: 2013: 3 2014: 3 2015: 3 2016: 3 2017: 3 2018: 3 2019: 3 Valid Range: min = 0 and max = 99 Out-of-Range Action: error</p>
      <h4>Child Tax Credit</h4>
      <p><strong>CTC_c:</strong> The maximum nonrefundable credit allowed for each child.</p>
      <p>Known Values: 2013: 1000.0 2014: 1000.0 2015: 1000.0 2016: 1000.0 2017: 1000.0 2018: 2000.0 2019: 2000.0 2020: 2000.0 2021: 2000.0 2022: 2000.0 2023: 2000.0 2024: 2000.0 2025: 2000.0 2026: 1000.0 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>CTC_c_under6_bonus:</strong> The maximum amount of child tax credit allowed for each child is increased by this amount for qualifying children under 6 years old.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>CTC_include17:</strong> If true, children eligible for the child tax credit include those of age 17.</p>
      <p>Known Values: 2013: False 2014: False 2015: False 2016: False 2017: False 2018: False 2019: False Valid Range: min = False and max = True Out-of-Range Action: error</p>
      <p><strong>CTC_refundable:</strong> If true, the child tax credit is made fully refundable.</p>
      <p>Known Values: 2013: False 2014: False 2015: False 2016: False 2017: False 2018: False 2019: False Valid Range: min = False and max = True Out-of-Range Action: error</p>
      <p><strong>CTC_ps:</strong> Child tax credit begins to decrease when MAGI is above this level; read descriptions of the dependent credit amounts for how they phase out when MAGI is above this level.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [75000.0, 110000.0, 55000.0, 75000.0, 75000.0] 2014: [75000.0, 110000.0, 55000.0, 75000.0, 75000.0] 2015: [75000.0, 110000.0, 55000.0, 75000.0, 75000.0] 2016: [75000.0, 110000.0, 55000.0, 75000.0, 75000.0] 2017: [75000.0, 110000.0, 55000.0, 75000.0, 75000.0] 2018: [200000.0, 400000.0, 200000.0, 200000.0, 400000.0] 2019: [200000.0, 400000.0, 200000.0, 200000.0, 400000.0] 2020: [200000.0, 400000.0, 200000.0, 200000.0, 400000.0] 2021: [200000.0, 400000.0, 200000.0, 200000.0, 400000.0] 2022: [200000.0, 400000.0, 200000.0, 200000.0, 400000.0] 2023: [200000.0, 400000.0, 200000.0, 200000.0, 400000.0] 2024: [200000.0, 400000.0, 200000.0, 200000.0, 400000.0] 2025: [200000.0, 400000.0, 200000.0, 200000.0, 400000.0] 2026: [75000.0, 110000.0, 55000.0, 75000.0, 75000.0] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>CTC_prt:</strong> The amount of the credit starts to decrease at this rate if MAGI is higher than child tax credit phaseout start.</p>
      <p>Known Values: 2013: 0.05 2014: 0.05 2015: 0.05 2016: 0.05 2017: 0.05 2018: 0.05 2019: 0.05 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <h4>Other Dependent Tax Credit</h4>
      <p><strong>ODC_c:</strong> This nonrefundable credit is applied to non-child dependents and phases out along with the CTC amount.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 500.0 2019: 500.0 2020: 500.0 2021: 500.0 2022: 500.0 2023: 500.0 2024: 500.0 2025: 500.0 2026: 0.0 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>ODC_refundable:</strong> If true, the other dependent tax credit is made fully refundable.</p>
      <p>Known Values: 2013: False 2014: False 2015: False 2016: False 2017: False 2018: False 2019: False Valid Range: min = False and max = True Out-of-Range Action: error</p>
    </div>
    <div id="item-deductions" class="param-section" style="display: none;">
      <h3>Itemized Deductions</h3>
      <h4>Casualty</h4>
      <p><strong>ID_Casualty_frt:</strong> Taxpayers are eligible to deduct the portion of their gross casualty losses exceeding this fraction of AGI.</p>
      <p>Known Values: 2013: 0.1 2014: 0.1 2015: 0.1 2016: 0.1 2017: 0.1 2018: 0.1 2019: 0.1 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>ID_Casualty_hc:</strong> This decimal fraction can be applied to limit the amount of casualty expense deduction allowed.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 1.0 2019: 1.0 2020: 1.0 2021: 1.0 2022: 1.0 2023: 1.0 2024: 1.0 2025: 1.0 2026: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>ID_Casualty_c:</strong> The amount of casualty expense deduction is limited to this dollar amount.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2014: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2015: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2016: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2017: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2018: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2019: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <h4>Ceiling On The Amount Of Itemized Deductions Allowed</h4>
      <p><strong>ID_c:</strong> The amount of itemized deductions is limited to this dollar amount.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2014: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2015: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2016: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2017: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2018: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2019: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <h4>Charity</h4>
      <p><strong>ID_Charity_crt_cash:</strong> The cash deduction for charity is capped at this fraction of AGI.</p>
      <p>Known Values: 2013: 0.5 2014: 0.5 2015: 0.5 2016: 0.5 2017: 0.5 2018: 0.6 2019: 0.6 2020: 1.0 2021: 0.6 2022: 0.6 2023: 0.6 2024: 0.6 2025: 0.6 2026: 0.5 Valid Range: min = 0 and max = 1.0 Out-of-Range Action: warn</p>
      <p><strong>ID_Charity_crt_noncash:</strong> The deduction for noncash charity contributions is capped at this fraction of AGI.</p>
      <p>Known Values: 2013: 0.3 2014: 0.3 2015: 0.3 2016: 0.3 2017: 0.3 2018: 0.3 2019: 0.3 Valid Range: min = 0 and max = 0.3 Out-of-Range Action: warn</p>
      <p><strong>ID_Charity_frt:</strong> Taxpayers are eligible to deduct the portion of their charitable expense exceeding this fraction of AGI.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>ID_Charity_hc:</strong> This decimal fraction can be applied to limit the amount of charity expense deduction allowed.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>ID_Charity_c:</strong> The amount of charity expense deduction is limited to this dollar amount.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2014: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2015: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2016: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2017: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2018: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2019: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>ID_Charity_f:</strong> Only charitable giving in excess of this dollar amount is eligible for a deduction.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [0.0, 0.0, 0.0, 0.0, 0.0] 2014: [0.0, 0.0, 0.0, 0.0, 0.0] 2015: [0.0, 0.0, 0.0, 0.0, 0.0] 2016: [0.0, 0.0, 0.0, 0.0, 0.0] 2017: [0.0, 0.0, 0.0, 0.0, 0.0] 2018: [0.0, 0.0, 0.0, 0.0, 0.0] 2019: [0.0, 0.0, 0.0, 0.0, 0.0] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <h4>Interest Paid</h4>
      <p><strong>ID_InterestPaid_hc:</strong> This decimal fraction can be applied to limit the amount of interest paid deduction allowed.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>ID_InterestPaid_c:</strong> The amount of interest paid deduction is limited to this dollar amount.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2014: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2015: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2016: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2017: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2018: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2019: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <h4>Itemized Deduction Limitation</h4>
      <p><strong>ID_ps:</strong> The itemized deductions will be reduced for taxpayers with AGI higher than this level.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [250000.0, 300000.0, 150000.0, 275000.0, 300000.0] 2014: [254200.0, 305050.0, 152525.0, 279650.0, 305050.0] 2015: [258250.0, 309900.0, 154950.0, 284050.0, 309900.0] 2016: [259400.0, 311300.0, 155650.0, 285350.0, 311300.0] 2017: [261500.0, 313800.0, 156900.0, 287650.0, 313800.0] 2018: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2019: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2020: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2021: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2022: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2023: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2024: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2025: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2026: [302907.0, 363489.0, 181744.0, 333198.0, 363489.0] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>ID_prt:</strong> Taxpayers will not be eligible to deduct the full amount of itemized deduction if their AGI is above the phaseout start. The deductible portion would be decreased at this rate for each dollar exceeding the start.</p>
      <p>Known Values: 2013: 0.03 2014: 0.03 2015: 0.03 2016: 0.03 2017: 0.03 2018: 0.0 2019: 0.0 2020: 0.0 2021: 0.0 2022: 0.0 2023: 0.0 2024: 0.0 2025: 0.0 2026: 0.03 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>ID_crt:</strong> The phaseout amount is capped at this fraction of the original total deduction.</p>
      <p>Known Values: 2013: 0.8 2014: 0.8 2015: 0.8 2016: 0.8 2017: 0.8 2018: 1.0 2019: 1.0 2020: 1.0 2021: 1.0 2022: 1.0 2023: 1.0 2024: 1.0 2025: 1.0 2026: 0.8 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <h4>Medical Expenses</h4>
      <p><strong>ID_Medical_frt:</strong> Taxpayers are eligible to deduct the portion of their medical expenses exceeding this fraction of AGI.</p>
      <p>Known Values: 2013: 0.1 2014: 0.1 2015: 0.1 2016: 0.1 2017: 0.075 2018: 0.075 2019: 0.075 2020: 0.075 2021: 0.075 2022: 0.075 2023: 0.075 2024: 0.075 2025: 0.075 2026: 0.075 Valid Range: min = 0.075 and max = 0.1 Out-of-Range Action: warn</p>
      <p><strong>ID_Medical_frt_add4aged:</strong> Elderly taxpayers have this fraction added to the value of the regular floor rate for deductible medical expenses. This fraction was -0.025 from 2013 to 2016, but that was temporary and it changed to zero beginning in 2017.</p>
      <p>Known Values: 2013: -0.025 2014: -0.025 2015: -0.025 2016: -0.025 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = -0.025 and max = 0.0 Out-of-Range Action: warn</p>
      <p><strong>ID_Medical_hc:</strong> This decimal fraction can be applied to limit the amount of medical expense deduction allowed.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>ID_Medical_c:</strong> The amount of medical expense deduction is limited to this dollar amount.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2014: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2015: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2016: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2017: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2018: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2019: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <h4>Miscellaneous</h4>
      <p><strong>ID_Miscellaneous_frt:</strong> Taxpayers are eligible to deduct the portion of their miscellaneous expense exceeding this fraction of AGI.</p>
      <p>Known Values: 2013: 0.02 2014: 0.02 2015: 0.02 2016: 0.02 2017: 0.02 2018: 0.02 2019: 0.02 Valid Range: min = 0.02 and max = 1 Out-of-Range Action: warn</p>
      <p><strong>ID_Miscellaneous_hc:</strong> This decimal fraction can be applied to limit the amount of miscellaneous expense deduction allowed.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 1.0 2019: 1.0 2020: 1.0 2021: 1.0 2022: 1.0 2023: 1.0 2024: 1.0 2025: 1.0 2026: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>ID_Miscellaneous_c:</strong> The amount of miscellaneous expense deduction is limited to this dollar amount.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2014: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2015: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2016: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2017: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2018: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2019: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <h4></h4>
      <p><strong>ID_StateLocalTax_hc:</strong> This decimal fraction reduces the state and local income and sales tax deduction.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>ID_StateLocalTax_crt:</strong> The total deduction for state and local taxes is capped at this fraction of AGI.</p>
      <p>Known Values: 2013: 9e+99 2014: 9e+99 2015: 9e+99 2016: 9e+99 2017: 9e+99 2018: 9e+99 2019: 9e+99 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>ID_StateLocalTax_c:</strong> The amount of state and local income and sales taxes deduction is limited to this dollar amount.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2014: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2015: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2016: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2017: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2018: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2019: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <h4>State And Local Taxes And Real Estate Taxes</h4>
      <p><strong>ID_AllTaxes_hc:</strong> This decimal fraction reduces all state and local taxes paid eligible to deduct in itemized deduction.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>ID_AllTaxes_c:</strong> The amount of state and local income, sales and real estate tax deductions is limited to this dollar amount.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2014: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2015: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2016: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2017: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2018: [10000.0, 10000.0, 5000.0, 10000.0, 10000.0] 2019: [10000.0, 10000.0, 5000.0, 10000.0, 10000.0] 2020: [10000.0, 10000.0, 5000.0, 10000.0, 10000.0] 2021: [10000.0, 10000.0, 5000.0, 10000.0, 10000.0] 2022: [10000.0, 10000.0, 5000.0, 10000.0, 10000.0] 2023: [10000.0, 10000.0, 5000.0, 10000.0, 10000.0] 2024: [10000.0, 10000.0, 5000.0, 10000.0, 10000.0] 2025: [10000.0, 10000.0, 5000.0, 10000.0, 10000.0] 2026: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <h4>State, Local, And Foreign Real Estate Taxes</h4>
      <p><strong>ID_RealEstate_hc:</strong> This decimal fraction reduces real estate taxes paid eligible to deduct in itemized deduction.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>ID_RealEstate_crt:</strong> The total deduction for all real estate taxes is capped at this fraction of AGI.</p>
      <p>Known Values: 2013: 9e+99 2014: 9e+99 2015: 9e+99 2016: 9e+99 2017: 9e+99 2018: 9e+99 2019: 9e+99 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>ID_RealEstate_c:</strong> The amount of real estate taxes deduction is limited to this dollar amount.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2014: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2015: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2016: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2017: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2018: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2019: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
    </div>
    <div id="cap-gains-and-dividends" class="param-section" style="display: none;">
      <h3>Capital Gains And Dividends</h3>
      <h4>AMT - Long Term Capital Gains And Qualified Dividends</h4>
      <p><strong>AMT_CG_rt1:</strong> Capital gain and qualified dividends (stacked on top of regular income) below threshold 1 are taxed at this rate.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>AMT_CG_brk1:</strong> The gains and dividends, stacked last, of AMT taxable income below this are taxed at AMT capital gain rate 1.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [36250.0, 72500.0, 36250.0, 48600.0, 72500.0] 2014: [36900.0, 73800.0, 36900.0, 49400.0, 73800.0] 2015: [37450.0, 74900.0, 37450.0, 50200.0, 74900.0] 2016: [37650.0, 75300.0, 37650.0, 50400.0, 75300.0] 2017: [37950.0, 75900.0, 37950.0, 50800.0, 75900.0] 2018: [38600.0, 77200.0, 38600.0, 51700.0, 77200.0] 2019: [39375.0, 78750.0, 39375.0, 52750.0, 78750.0] Valid Range: min = 0 and max = AMT_CG_brk2 Out-of-Range Action: error</p>
      <p><strong>AMT_CG_rt2:</strong> Capital gain and qualified dividend (stacked on top of regular income) below threshold 2 and above threshold 1 are taxed at this rate.</p>
      <p>Known Values: 2013: 0.15 2014: 0.15 2015: 0.15 2016: 0.15 2017: 0.15 2018: 0.15 2019: 0.15 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>AMT_CG_brk2:</strong> The gains and dividends, stacked last, of AMT taxable income below this threshold and above bracket 1 are taxed at AMT capital gain rate 2.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [400000.0, 450000.0, 225000.0, 425000.0, 450000.0] 2014: [406750.0, 457600.0, 228800.0, 432200.0, 457600.0] 2015: [413200.0, 464850.0, 232425.0, 439000.0, 464850.0] 2016: [415050.0, 466950.0, 233475.0, 441000.0, 466950.0] 2017: [418400.0, 470700.0, 235350.0, 444550.0, 470700.0] 2018: [425800.0, 479000.0, 239500.0, 452400.0, 479000.0] 2019: [434550.0, 488850.0, 244425.0, 461700.0, 488850.0] Valid Range: min = AMT_CG_brk1 and max = AMT_CG_brk3 Out-of-Range Action: error</p>
      <p><strong>AMT_CG_rt3:</strong> The capital gain and qualified dividend (stacked on top of regular income) above threshold 2 and below threshold 3 are taxed at this rate.</p>
      <p>Known Values: 2013: 0.2 2014: 0.2 2015: 0.2 2016: 0.2 2017: 0.2 2018: 0.2 2019: 0.2 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>AMT_CG_brk3:</strong> The gains and dividends, stacked last, of AMT taxable income below this and above bracket 2 are taxed at capital gain rate 3; above this they are taxed at AMT capital gain rate 4. Default value is essentially infinity.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2014: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2015: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2016: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2017: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2018: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2019: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] Valid Range: min = AMT_CG_brk2 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>AMT_CG_rt4:</strong> The capital gain and dividends (stacked on top of regular income) that are above threshold 3 are taxed at this rate.</p>
      <p>Known Values: 2013: 1.0 2014: 1.0 2015: 1.0 2016: 1.0 2017: 1.0 2018: 1.0 2019: 1.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <h4>Regular - Long Term Capital Gains And Qualified Dividends</h4>
      <p><strong>Capital_loss_limitation:</strong> The amount of capital loss deductions is limited to this dollar amount.</p>
      <p>Known Values: 2013: 3000.0 2014: 3000.0 2015: 3000.0 2016: 3000.0 2017: 3000.0 2018: 3000.0 2019: 3000.0 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>CG_rt1:</strong> The capital gain and dividends (stacked on top of regular income) that are below threshold 1 are taxed at this rate.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>CG_brk1:</strong> The gains and dividends (stacked on top of regular income) below this are taxed at capital gain rate 1.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [36250.0, 72500.0, 36250.0, 48600.0, 72500.0] 2014: [36900.0, 73800.0, 36900.0, 49400.0, 73800.0] 2015: [37450.0, 74900.0, 37450.0, 50200.0, 74900.0] 2016: [37650.0, 75300.0, 37650.0, 50400.0, 75300.0] 2017: [37950.0, 75900.0, 37950.0, 50800.0, 75900.0] 2018: [38600.0, 77200.0, 38600.0, 51700.0, 77200.0] 2019: [39375.0, 78750.0, 39375.0, 52750.0, 78750.0] Valid Range: min = 0 and max = CG_brk2 Out-of-Range Action: error</p>
      <p><strong>CG_rt2:</strong> The capital gain and dividends (stacked on top of regular income) that are below threshold 2 and above threshold 1 are taxed at this rate.</p>
      <p>Known Values: 2013: 0.15 2014: 0.15 2015: 0.15 2016: 0.15 2017: 0.15 2018: 0.15 2019: 0.15 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>CG_brk2:</strong> The gains and dividends (stacked on top of regular income) below this and above top of bracket 1 are taxed at capital gain rate 2.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [400000.0, 450000.0, 225000.0, 425000.0, 450000.0] 2014: [406750.0, 457600.0, 228800.0, 432200.0, 457600.0] 2015: [413200.0, 464850.0, 232425.0, 439000.0, 464850.0] 2016: [415050.0, 466950.0, 233475.0, 441000.0, 466950.0] 2017: [418400.0, 470700.0, 235350.0, 444550.0, 470700.0] 2018: [425800.0, 479000.0, 239500.0, 452400.0, 479000.0] 2019: [434550.0, 488850.0, 244425.0, 461700.0, 488850.0] Valid Range: min = CG_brk1 and max = CG_brk3 Out-of-Range Action: error</p>
      <p><strong>CG_rt3:</strong> The capital gain and dividends (stacked on top of regular income) that are above threshold 2 and below threshold 3 are taxed at this rate.</p>
      <p>Known Values: 2013: 0.2 2014: 0.2 2015: 0.2 2016: 0.2 2017: 0.2 2018: 0.2 2019: 0.2 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>CG_brk3:</strong> The gains and dividends (stacked on top of regular income) below this and above top of bracket 2 are taxed at the capital gain rate 3; above this they are taxed at capital gain rate 4. Default value is essentially infinity.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2014: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2015: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2016: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2017: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2018: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2019: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] Valid Range: min = CG_brk2 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>CG_rt4:</strong> The capital gain and dividends (stacked on top of regular income) that are above threshold 3 are taxed at this rate.</p>
      <p>Known Values: 2013: 1.0 2014: 1.0 2015: 1.0 2016: 1.0 2017: 1.0 2018: 1.0 2019: 1.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <h4>Tax All Capital Gains And Dividends The Same As Regular Taxable Income</h4>
      <p><strong>CG_nodiff:</strong> Specifies whether or not long term capital gains and qualified dividends are taxed like regular taxable income.</p>
      <p>Known Values: 2013: False 2014: False 2015: False 2016: False 2017: False 2018: False 2019: False Valid Range: min = False and max = True Out-of-Range Action: error</p>
      <p><strong>CG_ec:</strong> Positive value used only if long term capital gains and qualified dividends taxed no differently than regular taxable income.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>CG_reinvest_ec_rt:</strong> Positive value used only if long term capital gains and qualified dividends taxed no differently than regular taxable income. To limit the exclusion to capital gains and dividends invested within one year, set to statutory exclusion rate times the fraction of capital gains and qualified dividends in excess of the exclusion that are assumed to be reinvested within the year.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
    </div>
    <div id="personal-income" class="param-section" style="display: none;">
      <h3>Personal Income</h3>
      <h4>Alternative Minimum Tax</h4>
      <p><strong>AMT_em:</strong> The amount of AMT taxable income exempted from AMT.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [51900.0, 80800.0, 40400.0, 51900.0, 80800.0] 2014: [52800.0, 82100.0, 41050.0, 52800.0, 82100.0] 2015: [53600.0, 83400.0, 41700.0, 53600.0, 83400.0] 2016: [53900.0, 83800.0, 41900.0, 53900.0, 83800.0] 2017: [54300.0, 84500.0, 42250.0, 54300.0, 84500.0] 2018: [70300.0, 109400.0, 54700.0, 70300.0, 109400.0] 2019: [71700.0, 111700.0, 55850.0, 71700.0, 111700.0] 2020: [72804.18, 113420.18, 56710.09, 72804.18, 113420.18] 2021: [73335.65, 114248.15, 57124.07, 73335.65, 114248.15] 2022: [74032.34, 115333.51, 57666.75, 74032.34, 115333.51] 2023: [75202.05, 117155.78, 58577.88, 75202.05, 117155.78] 2024: [76653.45, 119416.89, 59708.43, 76653.45, 119416.89] 2025: [78186.52, 121805.23, 60902.6, 78186.52, 121805.23] 2026: [62898.0, 97880.0, 48940.0, 62898.0, 97880.0] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>AMT_prt:</strong> AMT exemption will decrease at this rate for each dollar of AMT taxable income exceeding AMT phaseout start.</p>
      <p>Known Values: 2013: 0.25 2014: 0.25 2015: 0.25 2016: 0.25 2017: 0.25 2018: 0.25 2019: 0.25 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>AMT_em_ps:</strong> AMT exemption starts to decrease when AMT taxable income goes beyond this threshold.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [115400.0, 153900.0, 76950.0, 115400.0, 153900.0] 2014: [117300.0, 156500.0, 78250.0, 117300.0, 156500.0] 2015: [119200.0, 158900.0, 79450.0, 119200.0, 158900.0] 2016: [119700.0, 159700.0, 79850.0, 119700.0, 159700.0] 2017: [120700.0, 160900.0, 80450.0, 120700.0, 160900.0] 2018: [500000.0, 1000000.0, 500000.0, 500000.0, 1000000.0] 2019: [510300.0, 1020600.0, 510300.0, 510300.0, 1020600.0] 2020: [518158.62, 1036317.24, 518158.62, 518158.62, 1036317.24] 2021: [521941.18, 1043882.36, 521941.18, 521941.18, 1043882.36] 2022: [526899.62, 1053799.24, 526899.62, 526899.62, 1053799.24] 2023: [535224.63, 1070449.27, 535224.63, 535224.63, 1070449.27] 2024: [545554.47, 1091108.94, 545554.47, 545554.47, 1091108.94] 2025: [556465.56, 1112931.12, 556465.56, 556465.56, 1112931.12] 2026: [139812.0, 186378.0, 93189.0, 139812.0, 186378.0] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>AMT_rt1:</strong> The tax rate applied to the portion of AMT taxable income below the surtax threshold, AMT bracket 1.</p>
      <p>Known Values: 2013: 0.26 2014: 0.26 2015: 0.26 2016: 0.26 2017: 0.26 2018: 0.26 2019: 0.26 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>AMT_brk1:</strong> AMT taxable income below this is subject to AMT rate 1 and above it is subject to AMT rate 1 + the additional AMT rate.</p>
      <p>Known Values: 2013: 179500.0 2014: 182500.0 2015: 185400.0 2016: 186300.0 2017: 187800.0 2018: 191100.0 2019: 194800.0 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>AMT_rt2:</strong> The additional tax rate applied to the portion of AMT income above the AMT bracket 1.</p>
      <p>Known Values: 2013: 0.02 2014: 0.02 2015: 0.02 2016: 0.02 2017: 0.02 2018: 0.02 2019: 0.02 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <h4>Pass-Through</h4>
      <p><strong>PT_qbid_rt:</strong> Fraction of pass-through business income that may be excluded from taxable income.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.2 2019: 0.2 2020: 0.2 2021: 0.2 2022: 0.2 2023: 0.2 2024: 0.2 2025: 0.2 2026: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>PT_qbid_taxinc_thd:</strong> Pre-QBID taxable income above this lower threshold implies the QBID amount begins to be limited.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [0.0, 0.0, 0.0, 0.0, 0.0] 2014: [0.0, 0.0, 0.0, 0.0, 0.0] 2015: [0.0, 0.0, 0.0, 0.0, 0.0] 2016: [0.0, 0.0, 0.0, 0.0, 0.0] 2017: [0.0, 0.0, 0.0, 0.0, 0.0] 2018: [157500.0, 315000.0, 157500.0, 157500.0, 315000.0] 2019: [160700.0, 321400.0, 160725.0, 160700.0, 321400.0] 2020: [163174.78, 326349.56, 163200.16, 163174.78, 326349.56] 2021: [164365.96, 328731.91, 164391.52, 164365.96, 328731.91] 2022: [165927.44, 331854.86, 165953.24, 165927.44, 331854.86] 2023: [168549.09, 337098.17, 168575.3, 168549.09, 337098.17] 2024: [171802.09, 343604.16, 171828.8, 171802.09, 343604.16] 2025: [175238.13, 350476.24, 175265.38, 175238.13, 350476.24] 2026: [0.0, 0.0, 0.0, 0.0, 0.0] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>PT_qbid_taxinc_gap:</strong> Pre-QBID taxable income above this upper threshold implies the QBID amount is even more limited.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [1.0, 1.0, 1.0, 1.0, 1.0] 2014: [1.0, 1.0, 1.0, 1.0, 1.0] 2015: [1.0, 1.0, 1.0, 1.0, 1.0] 2016: [1.0, 1.0, 1.0, 1.0, 1.0] 2017: [1.0, 1.0, 1.0, 1.0, 1.0] 2018: [50000.0, 100000.0, 50000.0, 50000.0, 100000.0] 2019: [50000.0, 100000.0, 50000.0, 50000.0, 100000.0] 2020: [50000.0, 100000.0, 50000.0, 50000.0, 100000.0] 2021: [50000.0, 100000.0, 50000.0, 50000.0, 100000.0] 2022: [50000.0, 100000.0, 50000.0, 50000.0, 100000.0] 2023: [50000.0, 100000.0, 50000.0, 50000.0, 100000.0] 2024: [50000.0, 100000.0, 50000.0, 50000.0, 100000.0] 2025: [50000.0, 100000.0, 50000.0, 50000.0, 100000.0] 2026: [1.0, 1.0, 1.0, 1.0, 1.0] Valid Range: min = 1 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>PT_qbid_w2_wages_rt:</strong> QBID is capped at this fraction of W-2 wages paid by the pass-through business if pre-QBID taxable income is above the QBID thresholds.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.5 2019: 0.5 2020: 0.5 2021: 0.5 2022: 0.5 2023: 0.5 2024: 0.5 2025: 0.5 2026: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>PT_qbid_alt_w2_wages_rt:</strong> QBID is capped at this fraction of W-2 wages paid by the pass-through business plus some fraction of business property if pre-QBID taxable income is above the QBID thresholds and the alternative cap is higher than the main wage-only cap.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.25 2019: 0.25 2020: 0.25 2021: 0.25 2022: 0.25 2023: 0.25 2024: 0.25 2025: 0.25 2026: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>PT_qbid_alt_property_rt:</strong> QBID is capped at this fraction of business property owned plus some fraction of W-2 wages paid by the pass-through business if pre-QBID taxable income is above the QBID thresholds and the alternative cap is higher than the main wage-only cap.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.025 2019: 0.025 2020: 0.025 2021: 0.025 2022: 0.025 2023: 0.025 2024: 0.025 2025: 0.025 2026: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>PT_qbid_ps:</strong> QBID begins to decrease when pre-QBID taxable income is above this level.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2014: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2015: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2016: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2017: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2018: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2019: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>PT_qbid_prt:</strong> QBID begins to decrease when pre-QBID taxable income is above this level.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2014: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2015: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2016: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2017: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2018: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2019: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>PT_qbid_prt:</strong> QBID will decrease at this rate for each dollar of taxable income exceeding QBID phaseout start.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <h4>Regular: Non-AMT</h4>
      <p><strong>II_rt1:</strong> The lowest tax rate, applied to the portion of taxable income below tax bracket 1.</p>
      <p>Known Values: 2013: 0.1 2014: 0.1 2015: 0.1 2016: 0.1 2017: 0.1 2018: 0.1 2019: 0.1 2020: 0.1 2021: 0.1 2022: 0.1 2023: 0.1 2024: 0.1 2025: 0.1 2026: 0.1 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>II_brk1:</strong> Taxable income below this threshold is taxed at tax rate 1.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [8925.0, 17850.0, 8925.0, 12750.0, 17850.0] 2014: [9075.0, 18150.0, 9075.0, 12950.0, 18150.0] 2015: [9225.0, 18450.0, 9225.0, 13150.0, 18450.0] 2016: [9275.0, 18550.0, 9275.0, 13250.0, 18550.0] 2017: [9325.0, 18650.0, 9325.0, 13350.0, 18650.0] 2018: [9525.0, 19050.0, 9525.0, 13600.0, 19050.0] 2019: [9700.0, 19400.0, 9700.0, 13850.0, 19400.0] 2020: [9849.38, 19698.76, 9849.38, 14063.29, 19698.76] 2021: [9921.28, 19842.56, 9921.28, 14165.95, 19842.56] 2022: [10015.53, 20031.06, 10015.53, 14300.53, 20031.06] 2023: [10173.78, 20347.55, 10173.78, 14526.48, 20347.55] 2024: [10370.13, 20740.26, 10370.13, 14806.84, 20740.26] 2025: [10577.53, 21155.07, 10577.53, 15102.98, 21155.07] 2026: [10802.0, 21603.0, 10802.0, 15464.0, 21603.0] Valid Range: min = 0 and max = II_brk2 Out-of-Range Action: error</p>
      <p><strong>II_rt2:</strong> The second lowest tax rate, applied to the portion of taxable income below tax bracket 2 and above tax bracket 1.</p>
      <p>Known Values: 2013: 0.15 2014: 0.15 2015: 0.15 2016: 0.15 2017: 0.15 2018: 0.12 2019: 0.12 2020: 0.12 2021: 0.12 2022: 0.12 2023: 0.12 2024: 0.12 2025: 0.12 2026: 0.15 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>II_brk2:</strong> Income below this threshold and above tax bracket 1 is taxed at tax rate 2.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [36250.0, 72500.0, 36250.0, 48600.0, 72500.0] 2014: [36900.0, 73800.0, 36900.0, 49400.0, 73800.0] 2015: [37450.0, 74900.0, 37450.0, 50200.0, 74900.0] 2016: [37650.0, 75300.0, 37650.0, 50400.0, 75300.0] 2017: [37950.0, 75900.0, 37950.0, 50800.0, 75900.0] 2018: [38700.0, 77400.0, 38700.0, 51800.0, 77400.0] 2019: [39475.0, 78950.0, 39475.0, 52850.0, 78950.0] 2020: [40082.92, 80165.83, 40082.92, 53663.89, 80165.83] 2021: [40375.53, 80751.04, 40375.53, 54055.64, 80751.04] 2022: [40759.1, 81518.17, 40759.1, 54569.17, 81518.17] 2023: [41403.09, 82806.16, 41403.09, 55431.36, 82806.16] 2024: [42202.17, 84404.32, 42202.17, 56501.19, 84404.32] 2025: [43046.21, 86092.41, 43046.21, 57631.21, 86092.41] 2026: [43959.0, 87918.0, 43959.0, 58844.0, 87918.0] Valid Range: min = II_brk1 and max = II_brk3 Out-of-Range Action: error</p>
      <p><strong>II_rt3:</strong> The third lowest tax rate, applied to the portion of taxable income below tax bracket 3 and above tax bracket 2.</p>
      <p>Known Values: 2013: 0.25 2014: 0.25 2015: 0.25 2016: 0.25 2017: 0.25 2018: 0.22 2019: 0.22 2020: 0.22 2021: 0.22 2022: 0.22 2023: 0.22 2024: 0.22 2025: 0.22 2026: 0.25 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>II_brk3:</strong> Income below this threshold and above tax bracket 2 is taxed at tax rate 3.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [87850.0, 146400.0, 73200.0, 125450.0, 146400.0] 2014: [89350.0, 148850.0, 74425.0, 127550.0, 148850.0] 2015: [90750.0, 151200.0, 75600.0, 129600.0, 151200.0] 2016: [91150.0, 151900.0, 75950.0, 130150.0, 151900.0] 2017: [91900.0, 153100.0, 76550.0, 131200.0, 153100.0] 2018: [82500.0, 165000.0, 82500.0, 82500.0, 165000.0] 2019: [84200.0, 168400.0, 84200.0, 84200.0, 168400.0] 2020: [85496.68, 170993.36, 85496.68, 85496.68, 170993.36] 2021: [86120.81, 172241.61, 86120.81, 86120.81, 172241.61] 2022: [86938.96, 173877.91, 86938.96, 86938.96, 173877.91] 2023: [88312.6, 176625.18, 88312.6, 88312.6, 176625.18] 2024: [90017.03, 180034.05, 90017.03, 90017.03, 180034.05] 2025: [91817.37, 183634.73, 91817.37, 91817.37, 183634.73] 2026: [106452.0, 177343.0, 88671.0, 151975.0, 177343.0] Valid Range: min = II_brk2 and max = II_brk4 Out-of-Range Action: error</p>
      <p><strong>II_rt4:</strong> The tax rate applied to the portion of taxable income below tax bracket 4 and above tax bracket 3.</p>
      <p>Known Values: 2013: 0.28 2014: 0.28 2015: 0.28 2016: 0.28 2017: 0.28 2018: 0.24 2019: 0.24 2020: 0.24 2021: 0.24 2022: 0.24 2023: 0.24 2024: 0.24 2025: 0.24 2026: 0.28 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>II_brk4:</strong> Income below this threshold and above tax bracket 3 is taxed at tax rate 4.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [183250.0, 223050.0, 111525.0, 203150.0, 223050.0] 2014: [186350.0, 226850.0, 113425.0, 206600.0, 226850.0] 2015: [189300.0, 230450.0, 115225.0, 209850.0, 230450.0] 2016: [190150.0, 231450.0, 115725.0, 210800.0, 231450.0] 2017: [191650.0, 233350.0, 116675.0, 212500.0, 233350.0] 2018: [157500.0, 315000.0, 157500.0, 157500.0, 315000.0] 2019: [160725.0, 321450.0, 160725.0, 160700.0, 321450.0] 2020: [163200.16, 326400.33, 163200.16, 163174.78, 326400.33] 2021: [164391.52, 328783.05, 164391.52, 164365.96, 328783.05] 2022: [165953.24, 331906.49, 165953.24, 165927.44, 331906.49] 2023: [168575.3, 337150.61, 168575.3, 168549.09, 337150.61] 2024: [171828.8, 343657.62, 171828.8, 171802.09, 343657.62] 2025: [175265.38, 350530.77, 175265.38, 175238.13, 350530.77] 2026: [221997.0, 270300.0, 135150.0, 246148.0, 270300.0] Valid Range: min = II_brk3 and max = II_brk5 Out-of-Range Action: error</p>
      <p><strong>II_rt5:</strong> The third highest tax rate, applied to the portion of taxable income below tax bracket 5 and above tax bracket 4.</p>
      <p>Known Values: 2013: 0.33 2014: 0.33 2015: 0.33 2016: 0.33 2017: 0.33 2018: 0.32 2019: 0.32 2020: 0.32 2021: 0.32 2022: 0.32 2023: 0.32 2024: 0.32 2025: 0.32 2026: 0.33 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>II_brk5:</strong> Income below this threshold and above tax bracket 4 is taxed at tax rate 5.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [398350.0, 398350.0, 199175.0, 398350.0, 398350.0] 2014: [405100.0, 405100.0, 202550.0, 405100.0, 405100.0] 2015: [411500.0, 411500.0, 205750.0, 411500.0, 411500.0] 2016: [413350.0, 413350.0, 206675.0, 413350.0, 413350.0] 2017: [416700.0, 416700.0, 208350.0, 416700.0, 416700.0] 2018: [200000.0, 400000.0, 200000.0, 200000.0, 400000.0] 2019: [204100.0, 408200.0, 204100.0, 204100.0, 408200.0] 2020: [207243.14, 414486.28, 207243.14, 207243.14, 414486.28] 2021: [208756.01, 417512.03, 208756.01, 208756.01, 417512.03] 2022: [210739.19, 421478.39, 210739.19, 210739.19, 421478.39] 2023: [214068.87, 428137.75, 214068.87, 214068.87, 428137.75] 2024: [218200.4, 436400.81, 218200.4, 218200.4, 436400.81] 2025: [222564.41, 445128.83, 222564.41, 222564.41, 445128.83] 2026: [482682.0, 482682.0, 241341.0, 482682.0, 482682.0] Valid Range: min = II_brk4 and max = II_brk6 Out-of-Range Action: error</p>
      <p><strong>II_rt6:</strong> The second higher tax rate, applied to the portion of taxable income below tax bracket 6 and above tax bracket 5.</p>
      <p>Known Values: 2013: 0.35 2014: 0.35 2015: 0.35 2016: 0.35 2017: 0.35 2018: 0.35 2019: 0.35 2020: 0.35 2021: 0.35 2022: 0.35 2023: 0.35 2024: 0.35 2025: 0.35 2026: 0.35 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>II_brk6:</strong> Income below this threshold and above tax bracket 5 is taxed at tax rate 6.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [400000.0, 450000.0, 225000.0, 425000.0, 450000.0] 2014: [406750.0, 457600.0, 228800.0, 432200.0, 457600.0] 2015: [413200.0, 464850.0, 232425.0, 439000.0, 464850.0] 2016: [415050.0, 466950.0, 233475.0, 441000.0, 466950.0] 2017: [418400.0, 470700.0, 235350.0, 444550.0, 470700.0] 2018: [500000.0, 600000.0, 300000.0, 500000.0, 600000.0] 2019: [510300.0, 612350.0, 306175.0, 510300.0, 612350.0] 2020: [518158.62, 621780.19, 310890.1, 518158.62, 621780.19] 2021: [521941.18, 626319.19, 313159.6, 521941.18, 626319.19] 2022: [526899.62, 632269.22, 316134.62, 526899.62, 632269.22] 2023: [535224.63, 642259.07, 321129.55, 535224.63, 642259.07] 2024: [545554.47, 654654.67, 327327.35, 545554.47, 654654.67] 2025: [556465.56, 667747.76, 333873.9, 556465.56, 667747.76] 2026: [484651.0, 545233.0, 272616.0, 514942.0, 545233.0] Valid Range: min = II_brk5 and max = II_brk7 Out-of-Range Action: error</p>
      <p>II_rt7<strong>:</strong> The tax rate applied to the portion of taxable income below tax bracket 7 and above tax bracket 6.</p>
      <p>Known Values: 2013: 0.396 2014: 0.396 2015: 0.396 2016: 0.396 2017: 0.396 2018: 0.37 2019: 0.37 2020: 0.37 2021: 0.37 2022: 0.37 2023: 0.37 2024: 0.37 2025: 0.37 2026: 0.396 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>II_brk7:</strong> Income below this threshold and above tax bracket 6 is taxed at tax rate 7; income above this threshold is taxed at tax rate 8. Default value is essentially infinity.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2014: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2015: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2016: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2017: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2018: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2019: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] Valid Range: min = II_brk6 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>II_rt8:</strong> The tax rate applied to the portion of taxable income above tax bracket 7.</p>
      <p>Known Values: 2013: 1.0 2014: 1.0 2015: 1.0 2016: 1.0 2017: 1.0 2018: 1.0 2019: 1.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
    </div>
    <div id="other-tax" class="param-section" style="display: none;">
      <h3>Other Taxes</h3>
      <h4>Net Investment Income Tax</h4>
      <p><strong>NIIT_thd:</strong> If modified AGI is more than this threshold, filing unit is subject to the Net Investment Income Tax.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [200000.0, 250000.0, 125000.0, 200000.0, 250000.0] 2014: [200000.0, 250000.0, 125000.0, 200000.0, 250000.0] 2015: [200000.0, 250000.0, 125000.0, 200000.0, 250000.0] 2016: [200000.0, 250000.0, 125000.0, 200000.0, 250000.0] 2017: [200000.0, 250000.0, 125000.0, 200000.0, 250000.0] 2018: [200000.0, 250000.0, 125000.0, 200000.0, 250000.0] 2019: [200000.0, 250000.0, 125000.0, 200000.0, 250000.0] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>NIIT_PT_taxed:</strong> Description: false ==> partnership and S-corp income excluded from NIIT base; true ==> partnership and S-corp income is in NIIT base.</p>
      <p>Known Values: 2013: False 2014: False 2015: False 2016: False 2017: False 2018: False 2019: False Valid Range: min = False and max = True Out-of-Range Action: error</p>
      <p><strong>NIIT_rt:</strong> If modified AGI exceeds NIIT_thd, all net investment income is taxed at this rate.</p>
      <p>Known Values: 2013: 0.038 2014: 0.038 2015: 0.038 2016: 0.038 2017: 0.038 2018: 0.038 2019: 0.038 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
    </div>
    <div id="refund-credits" class="param-section" style="display: none;">
      <h3>Refundable Credits</h3>
      <h4>Earned Income Tax Credit</h4>
      <p><strong>EITC_c:</strong> This is the maximum amount of earned income credit taxpayers are eligible for; it depends on how many kids they have.</p>
      <p>Known Values: for: [0kids, 1kid, 2kids, 3+kids] 2013: [487.0, 3250.0, 5372.0, 6044.0] 2014: [496.0, 3305.0, 5460.0, 6143.0] 2015: [503.0, 3359.0, 5548.0, 6242.0] 2016: [506.0, 3373.0, 5572.0, 6269.0] 2017: [510.0, 3400.0, 5616.0, 6318.0] 2018: [519.0, 3461.0, 5716.0, 6431.0] 2019: [529.0, 3526.0, 5828.0, 6557.0] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>EITC_rt:</strong> Pre-phaseout credit is minimum of this rate times earnings and the maximum earned income credit.</p>
      <p>Known Values: for: [0kids, 1kid, 2kids, 3+kids] 2013: [0.0765, 0.34, 0.4, 0.45] 2014: [0.0765, 0.34, 0.4, 0.45] 2015: [0.0765, 0.34, 0.4, 0.45] 2016: [0.0765, 0.34, 0.4, 0.45] 2017: [0.0765, 0.34, 0.4, 0.45] 2018: [0.0765, 0.34, 0.4, 0.45] 2019: [0.0765, 0.34, 0.4, 0.45] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>EITC_basic_frac:</strong> This fraction of EITC_c is always paid as a credit and one minus this fraction is applied to the phasein rate, EITC_rt. This fraction is zero under current law.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0.0 and max = 1.0 Out-of-Range Action: error</p>
      <p><strong>EITC_prt:</strong> Earned income credit begins to decrease at the this rate when AGI is higher than earned income credit phaseout start AGI.</p>
      <p>Known Values: for: [0kids, 1kid, 2kids, 3+kids] 2013: [0.0765, 0.1598, 0.2106, 0.2106] 2014: [0.0765, 0.1598, 0.2106, 0.2106] 2015: [0.0765, 0.1598, 0.2106, 0.2106] 2016: [0.0765, 0.1598, 0.2106, 0.2106] 2017: [0.0765, 0.1598, 0.2106, 0.2106] 2018: [0.0765, 0.1598, 0.2106, 0.2106] 2019: [0.0765, 0.1598, 0.2106, 0.2106] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>EITC_ps:</strong> If AGI is higher than this threshold, the amount of EITC will start to decrease at the phaseout rate.</p>
      <p>Known Values: for: [0kids, 1kid, 2kids, 3+kids] 2013: [7970.0, 17530.0, 17530.0, 17530.0] 2014: [8110.0, 17830.0, 17830.0, 17830.0] 2015: [8250.0, 18150.0, 18150.0, 18150.0] 2016: [8270.0, 18190.0, 18190.0, 18190.0] 2017: [8340.0, 18340.0, 18340.0, 18340.0] 2018: [8490.0, 18660.0, 18660.0, 18660.0] 2019: [8650.0, 19030.0, 19030.0, 19030.0] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>EITC_ps_MarriedJ:</strong> This is the additional amount added on the regular phaseout start amount for taxpayers with filling status of married filing jointly.</p>
      <p>Known Values: for: [0kids, 1kid, 2kids, 3+kids] 2013: [5340.0, 5340.0, 5340.0, 5340.0] 2014: [5430.0, 5430.0, 5430.0, 5430.0] 2015: [5500.0, 5500.0, 5500.0, 5500.0] 2016: [5550.0, 5550.0, 5550.0, 5550.0] 2017: [5590.0, 5590.0, 5590.0, 5590.0] 2018: [5680.0, 5690.0, 5690.0, 5690.0] 2019: [5800.0, 5790.0, 5790.0, 5790.0] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>EITC_MinEligAge:</strong> For a childless filing unit, at least one individual’s age needs to be no less than this age (but no greater than the EITC_MaxEligAge) in order to be eligible for an earned income tax credit.</p>
      <p>Known Values: 2013: 25 2014: 25 2015: 25 2016: 25 2017: 25 2018: 25 2019: 25 Valid Range: min = 0 and max = 125 Out-of-Range Action: error</p>
      <p><strong>EITC_MaxEligAge:</strong> For a childless filing unit, at least one individual’s age needs to be no greater than this age (but no less than the EITC_MinEligAge) in order to be eligible for an earned income tax credit.</p>
      <p>Known Values: 2013: 64 2014: 64 2015: 64 2016: 64 2017: 64 2018: 64 2019: 64 Valid Range: min = 0 and max = 125 Out-of-Range Action: error</p>
      <p><strong>EITC_InvestIncome_c:</strong> The EITC amount is reduced when investment income exceeds this ceiling.</p>
      <p>Known Values: 2013: 3300.0 2014: 3350.0 2015: 3400.0 2016: 3400.0 2017: 3450.0 2018: 3500.0 2019: 3600.0 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>EITC_excess_InvestIncome_rt:</strong> The EITC amount is reduced at this rate per dollar of investment income exceeding the ceiling.</p>
      <p>Known Values: 2013: 9e+99 2014: 9e+99 2015: 9e+99 2016: 9e+99 2017: 9e+99 2018: 9e+99 2019: 9e+99 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>EITC_indiv:</strong> Current-law value is false implying EITC is filing-unit based; a value of true implies EITC is computed for each individual wage earner. The additional phaseout start for joint filers is not affected by this parameter, nor are investment income and age eligibilty rules.</p>
      <p>Known Values: 2013: False 2014: False 2015: False 2016: False 2017: False 2018: False 2019: False Valid Range: min = False and max = True Out-of-Range Action: error</p>
      <p><strong>EITC_sep_filers_elig:</strong> Current-law value is false, implying ineligibility.</p>
      <p>Known Values: 2013: False 2014: False 2015: False 2016: False 2017: False 2018: False 2019: False Valid Range: min = False and max = True Out-of-Range Action: error</p>
      <h4>New Refundable Child Tax Credit</h4>
      <p><strong>CTC_new_c:</strong> In addition to all credits currently available for dependents, this parameter gives each qualifying child a new refundable credit with this maximum amount.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>CTC_new_c_under6_bonus:</strong> The maximum amount of the new refundable child tax credit allowed for each child is increased by this amount for qualifying children under 6 years old.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>CTC_new_for_all:</strong> The maximum amount of the new refundable child tax credit does not depend on AGI when true; otherwise, see CTC_new_rt.</p>
      <p>Known Values: 2013: False 2014: False 2015: False 2016: False 2017: False 2018: False 2019: False Valid Range: min = False and max = True Out-of-Range Action: error</p>
      <p><strong>CTC_new_rt:</strong> The maximum amount of the new child tax credit is increased at this rate per dollar of positive AGI until CTC_new_c times the number of qualified children is reached if CTC_new_for_all is false; if CTC_new_for_all is true, there is no AGI limitation to the maximum amount</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>CTC_new_ps:</strong> The total amount of new child tax credit is reduced for taxpayers with AGI higher than this level.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [0.0, 0.0, 0.0, 0.0, 0.0] 2014: [0.0, 0.0, 0.0, 0.0, 0.0] 2015: [0.0, 0.0, 0.0, 0.0, 0.0] 2016: [0.0, 0.0, 0.0, 0.0, 0.0] 2017: [0.0, 0.0, 0.0, 0.0, 0.0] 2018: [0.0, 0.0, 0.0, 0.0, 0.0] 2019: [0.0, 0.0, 0.0, 0.0, 0.0] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>CTC_new_prt:</strong> The total amount of the new child tax credit is reduced at this rate per dollar exceeding the phaseout starting AGI, CTC_new_ps.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>CTC_new_refund_limited:</strong> Specifies whether the new child tax credit refund is limited by the new child tax credit refund limit rate (_CTC_new_refund_limit_payroll_rt).</p>
      <p>Known Values: 2013: False 2014: False 2015: False 2016: False 2017: False 2018: False 2019: False Valid Range: min = False and max = True Out-of-Range Action: error</p>
      <p><strong>CTC_new_refund_limit_payroll_rt:</strong> The fraction of payroll taxes (employee plus employer shares, but excluding all Medicare payroll taxes) that serves as a limit to the amount of new child tax credit that can be refunded.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>CTC_new_refund_limited_all_payroll:</strong> Specifies whether the new child tax credit refund limit rate (_CTC_new_refund_limit_payroll_rt) applies to all FICA taxes (true) or just OASDI taxes (false).</p>
      <p>Known Values: 2013: False 2014: False 2015: False 2016: False 2017: False 2018: False 2019: False Valid Range: min = False and max = True Out-of-Range Action: error</p>
      <h4>Personal Refundable Credit</h4>
      <p><strong>II_credit:</strong> This credit amount is fully refundable and is phased out based on AGI. It is available to tax units who would otherwise not file.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [0.0, 0.0, 0.0, 0.0, 0.0] 2014: [0.0, 0.0, 0.0, 0.0, 0.0] 2015: [0.0, 0.0, 0.0, 0.0, 0.0] 2016: [0.0, 0.0, 0.0, 0.0, 0.0] 2017: [0.0, 0.0, 0.0, 0.0, 0.0] 2018: [0.0, 0.0, 0.0, 0.0, 0.0] 2019: [0.0, 0.0, 0.0, 0.0, 0.0] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>II_credit_ps:</strong> The personal refundable credit amount will be reduced for taxpayers with AGI higher than this threshold level.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [0.0, 0.0, 0.0, 0.0, 0.0] 2014: [0.0, 0.0, 0.0, 0.0, 0.0] 2015: [0.0, 0.0, 0.0, 0.0, 0.0] 2016: [0.0, 0.0, 0.0, 0.0, 0.0] 2017: [0.0, 0.0, 0.0, 0.0, 0.0] 2018: [0.0, 0.0, 0.0, 0.0, 0.0] 2019: [0.0, 0.0, 0.0, 0.0, 0.0] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>II_credit_prt:</strong> The personal refundable credit amount will be reduced at this rate for each dollar of AGI exceeding the II_credit_ps threshold.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>RRC_c:</strong> This credit amount is fully refundable and is phased out based on AGI. It is available for each person in the filing unit, except for dependent filers.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>RRC_ps:</strong> The Recovery Rebate Credit amount will be reduced for taxpayers with AGI higher than this threshold level.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [0.0, 0.0, 0.0, 0.0, 0.0] 2014: [0.0, 0.0, 0.0, 0.0, 0.0] 2015: [0.0, 0.0, 0.0, 0.0, 0.0] 2016: [0.0, 0.0, 0.0, 0.0, 0.0] 2017: [0.0, 0.0, 0.0, 0.0, 0.0] 2018: [0.0, 0.0, 0.0, 0.0, 0.0] 2019: [0.0, 0.0, 0.0, 0.0, 0.0] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>RRC_pe:</strong> The Recovery Rebate Credit amount will be fully phased out for taxpayers with AGI higher than this threshold level.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [0.0, 0.0, 0.0, 0.0, 0.0] 2014: [0.0, 0.0, 0.0, 0.0, 0.0] 2015: [0.0, 0.0, 0.0, 0.0, 0.0] 2016: [0.0, 0.0, 0.0, 0.0, 0.0] 2017: [0.0, 0.0, 0.0, 0.0, 0.0] 2018: [0.0, 0.0, 0.0, 0.0, 0.0] 2019: [0.0, 0.0, 0.0, 0.0, 0.0] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>RRC_prt:</strong> The Recovery Rebate Credit will be phased out at this rate for those with income above the phase out start and below the phase out end.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0.0 and max = 1.0 Out-of-Range Action: warn</p>
      <p><strong>RRC_c_unit:</strong> The maximum credit awarded as part of the Recovery Rebate Credit.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [0.0, 0.0, 0.0, 0.0, 0.0] 2014: [0.0, 0.0, 0.0, 0.0, 0.0] 2015: [0.0, 0.0, 0.0, 0.0, 0.0] 2016: [0.0, 0.0, 0.0, 0.0, 0.0] 2017: [0.0, 0.0, 0.0, 0.0, 0.0] 2018: [0.0, 0.0, 0.0, 0.0, 0.0] 2019: [0.0, 0.0, 0.0, 0.0, 0.0] Valid Range: min = 0.0 and max = 9e+99 Out-of-Range Action: warn</p>
      <p><strong>RRC_c_kids:</strong> The credit awarded for each child in an eligible family as part of the Recovery Rebate Credit.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0.0 and max = 9e+99 Out-of-Range Action: warn</p>
      <h4>Refundable Payroll Tax Credit</h4>
      <p><strong>RPTC_c:</strong> This is the maximum amount of the refundable payroll tax credit for each taxpayer/spouse.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>RPTC_rt:</strong> Pre-phaseout credit is minimum of this rate times earnings and the maximum refundable payroll tax credit, where earnings is defined as in FICA and SECA.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
    </div>
    <div id="surtaxes" class="param-section" style="display: none;">
      <h3>Surtaxes</h3>
      <h4>Lump-Sum Tax</h4>
      <p><strong>LST:</strong> The lump-sum tax is levied on every member of a tax filing unit. The lump-sum tax is included only in combined taxes; it is not included in income or payroll taxes.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = -9e+99 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>New AGI Surtax:</strong> AGI_surtax_trt</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>AGI_surtax_thd:</strong> The aggregate gross income above this AGI surtax threshold is taxed at surtax rate on AGI.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2014: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2015: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2016: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2017: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2018: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2019: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <h4>New Minimum Tax</h4>
      <p><strong>FST_AGI_trt:</strong> Individual income taxes and the employee share of payroll taxes are credited against this minimum tax, so the surtax is the difference between the tax rate times AGI and the credited taxes. The new minimum tax is similar to the Fair Share Tax, except that no credits are exempted from the base.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>FST_AGI_thd_lo:</strong> A taxpayer is only subject to the new minimum tax if they exceed this level of AGI.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [1000000.0, 1000000.0, 500000.0, 1000000.0, 1000000.0] 2014: [1000000.0, 1000000.0, 500000.0, 1000000.0, 1000000.0] 2015: [1000000.0, 1000000.0, 500000.0, 1000000.0, 1000000.0] 2016: [1000000.0, 1000000.0, 500000.0, 1000000.0, 1000000.0] 2017: [1000000.0, 1000000.0, 500000.0, 1000000.0, 1000000.0] 2018: [1000000.0, 1000000.0, 500000.0, 1000000.0, 1000000.0] 2019: [1000000.0, 1000000.0, 500000.0, 1000000.0, 1000000.0] Valid Range: min = 0 and max = FST_AGI_thd_hi Out-of-Range Action: error</p>
      <p><strong>FST_AGI_thd_hi:</strong> The new minimum tax will be fully phased in at this level of AGI. If there is no phase-in, this upper threshold should be set equal to the lower AGI threshold.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [2000000.0, 2000000.0, 1000000.0, 2000000.0, 2000000.0] 2014: [2000000.0, 2000000.0, 1000000.0, 2000000.0, 2000000.0] 2015: [2000000.0, 2000000.0, 1000000.0, 2000000.0, 2000000.0] 2016: [2000000.0, 2000000.0, 1000000.0, 2000000.0, 2000000.0] 2017: [2000000.0, 2000000.0, 1000000.0, 2000000.0, 2000000.0] 2018: [2000000.0, 2000000.0, 1000000.0, 2000000.0, 2000000.0] 2019: [2000000.0, 2000000.0, 1000000.0, 2000000.0, 2000000.0] Valid Range: min = FST_AGI_thd_lo and max = 9e+99 Out-of-Range Action: error</p>
    </div>
    <div id="ubi" class="param-section" style="display: none;">
      <h3>Universal Basic Income</h3>
      <h4>UBI Benefits</h4>
      <p><strong>UBI_u18:</strong> UBI benefit provided to people under 18.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>UBI_1820:</strong> UBI benefit provided to people 18-20 years of age.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>UBI_21:</strong> UBI benefit provided to people 21 and over.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <h4>UBI Taxability</h4>
      <p><strong>UBI_ecrt:</strong> One minus this fraction of UBI benefits are taxable and will be added to AGI.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
    </div>
    <div id="benefits" class="param-section" style="display: none;">
      <h3>Benefits</h3>
      <h4>Benefit Repeal</h4>
      <p><strong>BEN_ssi_repeal:</strong> SSI benefits can be repealed by switching this parameter to true.</p>
      <p>Known Values: 2013: False 2014: False 2015: False 2016: False 2017: False 2018: False 2019: False Valid Range: min = False and max = True Out-of-Range Action: error</p>
      <p><strong>BEN_housing_repeal:</strong> Housing benefits can be repealed by switching this parameter to true.</p>
      <p>Known Values: 2013: False 2014: False 2015: False 2016: False 2017: False 2018: False 2019: False Valid Range: min = False and max = True Out-of-Range Action: error</p>
      <p><strong>BEN_snap_repeal:</strong> SNAP benefits can be repealed by switching this parameter to true.</p>
      <p>Known Values: 2013: False 2014: False 2015: False 2016: False 2017: False 2018: False 2019: False Valid Range: min = False and max = True Out-of-Range Action: error</p>
      <p><strong>BEN_tanf_repeal:</strong> TANF benefits can be repealed by switching this parameter to true.</p>
      <p>Known Values: 2013: False 2014: False 2015: False 2016: False 2017: False 2018: False 2019: False Valid Range: min = False and max = True Out-of-Range Action: error</p>
      <p><strong>BEN_vet_repeal:</strong> Veterans benefits can be repealed by switching this parameter to true.</p>
      <p>Known Values: 2013: False 2014: False 2015: False 2016: False 2017: False 2018: False 2019: False Valid Range: min = False and max = True Out-of-Range Action: error</p>
      <p><strong>BEN_wic_repeal:</strong> WIC benefits can be repealed by switching this parameter to true.</p>
      <p>Known Values: 2013: False 2014: False 2015: False 2016: False 2017: False 2018: False 2019: False Valid Range: min = False and max = True Out-of-Range Action: error</p>
      <p><strong>BEN_mcare_repeal:</strong> Medicare benefits can be repealed by switching this parameter to true.</p>
      <p>Known Values: 2013: False 2014: False 2015: False 2016: False 2017: False 2018: False 2019: False Valid Range: min = False and max = True Out-of-Range Action: error</p>
      <p><strong>BEN_mcaid_repeal:</strong> Medicaid benefits can be repealed by switching this parameter to true.</p>
      <p>Known Values: 2013: False 2014: False 2015: False 2016: False 2017: False 2018: False 2019: False Valid Range: min = False and max = True Out-of-Range Action: error</p>
      <p><strong>BEN_oasdi_repeal:</strong> Social Security benefits (e02400) can be repealed by switching this parameter to true.</p>
      <p>Known Values: 2013: False 2014: False 2015: False 2016: False 2017: False 2018: False 2019: False Valid Range: min = False and max = True Out-of-Range Action: error</p>
      <p><strong>BEN_ui_repeal:</strong> Unemployment insurance benefits (e02300) can be repealed by switching this parameter to true.</p>
      <p>Known Values: 2013: False 2014: False 2015: False 2016: False 2017: False 2018: False 2019: False Valid Range: min = False and max = True Out-of-Range Action: error</p>
      <p><strong>BEN_other_repeal:</strong> Other benefits can be repealed by switching this parameter to true.</p>
      <p>Known Values: 2013: False 2014: False 2015: False 2016: False 2017: False 2018: False 2019: False Valid Range: min = False and max = True Out-of-Range Action: error</p>
    </div>
    <div id="other" class="param-section" style="display: none;">
      <h3>Other Parameters</h3>
      <p><strong>II_em_ps:</strong> If taxpayers’ AGI is above this level, their personal exemption will start to decrease at the personal exemption phaseout rate (PEP provision).</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [250000.0, 300000.0, 150000.0, 275000.0, 300000.0] 2014: [254200.0, 305050.0, 152525.0, 279650.0, 305050.0] 2015: [258250.0, 309900.0, 154950.0, 284040.0, 309900.0] 2016: [259400.0, 311300.0, 155650.0, 285350.0, 311300.0] 2017: [261500.0, 313800.0, 156900.0, 287650.0, 313800.0] 2018: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] 2019: [9e+99, 9e+99, 9e+99, 9e+99, 9e+99] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>STD_Dep:</strong> This is the maximum standard deduction for dependents.</p>
      <p>Known Values: 2013: 1000.0 2014: 1000.0 2015: 1050.0 2016: 1050.0 2017: 1050.0 2018: 1050.0 2019: 1100.0 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>STD_allow_charity_ded_nonitemizers:</strong> Extends the charitable contributions deduction to taxpayers who take the standard deduction. The same ceilings, floor, and haircuts applied to itemized deduction for charitable contributions also apply here as well as a max on the dollar amount for total charitable deductions for those taking the standard deduction.</p>
      <p>Known Values: 2013: False 2014: False 2015: False 2016: False 2017: False 2018: False 2019: False Valid Range: min = False and max = True Out-of-Range Action: error</p>
      <p><strong>STD_charity_ded_nonitemizers_max:</strong> Puts a ceiling on the dollar of amount of charitable contributions deductions for taxpayers who take the standard deduction.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0.0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>UI_em:</strong> The amount of Unemployment Insurance benefits excluded from taxable income.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>UI_thd:</strong> Unemployment Insurance exemption is eliminated when AGI minus Unemployment Insurance goes beyond this threshold.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [0.0, 0.0, 0.0, 0.0, 0.0] 2014: [0.0, 0.0, 0.0, 0.0, 0.0] 2015: [0.0, 0.0, 0.0, 0.0, 0.0] 2016: [0.0, 0.0, 0.0, 0.0, 0.0] 2017: [0.0, 0.0, 0.0, 0.0, 0.0] 2018: [0.0, 0.0, 0.0, 0.0, 0.0] 2019: [0.0, 0.0, 0.0, 0.0, 0.0] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>AMT_child_em:</strong> The child’s AMT exemption is capped by this amount plus the child’s earned income.</p>
      <p>Known Values: 2013: 7150.0 2014: 7250.0 2015: 7400.0 2016: 7400.0 2017: 7500.0 2018: 7600.0 2019: 0.0 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>AMT_child_em_c_age:</strong> Individuals under this age must use the child AMT exemption rules.</p>
      <p>Known Values: 2013: 18 2014: 18 2015: 18 2016: 18 2017: 18 2018: 18 2019: 18 Valid Range: min = 0 and max = 30 Out-of-Range Action: error</p>
      <p><strong>AMT_em_pe:</strong> The AMT exemption is entirely disallowed beyond this AMT taxable income level for individuals who are married but filing separately.</p>
      <p>Known Values: 2013: 238550.0 2014: 242450.0 2015: 246250.0 2016: 247450.0 2017: 249450.0 2018: 718800.0 2019: 733700.0 2020: 744998.98 2021: 750437.47 2022: 757566.63 2023: 769536.18 2024: 784388.23 2025: 800075.99 2026: 288949.0 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>LLC_Expense_c:</strong> The maximum expense eligible for lifetime learning credit, per child.</p>
      <p>Known Values: 2013: 10000.0 2014: 10000.0 2015: 10000.0 2016: 10000.0 2017: 10000.0 2018: 10000.0 2019: 10000.0 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>ETC_pe_Single:</strong> The education tax credit will be zero for those taxpayers of single filing status with modified AGI (in thousands) higher than this level.</p>
      <p>Known Values: 2013: 63.0 2014: 64.0 2015: 65.0 2016: 65.0 2017: 66.0 2018: 67.0 2019: 68.0 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>ETC_pe_Married:</strong> The education tax credit will be zero for those taxpayers of married filing status with modified AGI level (in thousands) higher than this level.</p>
      <p>Known Values: 2013: 127.0 2014: 128.0 2015: 130.0 2016: 131.0 2017: 132.0 2018: 134.0 2019: 136.0 Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>CR_Charity_rt:</strong> If greater than zero, this decimal fraction represents the portion of total charitable contributions provided as a nonrefundable tax credit.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
      <p><strong>CR_Charity_f:</strong> Only charitable giving in excess of this dollar amount is eligible for the charity credit.</p>
      <p>Known Values: for: [single, mjoint, mseparate, headhh, widow] 2013: [0.0, 0.0, 0.0, 0.0, 0.0] 2014: [0.0, 0.0, 0.0, 0.0, 0.0] 2015: [0.0, 0.0, 0.0, 0.0, 0.0] 2016: [0.0, 0.0, 0.0, 0.0, 0.0] 2017: [0.0, 0.0, 0.0, 0.0, 0.0] 2018: [0.0, 0.0, 0.0, 0.0, 0.0] 2019: [0.0, 0.0, 0.0, 0.0, 0.0] Valid Range: min = 0 and max = 9e+99 Out-of-Range Action: error</p>
      <p><strong>CR_Charity_frt:</strong> Only charitable giving in excess of this decimal fraction of AGI is eligible for the charity credit.</p>
      <p>Known Values: 2013: 0.0 2014: 0.0 2015: 0.0 2016: 0.0 2017: 0.0 2018: 0.0 2019: 0.0 Valid Range: min = 0 and max = 1 Out-of-Range Action: error</p>
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
