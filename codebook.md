## Fields:

### precinct: 
The string id for the smallest election reporting unit of a state. Should generally be left the way it is, except under two conditions. 1) if the precinct is actually some type of total or aggregation of precinct results, then it should be dropped. 2) If we already know what the precinct id looks like from some type of precinct shapefile from a state, then the precinct id should be structured to match the shapefile precinct id. Values that include the string `FLOATING` refer to totals announced at a higher level of aggregation, so for example a county name of `COUNTY FLOATING` represents data reported at the county level.

### office: 
The field which contains the name of the elected position for the race. These should be standardized and stripped of the district code, candidate names, parties, etc. that belong in the other fields. All entries should be in upper case. Standard entries are US PRESIDENT, US SENATE, US HOUSE, GOVERNOR, STATE SENATE, and STATE HOUSE.

### party_detailed:
The upper case party name for the given entry. The most common entries will be DEMOCRAT, REPUBLICAN, and LIBERTARIAN, with the full detailed names for the various parties, including those names that are unique to a given state (i.e. party fusion names). Propositions, amendment, and other referenda should be leave this field as blank "". If there are complications, reach out to one of the QA checkers. 

### party_simplified:
The upper case party name for the given entry. The entries will be one of: DEMOCRAT, REPUBLICAN, LIBERTARIAN, OTHER, and NONPARTISAN. Propositions, amendment, and other referenda should be leave this field as blank "". If there are complications, reach out to one of the QA checkers. 

### mode:
The upper case voting mode for how the election results will be reported. For results that do not offer disaggregation by mode, it will be "TOTAL". For other states that do offer the distinction, then some common entries might include: ABSENTEE, ELECTRONIC, WRITE-IN, PROVISIONAL, ONE-STOP, etc.

### votes:
The numeric value of votes for a given entry. Ensure that commas and the like are not included so as to ensure that it is numeric and not string, and any missing values should be coded as 0. 

### county_name:
The upper case name of the county. As with precincts, values that include the string `FLOATING` refer to totals announced at a higher level of aggregation, so for example a county name of `STATE FLOATING` represents data reported at the state level.

### county_fips: 
The Census 5-digit code for a given county. Structured such that the first two digits are the state fips, and the last three digits are the county part of the fips. Ensure that each component is string padded such that if a state's or county's fip is one digit, i.e. AL, then padded such that it might take the form of 01020. 

### jurisdiction_name:
The upper case name for the jurisdiction. With the exception of New England states, Wisconsin, and Alaska, these will be the same as the county_name. For the New England states, these will be the town names. 

### jurisdiction_fips: 
The fips code for the jurisdiction, which will be the same as the county fips for every state except New England states, Wisconsin, and Alaska. Just as with county fips, these should be string padded, though the fips will be 10 digits.  

### candidate:
The candidate name. Should be all upper case and punctuation.

### district: 
The district identifier for the race, given that it is substate. If the district is a state legislative or U.S. House race, then the district should be string padded to be 3 digits long and with zeroes, i.e. State Senate district 3 would be equal to "003". For other substate units (wards, seats, etc) with multiple levels, should reflect the entire unique identifier, i.e. State District Court of the Sixth district and seat C, would be "6, seat C". Ensure consistency for a given state for these non-legislative and congressional races. For candidates with state wide jurisdictions, district should be "statewide". For races without district info, the field should be equal to "". 

### dataverse:
The dataverse that the data will be a part of, based on its office. The allowed values are "PRESIDENT" for US Presidential races, "SENATE" for US Senate races, "HOUSE" for US House races, and "STATE" for state level executive, legislative, and judicial races. All other races have a blank dataverse value.

Note that judicial races can be determined if they are part of the state dataverse from the State Court Strucutre chart, http://www.courtstatistics.org/state_court_structure_charts?SQ_VARIATION_28850=0
where if it is labeled as Limited Jurisdiction Court, then it is local, and state otherwise. 

### year:
The year of the election.

### stage:
The stage of the election, can be "pri" for primary, "gen" for general, or "runoff" for a runoff election. 

### state: 
The name of the state in capitals. 

### special:
An indicator for whether the election was a special election, "TRUE" if special, "FALSE" for non-special. 

### writein:
An indicator for whether the candidate was a write in, "TRUE" if write in, "FALSE" otherwise. Note that entries noted as "scattering" are write in votes, and should be noted as TRUE. 

### state_po:
The state postal abbreviation. Merged on from the statecode file.

### state_fips:
The state's fips code, 2 digits. Merged on from the statecode file.

### state_cen: 
The state's census code. Merged on from the statecode file.

### state_ic:
Merged on from the statecode file.

### date: 
The date of the primary/election. Note that there will be some states with different election dates for different offices (i.e. presidential primary v. congressional primary). Should be formatted as %y-%m-%d, such that January 5, 2019 would be "2019-01-05" 

### readme_check:
An indicator for whether an issue arose with the data that must be noted in a readme file, "TRUE" if so, and "FALSE" otherwise. Note that such a decision must be made by senior QA staff, and should be minimized to the greatest extent possible. 

### magnitude:
The number of seats to be filled, usually equal to the number of votes an elector can cast for the office
