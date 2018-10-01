# 2018 Texas Voter Rolls Parsing and Analysis

## Description

Data for all registered voters in Texas were requested and provided by the Texas Secretary of State's office in August 2018. This work imports the 15M+ records, cleans them up, merges them with geographic data related to voting precincts, districts, etc. and does some basic exploratory analysis. 

Much of the more advanced visualization and exploration work can be found in [this public Tableau site.](https://public.tableau.com/profile/dave.rench.mccauley#!/vizhome/TX_Voter_Trends_Agg_v2/Story1?publish=yes)

## Acknowledgements

I was connected to this project by the group Science & Engineers for Civic Engagement (SE Civics). They were looking for data scientist volunteers to help out with various projects. Various open datasets related to Texas electorate areas were utilized in this work. Thank you to SE Civics for helping make this project happen, it was a great experience learning how to handle such large and varied data!

## Code

* voter_data_processing.py contains the data prep and cleaning code for stitching together lots of voter data files from TX SOS and then optimizing resultant pandas DataFrame for lowest possible memory usage

## Data Files

* /VoterCounts includes CSV files that aggregate voter record counts, for active and suspended voters, at different geographic resolutions: precinct, state house district, state senate district, and US Congressional district
	* Also, each of these CSV files has a precinct/district of -1 that counts the number of records missing a value for the given geographic resolution (e.g. precinct or district)