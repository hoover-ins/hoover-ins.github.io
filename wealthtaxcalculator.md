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

<img src="{{ site.baseurl }}/assets/tstarformula.jpg" alt="t-star Formula" style="max-width: 100%; height: auto; display: block; margin: 0 auto;">

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

<p><strong>Wealth Tax Rate (θ) - Expropriation Risk:</strong> A wealth tax of 1% should be entered as 1. Acceptable range of values is between 0 and 100 (0-100%).</p>

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
      <option value="0.0522">National Average</option>
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
      <option value="0.1430">New York City</option>
      <option value="0.045">North Carolina</option>
      <option value="0.025">North Dakota</option>
      <option value="0.035">Ohio</option>
      <option value="0.0475">Oklahoma</option>
      <option value="0.099">Oregon</option>
      <option value="0.139">Portland, Oregon</option>
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
      <option value="0.3">France - Financial Assets</option>
      <option value="0.362">France - Real Estate (under 22 years)</option>   
    </select>
  </div>

  <div style="margin: 20px 0;">
    <label for="theta1" style="display: block; margin-bottom: 5px;">
      <strong>Wealth Tax Rate (θ) - Expropriation Risk:</strong>
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
  
  // Check if France, NYC, or Portland is selected
  var isFrance = selectedStateName.indexOf("France") !== -1;
  var isNYC = selectedStateName.indexOf("New York City") !== -1;
  var isPortland = selectedStateName.indexOf("Portland, Oregon") !== -1;
  
  // For NYC and Portland, separate city and state rates
  var cityRate = 0;
  var metroRate = 0;
  var pfaRate = 0;
  var actualStateRate = stateCapGainsRate;
  
  if (isNYC) {
    cityRate = 0.034; // 3.4% NYC tax
    actualStateRate = 0.109; // 10.9% NY state tax
  }

  // For Portland, separate city and state rates
  if (isPortland) {
    metroRate = 0.01; // 1% Metro Tax
    pfaRate = 0.03; // 3% Preschool for All Tax
    cityRate = metroRate + pfaRate; // 4% total city tax
    actualStateRate = 0.099; // 9.9% Oregon state tax
  }
  
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
  
  // Calculate combined tax (base + city + state + federal + NIIT, all in percentage)
  var combinedTax = tBase + (cityRate * 100) + (actualStateRate * 100) + (federalCapGains * 100) + (niit * 100);
  
  // Calculate rho using the combined tax rate
  var tCombinedDecimal = combinedTax / 100;
  
  // Check for division by zero
  if (tCombinedDecimal >= 2) {
    document.getElementById('error1').style.display = 'block';
    document.getElementById('error1').innerHTML = '<strong>Error: Combined tax rate equals or exceeds 200% (calculation not possible).</strong>';
    return;
  }
  
  var rho = r / (1 - tCombinedDecimal);
  
  // Round to 3 decimal places
  tBase = Math.round(tBase * 1000) / 1000;
  combinedTax = Math.round(combinedTax * 1000) / 1000;
  rho = Math.round((rho * 100) * 1000) / 1000;
  
  // Display results - different format for France, NYC, Portland, and regular states
  var resultHTML = "<strong>Base Equivalent Capital Income Tax Rate:</strong> " + tBase + "%<br>";
  
  if (isFrance) {
    resultHTML += "<strong>France Capital Gains Tax Rate:</strong> " + Math.round((stateCapGainsRate * 100) * 100) / 100 + "%<br>";
    resultHTML += "<strong>Comparable Combined Tax on Capital Income:</strong> " + combinedTax + "%<br><br>";
  } else if (isNYC) {
    resultHTML += "<strong>Top City Capital Gains Tax Rate:</strong> " + Math.round((cityRate * 100) * 100) / 100 + "%<br>";
    resultHTML += "<strong>Top State Capital Gains Tax Rate:</strong> " + (actualStateRate * 100) + "%<br>";
    resultHTML += "<strong>Top Federal Capital Gains Tax Rate:</strong> 20%<br>";
    resultHTML += "<strong>Net Investment Income Tax:</strong> 3.8%<br>";
    resultHTML += "<strong>Comparable Combined Tax on Capital Income:</strong> " + combinedTax + "%<br><br>";
  } else if (isPortland) {
    resultHTML += "<strong>Top City Capital Gains Tax Rate:</strong> " + Math.round((cityRate * 100) * 100) / 100 + "%<br>";
    resultHTML += "<strong>Top State Capital Gains Tax Rate:</strong> " + (actualStateRate * 100) + "%<br>";
    resultHTML += "<strong>Top Federal Capital Gains Tax Rate:</strong> 20%<br>";
    resultHTML += "<strong>Net Investment Income Tax:</strong> 3.8%<br>";
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
        <td><a href="https://legislature.maine.gov/statutes/36/title36sec5111.html">36 M.R.S.A. § 5111</a></td>
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
        <td><a href="https://www.revisor.mn.gov/statutes/cite/290.06">Minnesota Statutes § 290.06</a></td>
    </tr>
    <tr>
        <td>Mississippi</td>
        <td>4.4%</td>
        <td><a href="https://advance.lexis.com/documentpage/?pdmfid=1000516&crid=b59466b9-22c5-461b-86ed-22e7f848bff8&nodeid=AAPAAFAABAAD&nodepath=%2FROOT%2FAAP%2FAAPAAF%2FAAPAAFAAB%2FAAPAAFAABAAD&level=4&haschildren=&populated=false&title=%C2%A7+27-7-5.+Imposition+of+the+tax.&config=00JABhZDIzMTViZS04NjcxLTQ1MDItOTllOS03MDg0ZTQxYzU4ZTQKAFBvZENhdGFsb2f8inKxYiqNVSihJeNKRlUp&pddocfullpath=%2Fshared%2Fdocument%2Fstatutes-legislation%2Furn%3AcontentItem%3A6FG8-VHX3-SBN1-P36K-00008-00&ecomp=6gf5kkk&prid=ef6cdf66-5f51-4584-bf45-0c3b636c1a0a">Mississippi Code § 27‑7‑5</a></td>
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

<table>
    <tr>
        <th></th>
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
        <td><a href="https://www.oregonmetro.gov/sites/default/files/2025/10/16/Metro-Code-complete-effective-20250924.pdf">Metro Code § 7.06.040</a>; <a href = "https://multco.us/file/preschool_for_all_personal_income_tax_code/download">Multnomah County Code § 11.512</a></td>
    </tr>
</table>

<table>
    <tr>
        <th></th>
        <th>Capital Gains</th>
        <th>Source</th>
    </tr>
    <tr>
        <td>France - Financial Assets</td>
        <td>30%</td>
        <td><a href="https://www.service-public.gouv.fr/particuliers/vosdroits/F21618?lang=en">Service-Public.fr</a></td>
    </tr>
    <tr>
        <td>France - Real Estate (under 22 years)</td>
        <td>36.2%</td>
        <td><a href="https://www.service-public.gouv.fr/particuliers/vosdroits/F21618?lang=en">Service-Public.fr</a></td>
    </tr>
</table>

The academic content, calculator methodology, and associated research are © 2025 William Dougan and Benjamin Jaros. For inquiries regarding the research or calculator, please contact: hooverfpi@stanford.edu.

<p>Page last updated November 14, 2025.</p>
