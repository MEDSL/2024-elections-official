# 2024-elections-official

![](precinct_progress_map_.png "Title")

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

*Added:*

*Source:*

### District of Columbia

*Added:*

*Source:*

### Florida

*Added:*

*Source:*

### Georgia

*Added:*

*Source:*

### Hawaii

*Added:*

*Source:*

### Idaho

*Added:*

*Source:*

### Illinois

*Added:*

*Source:*

### Indiana

*Added:*

*Source:*

### Iowa

*Added:*

*Source:*

### Kansas

*Added:*

*Source:*

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

*Added:*

*Source:*

### Mississippi

*Added:*

*Source:*

### Missouri

*Added:*

*Source:*

### Montana

*Added:*

*Source:*

### Nebraska

*Added:*

*Source:*

### Nevada

*Added:*

*Source:*

### New Hampshire

*Added:*

*Source:*

### New Jersey

*Added:*

*Source:*

### New Mexico

*Added:*

*Source:*

### New York

*Added:*

*Source:*

### North Carolina

*Added:*

*Source:*


### North Dakota

*Added:*

*Source:*

### Oklahoma

*Added:*

*Source:*

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

*Added:*

*Source:*

### South Dakota

*Added:*

*Source:*

### Tennessee

*Added:*

*Source:*

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

*Added:*

*Source:*

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