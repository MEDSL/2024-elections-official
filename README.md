# 2024-elections-official

![](precinct_progress_map.png "Title")

## Repository info
This is the MEDSL repository for election returns from the 2024 General Election in the United States. We have begun compiling precinct-level election results. If you notice any issues in our results, please open an Issue in this repository. 

## General usage notes
### Methods and accuracy
For any questions about how we clean and Quality Assure these data, and how accurate they are, please consult this paper, which answers those questions for our 2016, 2018, and 2020 precinct data efforts: https://www.nature.com/articles/s41597-022-01745-0.

### Warnings
* In general, users need to exercise real caution when computing descriptive statistics. Please make sure you understand exactly which rows belong in the computation you're performing. Here are two of the most common issues:
   * Sometimes the way that states report data generates fictitious zero-vote rows, where a candidate is recorded as getting no votes in a precinct where they did not actually appear on the ballot. It is not generally possible to ensure that all real zero-vote totals are recorded while no fictitious zero-vote totals are recorded. This could affect, for example, measures of central tendency.
   * We typically retain exactly the modes that states report. This can lead to double-counting if users do not select the correct modes, for example if modes are split apart *and* a mode value of `TOTAL` is included. Users should make sure that any analysis includes votes of each mode once.
* While we attempt to verify every value of every variable, `magnitude` values in particular may be approximate for local-level offices. Please double-check these values before relying on them. We are also still working to make sure that the `NONPARTISAN` value of the party fields is propagated correctly to local offices.
* `mode` values typically retain the state's original classification. These original data sources may not identify modes in a way that is consistent across jurisdictions, and one jurisdiction may report more granularly or more accurately than another. For example, `UOCAVA` ballots may be classed as `ABSENTEE` without any means to disaggregate them.

## State-specific information
### Alabama

*Added:*

*Source:*

### Alaska

*Added:*

*Source:*

### Arizona

*Added:*

*Source:*

### Arkansas

*Added:*

*Source:*

### California

*Added:*

*Source:*

### Connecticut

*Added:*

*Source:*

### Colorado

*Added:*

*Source:*

### Delaware

*Added:* 2024-11-13

*Source:* https://elections.delaware.gov/results/html/index.shtml?electionId=GE2024

### District of Columbia

*Added:* 2025-01-23

*Source:* https://electionresults.dcboe.org/election_results/2024-General-Election

### Florida

*Added:* 2025-04-27

*Source:* https://dos.fl.gov/elections/data-statistics/elections-data/precinct-level-election-results/

### Georgia

*Added:*

*Source:*

### Hawaii

*Added:* 2025-07-23

*Source:* Precinct data from here: https://elections.hawaii.gov/election-results/ , precinct to county crosswalk here: https://elections.hawaii.gov/resources/districts-and-precincts/

### Idaho

*Added:*

*Source:*

### Illinois

*Added:* 2025-02-13

*Source:* https://www.elections.il.gov/electionoperations/ElectionVoteTotalsPrecinct.aspx?ID=rfZ%2buidMSDY%3d

### Indiana

*Added:* 2025-08-03

*Source:* Most data are from the state government, here: https://enr.indianavoters.in.gov/site/index.html . However, Indiana has not published complete precinct-level election results since 2018; in 2018, official county-level results were not available, and in 2020 and 2022, Indiana was the only state in which multiple counties did not supply any precinct-level election result data. This occurred again in 2024, so we supplement the official state releases with information from OpenElections in the following counties: Allen, Boone, Clay, Fountain, Gibson, Hancock, Laporte, Noble, Porter, Putnam, Ripley, and Washington. The OpenElections data are available here: https://github.com/openelections/openelections-data-in/tree/master/2024/counties .

*WARNING:* Please be aware of major caveats when using these data.

* The following counties are missing entirely, due to a lack of any availabel precinct-level election result data from an official government source: BENTON, BLACKFORD, BROWN, CARROLL, CASS, CLARK, DAVIESS, DEKALB, DUBOIS, FLOYD, HENDRICKS, JACKSON, JASPER, JAY, LAWRENCE, MADISON, MARSHALL, MIAMI, MONROE, NEWTON, OWEN, PERRY, PULASKI, RANDOLPH, SCOTT, SHELBY, STARKE, STEUBEN, SWITZERLAND, TIPPECANOE, TIPTON, UNION, WABASH, WARREN, WARRICK, and WAYNE

* We are unable to conduct our usual aggregation check, comparing the sum of precinct-level results to county- or district-wide vote totals for state- and federal-level offices, because so many counties are missing election result data entirely. So, we cannot be confident in the accuracy of the reported precinct-level vote totals.

* We ensure completeness and accuracy of the `magnitude` field for any state- or federal-level office, but below that we have left this field blank nearly always for this state. Local offices in Indiana (e.g. school board) often have magnitudes much larger than 1, but in many cases the magnitude is not published as part of the election result reporting, and ballots sample ballots, or local law must be consulted.

* There are some duplicated and nearly duplicated rows. These appear in the original data source. We *suspect* (though we cannot be certain) that they represent different collections of votes, but that some disambiguating information was not included in the original data reporting.

### Iowa

*Added:*

*Source:*

### Kansas

*Added:* 2025-07-23

*Source:* https://sos.ks.gov/elections/election-results.html

*Notes:* A `*` is used to represent a vote total in precincts where the source dataset masked the vote total of sufficiently small geographies to preserve voter privacy.

### Kentucky

*Added:*

*Source:*

### Louisiana

*Added:*

*Source:*

### Maine

*Added:*

*Source:*

### Maryland

*Added:*

*Source:*

### Massachusetts

*Added:*

*Source:*

### Michigan

*Added:*

*Source:*

### Minnesota

*Added:* 2025-02-13

*Source:* https://electionresults.sos.mn.gov/Select/MediaFiles/Index?ersElectionId=170

### Mississippi

*Added:*

*Source:*

### Missouri

*Added:*

*Source:*

### Montana

*Added:* 2024-12-16

*Source:* https://electionresults.mt.gov/ResultsSW.aspx

### Nebraska

*Added:*

*Source:*

### Nevada

*Added:*

*Source:*

### New Hampshire

*Added:* 2025-07-13

*Source:* https://www.sos.nh.gov/2024-general-election-results

### New Jersey

*Added:*

*Source:*

### New Mexico

*Added:* 2025-07-23

*Source:* https://electionresults.sos.nm.gov/

*Notes:* A `*` is used to represent a vote total in precincts where the source dataset masked the vote total of sufficiently small geographies to preserve voter privacy.

### New York

*Added:*

*Source:*

### North Carolina

*Added:* 2024-12-16

*Source:* https://www.ncsbe.gov/results-data/election-results/historical-election-results-data


### North Dakota

*Added:*

*Source:*

### Oklahoma

*Added:* 2024-11-14

*Source:* https://results.okelections.gov/OKER/?elecDate=20241105

### Ohio

*Added:*

*Source:*

### Oregon

*Added:*

*Source:*

### Pennsylvania

*Added:*

*Source:*

### Rhode Island

*Added:*

*Source:*

### South Carolina

*Added:* 2025-05-05

*Source:* https://www.enr-scvotes.org/SC/122436/web.345435/#/access-to-races

### South Dakota

*Added:* 2024-11-21

*Source:* Results from https://electionresults.sd.gov/Default.aspx, candidate party labels from https://vip.sdsos.gov/candidatelist.aspx?eid=684

### Tennessee

*Added:* 2024-12-05

*Source:* https://sos.tn.gov/elections/results

### Texas

*Added:*

*Source:*


### Utah

*Added:*

*Source:*

### Vermont

*Added:*

*Source:*


### Virginia

*Added:* 2025-07-26

*Source:* https://enr.elections.virginia.gov/results/public/Virginia/elections/2024NovemberGeneral

### Washington

*Added:*

*Source:*

### West Virginia

*Added:*

*Source:*

### Wisconsin

*Added:*

*Source:*

### Wyoming

*Added:*

*Source:*
