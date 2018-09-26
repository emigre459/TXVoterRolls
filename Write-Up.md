# Tableau Data Visualization Write-Up

## Summary

The data shown here are drawn from records for all registered voters in the state of Texas, with the records being at the individual voter resolution (but aggregated for purposes of visualization so that individual voter identities are protected). These data include demographic information (e.g. voters' birthdates) as well as geospatial information (e.g. voters' current mailing addresses). The geospatial data are likely somewhat flawed in the visualizations presented here as they are referenced off of the Permanent ZIP Code field in the data, which go back to 1970 - since ZIP codes change frequently, the age of these records likely has a negative impact on the geospatial accuracy of the ZIP codes. The goal of this work is to help readers answer this question: if you were to try and target new potential voters for voter registration campaigns, where should you put most of your effort geographically and in what way would it be most effectively deployed?


## Design

### Pre-Feedback Design

1. I wanted to give readers the most basic information possible about the dataset as a starting point, to give them a sense of context for the points being made later. I also wanted to point out how the voter count has changed over time relative to Texas' population to explain the nonlinear trend in registrations over time
	* **Point for possible changes:** I may want to remove the population estimates plot - since it's roughly linear over time, it may create more confusion than be a help
2. Here I wanted to look at voter demographic trends from a variety of angles, to see if there was any clear heterogeneity in who is registered to vote by age, gender, or registration status. I could have sliced this more than 3 ways, but I expect that the average reader can't really intuitively process more than three interacting variables, so it seemed safe to keep the story simpler. Also, since the age distribution was more complex than the other two, I gave it the wide spot on the screen to give readers the most space to explore the nuances of that data.
3. For this story page, I wanted to show how voter registrations trended over time, clearly denote that spikes were due to Presidential election years, while also exposing the oddity in registration ages during Presidential election years in a fun yet intuitive manner, so animation and gratuitous labeling seemed like a good way to do that!
	* That being said, I probably need to update the x-axis title at least, as this measure is somewhat complicated
4. I wanted to show how ridiculously spread out TX voters are by showing their current mailing addresses. This is a proxy measure for the quantity of absentee ballots that can be expected, as well as an indication that many unregistered voters may be unavailable due to their current place of residence.
5. I chose to color voter count maps based upon the fraction of expected voting population (552,805) vs. actual registered voter count for each US Congressional District. The idea here is that districts with a lower fraction of registered-to-potential voters would likely provide the most bang-for-your-buck in terms of registration drives and other efforts that require a dense population of relevant parties due to the local structure of such efforts.
6. 
 

### Post-Feedback Design
1. 


## Feedback: include all feedback you received from others on your visualization from the first sketch to the final visualization



## Resources
Below is a list of resources that provided me with both general and specific help in executing this project. Largely, 
* [Dataquest](https://www.dataquest.io/blog/pandas-big-data/): this group provided info by way of a blog-based tutorial on optimizing pandas DataFrames in memory
* Scientists & Engineers for Civic Engagement: this group guided me towards the data used in this project and helped provide relevant context for the data, its role in the electoral process, different geospatial resolutions of relevance, etc.
* [Tableau Knowledge Base](https://www.tableau.com/support/knowledgebase): general tips and tricks for various specific aspects of visualizations I tried
* [Texas Secretary of State](https://www.sos.state.tx.us/): this group, along with the other Texas government groups/agencies, provided important context on things like historical TX population numbers, voting-age populations in 2018, field mappings for the data files, the data files themselves, etc.
* [Texas Legislative Council](https://tlc.texas.gov/redist/districts/congress.html): see comments for the TX Secretary of State
* [Texas State Library and Archives Commission](https://www.tsl.texas.gov/ref/abouttx/census.html): see comments for the TX Secretary of State
* 