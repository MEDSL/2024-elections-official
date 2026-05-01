# 2024-elections-official

This is the MIT Election Data + Science Lab repository for precinct-level election returns from the 2024 General Election in the United States. See our [2024 precincts Harvard Dataverse](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/PRRM1V).

If you notice any issues in our results, please open an issue in this repository. **We ask that you triple check that potential issues exist in the repository's data and are not an artifact of the way that you are processing the data.**

## Usage
### Methods and accuracy
For any questions about how we clean and Quality Assure these data, and how accurate they are, please consult this paper, which answers those questions for our 2016, 2018, and 2020 precinct data efforts (see Appendix E for precinct data processing methods): https://arxiv.org/abs/2106.04570

For more of our election return data, visit [our website](https://electionlab.mit.edu/data) or the [Harvard Dataverse](https://dataverse.harvard.edu/dataverse/medsl_election_returns).

We strongly encourage a careful reading of the below and our [codebook](codebook.md) before you begin working with the data.

### Warnings
* In general, users need to exercise real caution when computing descriptive statistics. Please make sure you understand exactly which rows belong in the computation you're performing. Here are two of the most common pitfalls:
   * Sometimes the way that states report data generates fictitious zero-vote rows, where a candidate is recorded as getting no votes in a precinct where they did not actually appear on the ballot. It is important to ensure that these rows do not contaminate, for example, the mean vote share for a candidate.
   * We typically retain exactly the modes that states report. This can lead to double-counting if users do not select the correct modes, for example if modes are split apart *and* a mode value of `TOTAL` exists.
* While we attempt to verify every value of every variable, `magnitude` values in particular may be approximate for local-level offices. Please double-check these values before relying on them. We are working on quality assuring these values.
* `mode` values typically retain the state's original classification. These original data sources may not identify modes in a way that is consistent across jurisdictions, and one jurisdiction may report both `MAIL` and `ABSENTEE`, for example.
* In some small jurisdictions in California, Kansas, Nevada, and New Mexico, vote counts are not published due to privacy concerns. In these cases `votes = "*"`.

## State-specific information
### Alabama
*Added:* 2025-10-31  
*[Source](https://www.sos.alabama.gov/alabama-votes/voter/election-data)*  

*Notes:* Alabama gives voters an option to check one box to cast a straight ticket ballot (e.g. vote for all Republican candidates). We denote this as `office = "STRAIGHT PARTY"`.

### Alaska
*Added:* 2025-11-19  
*[Source](https://www.elections.alaska.gov/election-results/e/?id=24genr)*  

### Arizona
*Added:* 2026-03-20  
*[Source](https://github.com/openelections/openelections-data-az/tree/master/2024/General)*  

**Notes:** `STATE HOUSE` races in Pima County are missing values for `district` due to limitations of the source data.

### Arkansas
*Added:* 2025-11-07  
*[Source](https://results.enr.clarityelections.com/AR/122502/web.345435/#/reporting)*  

### California
*Added:*  2026-04-01  
*[Source](https://statewidedatabase.org/election.html)*  

**Notes:** 

With regards to `precinct` codes:

`precinct` ending in `"A"`
- These are thought to denote absentee ballots.

From the Statewide Database's FAQ we have: 

> There are two rows for each precinct in the SVPREC files: one with a number and one with the same number plus "A" (e.g., 202 and 202A). To determine total vote for a candidate, for example, should I add the two rows?

> Yes. The A denotes the absentee ballots that were cast in that precinct.

`precinct` ending in `"AA"`
- These are thought to denote all-absentee jurisdictions because the "AA" (All-Absentee) designation is a legal status defined under California Elections Code §3005.

`precinct` ending in `"B"` or `"C"`
- We believe these denote later supplemental batches of votes that are provisionals or VBM dropped off on Election Day.

Upon reaching out to [Statewide Database](https://statewidedatabase.org/), we were told that these suffixes on precinct names are determined jurisdiction by jurisdiction and are not necessarily standardized.

### Colorado
*Added:* 2025-10-24  
*[Source](https://www.sos.state.co.us/pubs/elections/resultsData.html)*  

### Connecticut
*Added:* 2025-11-05  
*[Source](https://ctemspublic.tgstg.net/#/home)*  

### Delaware
*Added:* 2024-11-13  
*[Source](https://elections.delaware.gov/results/html/index.shtml?electionId=GE2024)*  

### District of Columbia
*Added:* 2025-01-23  
*[Source](https://electionresults.dcboe.org/election_results/2024-General-Election)*  

### Florida
*Added:* 2025-04-27  
*[Source](https://dos.fl.gov/elections/data-statistics/elections-data/precinct-level-election-results/)*  

### Georgia
*Added:* 2025-10-30  
*[Source (precinct data)](https://results.sos.ga.gov/results/public/Georgia/elections/2024NovGen)*  
*[Source (office crosswalk)](https://results.sos.ga.gov/results/public/Georgia/elections/2024NovGen/reports)*  

### Hawaii
*Added:* 2025-11-19  
*[Source (precinct data)](https://elections.hawaii.gov/election-results/)*  
*[Source (precinct-to-county crosswalk)](https://elections.hawaii.gov/resources/districts-and-precincts/)*  

### Idaho
*Added:* 2025-12-17  
*[Source](https://voteidaho.gov/election-results/)*  

### Illinois
*Added:* 2025-02-13  
*[Source](https://www.elections.il.gov/electionoperations/ElectionVoteTotalsPrecinct.aspx?ID=rfZ%2buidMSDY%3d)*  

### Indiana
*Added:* 2025-08-03  
*[Source (official state data)](https://enr.indianavoters.in.gov/site/index.html)*  
*[Source (supplemental OpenElections data)](https://github.com/openelections/openelections-data-in/tree/master/2024/counties)*  

**Warning:** Major caveats apply to Indiana’s data completeness and accuracy. Senate and Governor totals are overreported because some county sources appear to fold straight-party votes into candidate vote totals.

### Iowa
*Added:* 2025-11-03  
*[Source](https://sos.iowa.gov/elections/results/precinctvotetotals2024general.html)*  

### Kansas
*Added:* 2025-07-23  
*[Source](https://sos.ks.gov/elections/election-results.html)*  

### Kentucky
*Added:*  2025-05-06  
*[Source](https://elect.ky.gov/results/2020-2029/Pages/2024.aspx)*  

### Louisiana
*Added:*  2026-01-20  
*[Source](https://voterportal.sos.la.gov/static/2024-11-05)*  

**Notes:** Louisiana reports early voting only at the parish level, as such early votes are NOT included in the precinct data.

### Maine
*Added:* 2025-10-27  
*[Source](https://www.maine.gov/sos/cec/elec/results/results24.html)*  

**Notes:** 

For some observations, `jurisdiction_fips` was unable to be determined. 

Maine precinct totals are first-round counts and will not match final certified presidential/Senate totals because of ranked-choice redistribution.

State House district 021 is missing candidate Marianna Reeves because she is absent from the raw data.

### Maryland
*Added:* 2025-11-13  
*[Source](https://www.elections.maryland.gov/elections/2024/index.html)*  

### Massachusetts
*Added:* 2025-10-24  
*[Source](https://electionstats.state.ma.us/elections/search/year_from:2024/year_to:2024/stage:General)*  

### Michigan
*Added:* 2025-10-24  
*[Source](https://mielections.us/election/results/)*  

**Notes:** There are several cases of negative vote values that appear to be county-level correction artifacts, these were retained as reported.

### Minnesota
*Added:* 2025-02-13  
*[Source](https://electionresults.sos.mn.gov/Select/MediaFiles/Index?ersElectionId=170)*  

### Mississippi
*Added:* 2026-04-13  
*[Source](https://sos.ms.gov/elections/electionresults_aspx/elections_results_2024_county.aspx)*  

### Missouri
*Added:* 2025-10-24  
*[Source](https://enr.sos.mo.gov/)*  

**Notes:** Kansas City rows use synthetic county_fips = 36000 as a cross-county placeholder because Kansas City spans multiple counties.

### Montana
*Added:* 2024-12-16  
*[Source](https://electionresults.mt.gov/ResultsSW.aspx)*  

### Nebraska
*Added:* 2025-10-24  
*[Source](https://electionresults.nebraska.gov/default.aspx)*  

### Nevada
*Added:* 2025-11-10  
*[Source (results)](https://www.nvsos.gov/electionresults/)*  
*[Source (parties)](https://www.nvsos.gov/sos/elections/election-information/2024-election-information)*  

### New Hampshire
*Added:* 2025-07-13  
*[Source](https://www.sos.nh.gov/2024-general-election-results)*  

### New Jersey
*Added:* 2026-02-04  
*Source:* NJ's data is collected from a number of locations, including:
- https://www.nj.gov/state/elections/election-night-results.shtml
- https://github.com/openelections/openelections-data-nj/tree/master/2024
- https://www.co.hunterdon.nj.us/DocumentCenter/View/15968/G2024-Official-Elections-Results-PDF 
- https://sussexcountyclerk.org/wp-content/uploads/2025/01/OFFICIAL-Precinct-Rpt-suppressed-11-25-Amended-web.pdf
- https://www.warrencountyvotes.com/home/showpublisheddocument/11384
- https://www.camdencounty.com/wp-content/elections/general2024/2024_General_Election_Canvasser.pdf
- https://www.bergencountyclerk.gov/_Content/pdf/ElectionResult/2024%20General%20District%20Report(2).pdf
- https://www.livevoterturnout.com/ENR/salemnjenr/7/en/Index_7.html
- https://gloucestercountynj.gov/1252/Previous-Election-Results

**Notes:** 

In 2024 NJ reported its data at the election district level but also included totals at the municipal level. For instance, an observation with `precinct = "Cliffside Park"` provides the total votes across the municipality, while `precinct = "Cliffside Park ED 1"` provides the votes for that election district.

### New Mexico
*Added:* 2025-07-23  
*[Source](https://electionresults.sos.nm.gov/)*  

### New York
*Added:* 2026-03-24  
*Source:* Most counties' data were drawn from [OpenElections](https://github.com/openelections/openelections-sources-ny/tree/master/2024/general), NYC data drawn from [here](https://www.vote.nyc/page/election-results).

**Notes:**

New York is one of the most challenging states to gather and standardize precinct-level returns for due to data availability, formatting, and complexity. Considerable care should be taken when using these data.

* Party fusion: New York uses a party fusion system where candidates appear on multiple party lines. Most counties report vote totals for each party line separately, in these cases we preserve this in the data.
* Negative undervotes: There are two cases of undervotes being reported as `-2` in the raw Albany County data. We reached out to the Albany County Board of Elections who explained this as a system-balance artifact.
* Jefferson and Dutchess County have minor vote shortfalls/missing precincts due to "protected precincts" where data is suppressed for privacy.
* Herkimer County is missing results for `office = "State Proposal One"` in the raw data from the county.

### North Carolina
*Added:* 2024-12-16  
*[Source](https://www.ncsbe.gov/results-data/election-results/historical-election-results-data)*  

### North Dakota
*Added:* 2025-11-10  
*[Source](https://results.sos.nd.gov/ResultsExport.aspx?)*  

### Ohio
*Added:* 2025-10-31  
*[Source](https://www.ohiosos.gov/elections/election-results-and-data/2024-official-election-results/)*  

### Oklahoma
*Added:* 2024-11-14  
*[Source](https://results.okelections.gov/OKER/?elecDate=20241105)*  

### Oregon
*Added:* 2026-04-17  
*Source:* [Open Elections](https://github.com/openelections/openelections-sources-or/tree/master/2024/general) and county websites

### Pennsylvania
*Added:* 2025-10-24  
*[Source](https://www.pa.gov/agencies/dos/resources/voting-and-elections-resources/voting-and-election-statistics/bulk-election-data.html#accordion-b33bb36a11-item-d105bc02cf)*  

### Rhode Island
*Added:* 2025-11-10  
*[Source](https://elections.ri.gov/elections/previous-election-results)*  

### South Carolina
*Added:* 2025-05-05  
*[Source](https://www.enr-scvotes.org/SC/122436/web.345435/#/access-to-races)*  

### South Dakota
*Added:* 2024-11-21  
*[Source (official results)](https://electionresults.sd.gov/Default.aspx)*  
*[Source (candidate party labels)](https://vip.sdsos.gov/candidatelist.aspx?eid=684)*  

### Tennessee
*Added:* 2024-12-05  
*[Source](https://sos.tn.gov/elections/results)*  

### Texas
*Added:* 2025-10-24  
*[Source](https://data.capitol.texas.gov/topic/elections)*  

### Utah
*Added:* 2025-11-07  
*[Source](https://electionresults.utah.gov/results/public/utah/elections/general11052024)*  

### Vermont
*Added:* 2025-10-24  
*[Source](https://electionarchive.vermont.gov/elections/search/date:2024-11-05)*  

### Virginia
*Added:* 2025-07-26  
*[Source](https://enr.elections.virginia.gov/results/public/Virginia/elections/2024NovemberGeneral)*  

### Washington
*Added:* 2025-11-07  
*[Source](https://results.vote.wa.gov/results/20241105/export.html)*  

### West Virginia
*Added:* 2025-10-24  
*[Source](https://results.enr.clarityelections.com/WV/122766/web.345435/#/summary)*  

### Wisconsin
*Added:* 2025-11-07  
*[Source](https://elections.wi.gov/elections/election-results#accordion-11951)*  

**Notes:** `VILLAGE OF LISBON` rows are missing jurisdiction_name and jurisdiction_fips in the source data and could not be resolved cleanly.

### Wyoming
*Added: 2025-12-17*  
*[Source](https://sos.wyo.gov/Elections/Docs/2024/2024GeneralResults.aspx)*  

---

All sections without current entries are placeholders and will be updated as additional states are processed.
