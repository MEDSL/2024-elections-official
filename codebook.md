## Fields:

### precinct

**Type:** `string`

**Example(s):** `DISTRICT 1-Andover Elementary School Gym`, `PRECINCT 70`, `104`

**Description:** The identifier for the smallest election reporting unit of a state exactly as it appears in the raw data. Note that precinct identifiers and boundaries vary from election to election.

------------------------------------------------------------------------

### office

**Type:** `string`

**Example(s):** `US PRESIDENT`, `STATE HOUSE`, `ERIE COUNTY EXECUTIVE`, `SUPREME COURT - RETENTION - LORETTA RUSH`

**Description:** The uppercase name of the elected position for the race, standardized and stripped of values captured by other variables like district identifiers, candidate names, parties, etc. Standard entries are `US PRESIDENT`, `US SENATE`, `US HOUSE`, `GOVERNOR`, `STATE SENATE`, and `STATE HOUSE`. When a row holds meta-information like the number of registered voters in a jurisdiction, the label is stored in `office`, and `candidate` is left blank.

Other cases: 
- For local offices known to be countywide, `county_name` is prepended to `office` when possible. 
- For state offices besides the legislature and governorship, `office` is standardized across counties when possible. 
- For ballot measures (propositions, initiatives, referenda, state constitutional amendments), district and locality information is preserved to allow proper identification of the question. This includes the type of measure, its designation, and its title. 
- For retention elections (usually judicial contests), the court name, the office, and the candidate's name are preserved in `office` while `candidate` contains `YES/NO` or `FOR/AGAINST`, depending on the state's standard. Identifying district information about the court (district, circuit, division, etc.) appears in `district`.

------------------------------------------------------------------------

### party_detailed

**Type:** `string`

**Example(s):** `REPUBLICAN`, `DEMOCRAT / WORKING FAMILIES`, `GREEN`

**Description:** The uppercase detailed party label of the candidate. The most common entries will be `DEMOCRAT`, `REPUBLICAN`, and `LIBERTARIAN`, with the full detailed names for the various parties. Abbreviated party names should be expanded, e.g., `CON` becomes `CONSTITUTION`, and `PARTY` should generally be omitted. In states like New York with fusion party lines, it contains both parties separated by a forward slash, e.g. `DEMOCRAT / WORKING FAMILIES`. For ballot measures this is left blank.

------------------------------------------------------------------------

### party_simplified

**Type:** `string`

**Example(s):** `DEMOCRAT`, `REPUBLICAN`, `LIBERTARIAN`, `OTHER`, `NONPARTISAN`

**Description:** The uppercase party label of the candidate, standardized to be one of: `DEMOCRAT`, `REPUBLICAN`, `LIBERTARIAN`, `OTHER`, `NONPARTISAN`, or blank (for ballot measures or cases where party cannot be determined).

------------------------------------------------------------------------

### mode

**Type:** `string`

**Example(s):** `TOTAL`, `ELECTION DAY`, `ABSENTEE`

**Description:** The uppercase voting mode for the results, set to `TOTAL` when disaggregation by mode is not reported. For states that do disaggregate by mode, observed values may include but are not limited to `ABSENTEE`, `EARLY MAIL BALLOT`, `MILITARY`, `UOCAVA`, `AFFIDAVIT`, `ABSENTEE/AFFIDAVIT`, `EARLY VOTE`, `ELECTION DAY`, `EMERGENCY`, `IN-PERSON`, `MAIL-IN`, `PROVISIONAL`. With the exception of `TOTAL`, mode is generally not standardized across states.

------------------------------------------------------------------------

### votes

**Type:** `numeric` or `string`

**Example(s):** `42`, `0`, `*`

**Description:** The numeric value of votes for `candidate`. Some small jurisdictions redact vote counts to prevent identifying voters, in which case the value is coded as `*`.

------------------------------------------------------------------------

### county_name

**Type:** `string`

**Example(s):** `ERIE`

**Description:** The uppercase name of the county. Note that for Alaska and Louisiana this value identifies boroughs and parishes, respectively, rather than counties; for Connecticut, this value identifies planning regions.

------------------------------------------------------------------------

### county_fips

**Type:** `string`

**Example(s):** `01002`

**Description:** The Census 5-digit code for a given county where the first two digits are the state FIPS and the last three digits are the county FIPS. For example, Autauga County, AL has a `state_fips` of `01` and its county code is `002` yielding `01002` as the `county_fips`. Note that for Alaska and Louisiana this value identifies boroughs and parishes, respectively, rather than counties; for Connecticut, this value identifies planning regions.

------------------------------------------------------------------------

### jurisdiction_name

**Type:** `string`

**Example(s):** `MIDDLESEX`

**Description:** The uppercase name for the jurisdiction. With the exception of New England states, Wisconsin, and Alaska, these will be the same as `county_name`. For the New England states, these will be the town names.

------------------------------------------------------------------------

### jurisdiction_fips

**Type:** `string`

**Example(s):** `0102700000`, `2501739625`

**Description:** The FIPS code for the jurisdiction. This is `county_fips` with `00000` appended for every state except New England states, Wisconsin, and Alaska, which have ten-digit FIPS codes distinct from counties/boroughs.

------------------------------------------------------------------------

### candidate

**Type:** `string`

**Example(s):** `GEORGE WASHINGTON`, `THOMAS "TOM" JEFFERSON`

**Description:** The candidate name in all uppercase letters in the format `FIRST MIDDLE LAST`. Candidate names are standardized within states according to the following conventions:

1.  Overvotes are coded as `OVERVOTES`.
2.  Undervotes are coded as `UNDERVOTES`.
3.  Write-in candidates' names are uppercased but otherwise preserved, this includes preserving running mates.
4.  When the total write-in votes, rather than individual write-in candidates' totals, are present, they are coded as `WRITE-IN`.
5.  Middle initials do not include a trailing period. Punctuation appears only when it is part of a first, middle, or last name, e.g. `CONAN O'BRIEN` or `ELIZABETH MOUNTBATTEN-WINDSOR`.
6.  Nicknames appear in double quotes following the first name, e.g. `TIMOTHEE "TIM" CHALAMET`.

For `US PRESIDENT` in 2024 the following standardized names are used: `DONALD J TRUMP`, `KAMALA D HARRIS`, `CHASE OLIVER`, `CLAUDIA DE LA CRUZ`, `JILL STEIN`, `RANDALL TERRY`, `PETER SONSKI`, `ROBERT F KENNEDY`, `CORNEL WEST`, `JOSEPH KISHORE`, `RACHELE FRUIT`. Across states we only standardize `candidate` for `US PRESIDENT`.

------------------------------------------------------------------------

### district

**Type:** `string`

**Example(s):** `002`, `6, seat C`, `STATEWIDE`

**Description:** The district identifier for the office following these conventions:
- For state legislative and US House races it is zero-padded to 3 digits, i.e., State Senate District 3 would be equal to `003`. For at-large seats it is set to `AT-LARGE`.
- For sub-state offices with specific sub-state units (districts, wards, seats, zones, etc.), it contains the entire unique identifier standardized within the state. For example, State District Court of the Sixth District and seat C would be `6, seat C`, and a seat in the Fifth District would be `5, seat A`.
- For candidates with statewide jurisdictions it is set to `STATEWIDE`; this includes at-large legislative offices.
- For races without district info, the field is left blank.

------------------------------------------------------------------------

### dataverse

**Type:** `string`

**Example(s):** `PRESIDENT`, `SENATE`, `HOUSE`, `STATE`, `LOCAL`

**Description:** The Harvard Dataverse repository containing the data, based on `office`. The allowed values are: 
- `PRESIDENT` for US Presidential races. 
- `SENATE` for US Senate races. 
- `HOUSE` for US House races.
- `STATE` for state-level executive, legislative, judicial races, or statewide ballot questions.
- `LOCAL` for local contests.

For rows that include ancillary information about the contest (registered voters, ballots cast, total votes, etc.), the value is left blank.

------------------------------------------------------------------------

### year

**Type:** `numeric`

**Example(s):** `2024`

**Description:** The year the election took place.

------------------------------------------------------------------------

### stage

**Type:** `string`

**Example(s):** `GEN`, `PRI`, `RUNOFF`

**Description:** The stage of the election: `PRI` for primary, `GEN` for general, or `RUNOFF` for a runoff election.

------------------------------------------------------------------------

### state

**Type:** `string`

**Example(s):** `NEW YORK`

**Description:** The name of the state in uppercase.

------------------------------------------------------------------------

### special

**Type:** `boolean`

**Example(s):** `TRUE`, `FALSE`

**Description:** An indicator for whether the election was a special election, `TRUE` if special, `FALSE` for non-special.

------------------------------------------------------------------------

### writein

**Type:** `boolean`

**Example(s):** `TRUE`, `FALSE`

**Description:** An indicator that is `TRUE` if the observation is for write-ins or a write-in candidate, `FALSE` otherwise. Note that `SCATTERING` is treated as a write-in.

------------------------------------------------------------------------

### state_po

**Type:** `string`

**Example(s):** `AL`, `NY`

**Description:** The state's postal abbreviation.

------------------------------------------------------------------------

### state_fips

**Type:** `string`

**Example(s):** `01`, `23`

**Description:** The state's FIPS code, zero-padded to be 2 digits.

------------------------------------------------------------------------

### state_cen

**Type:** `string`

**Example(s):** `01`, `21`

**Description:** The state's Census code.

**Internal Notes:**
- Merged from `_help_files/`
------------------------------------------------------------------------

### state_ic

**Type:** `string`

**Example(s):** `41`, `13`

**Description:** The state's IC code.

------------------------------------------------------------------------

### date

**Type:** `string`

**Example(s):** `2024-11-05`

**Description:** The date of the election in the format `%Y-%m-%d`.

------------------------------------------------------------------------

### magnitude

**Type:** `numeric`

**Example(s):** `2`

**Description:** The number of candidates a voter may select for a given office. In most cases this will be `1`, however city councils and other local bodies often have magnitudes of `2` or more. For some offices, this may be empty, which signifies that we were not able to directly verify the magnitude.

---

**Note**:  A variable called `readme_check` was included in our 2018, 2020, and 2022 precinct data, but is discontinued starting in 2024. The readme contains information that is relevant to every row of the dataset.
