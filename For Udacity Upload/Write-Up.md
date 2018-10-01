# Tableau Data Visualization Write-Up

## Summary

The data shown here are drawn from the 2018 records for all registered voters in the state of Texas, with the records being at the individual voter resolution (but aggregated for purposes of visualization so that individual voter identities are protected). These data include demographic information (e.g. voters' birthdates) as well as geospatial information (e.g. voters' current mailing addresses). The geospatial data are likely somewhat flawed in the visualizations presented here as they are referenced off of the Permanent ZIP Code field in the data, which go back to 1970 - since ZIP codes change frequently, the age of these records likely has a negative impact on the geospatial accuracy of the ZIP codes. The goal of this work is to help readers answer this question: if you were to try and target new potential voters for voter registration campaigns, where should you put most of your effort geographically and in what way would it be most effectively deployed?

## Project Links

1. [You can find here my original story design](https://public.tableau.com/profile/dave.rench.mccauley#!/vizhome/TX_Voter_Trends_Agg_v1/Story1?publish=yes)
2. [You can find here the final story design with peer feedback incorporated](https://public.tableau.com/profile/dave.rench.mccauley#!/vizhome/TX_Voter_Trends_Agg_v2/Story1?publish=yes)


## Design

### Pre-Feedback Design

This list is ordered according the final story points I have within my Tableau design, withthe caption text of each story point provided as the sub-section header, for reference.

#### Providing Context

I wanted to give readers the most basic information possible about the dataset as a starting point, to give them a sense of context for the points being made later. I also wanted to point out how the voter count has changed over time relative to Texas' population to highlight the nonlinear trend in registrations over time.


#### A Profile of Texas Voters

Here I wanted to look at voter demographic trends from a variety of angles, to see if there was any clear heterogeneity in who is registered to vote by age, gender, or registration status. I could have sliced this more than 3 ways, but I expect that the average reader can't really intuitively process more than three interacting variables, so it seemed safe to keep the story simpler. Also, since the age distribution was more complex than the other two, I gave it the wide spot on the screen to give readers the most space to explore the nuances of that data. Note that I limited the age range to be between 18 and 123, since you have to be at least 18 to register to vote and the oldest recorded human only lived to be a little shy of 123 years old.


#### Voter Registration Over the Decades

For this story page, I wanted to show how voter registrations trended over time, clearly denote that spikes were due to Presidential election years, while also exposing the oddity in registration ages during Presidential election years in a fun yet intuitive manner, so animation and gratuitous labeling seemed like a good way to do that! Also, the animation is designed to loop, so that it never stops, in case a reader missed something in earlier years.


#### Find Them Where They Live

I wanted to show how ridiculously spread out TX voters are by showing their current mailing addresses. This is a proxy measure for the quantity of absentee ballots that can be expected, as well as an indication that many unregistered voters may be unavailable due to their current place of residence.


#### Bringing It All Together

I chose to color voter count maps based upon the fraction of expected voting population (552,805) vs. actual registered voter count for each US Congressional District. The idea here is that districts with a lower fraction of registered-to-potential voters would likely provide the most bang-for-your-buck in terms of registration drives and other efforts that require a dense population of relevant parties due to the local structure of such efforts. 
 

### Post-Feedback Design

Here I list, by story point, the changes that I made based upon the feedback I document later in this document. Note that not all feedback could be incorporated due to the limits of the Tableau platform.

One general thing I did: make the layout of my story be fixed-size for a laptop browser, as Automatic didn't seem to work for my laptop view on the public server of version 1.

### Providing Context

* Changed the color of the TX population plot to be a darker color and updated the voter registration plot to be darker than that, to call it out visually still
* Synchronized axes for the two plots, to make the difference between registered voter count and overall population obvious to the eye
* Removed the speculation about the non-voting immigrant population and made the language regarding the difference in population trends use more layman's terms
* Added a horizonal reference line for 2018 voting age population number to give clear sense of what the ultimate goal is in a voter registration drive.
	* Also resized some elements and moved legend ot accommodate the line and label

#### A Profile of Texas Voters

* Changed first sentence in text box to say "the smallest groups" instead of "edge cases"
* Switched Voter Status and text box positions to make text more obvious and give screen a less busy look in general
* Changed Age distribution to be fading purple color palette
* Reduced y-axis maximum from 123 to 100 to avoid forcing readers to hunt and click for the small (and thus largely not helpful) higher-age bins
* Added line to the text box "Click on different data to interactively filter all views and explore."


#### Voter Registration Over the Decades

* Added instructions for the play button and moved to be near the text commentary so eye catches it easily
* Disabled animation loop
* Changed axis title to "% of 2018 Voter Pool"
* Did **not** add a floating text box to describe that the years labeled are Presidential election years - the additional text made the screen too busy
* Did **not** add an info box to the Age at Registration pane that points out how distribution of ages skews older in Presidential election years, as it doesn't seem like Tableau can do a floating tooltip like that


#### Find Them Where They Live

* Corrected "Permantent" spelling error
* Made permanent ZIP map blue color scale instead of purple, so you can use purple map color in next story point
* Made Mailing ZIP and Permanent ZIP maps choropleths, with shades denoting number of registered voters (keep it orange)
* In order to facilitate searching for ZIPs where there were low numbers of registered voters (so as to determine if a registration drive should occur there), aggregated these maps by ZIP and not US Congressional district (since aggregating by districts messed up the coloring of the choropleth, associating far-flung mailing ZIP codes with a single district).


#### Bringing It All Together

* Made color scale be “10” not “0.1” so percentages were more intuitive
	* I could not find an easy way to "%" to the scale bar numbers
* Made map have a blue color scale, to avoid implicitly suggesting that the data are all for Females
* Added text to make it clear that these are interactive filters
* Reduced y-axis maximum from 123 to 100 to avoid forcing readers to hunt and click for the small (and thus largely not helpful) higher-age bins


## Feedback: 

I collected feedback from two friends and my wife regarding my initial design and, as a group, they provided joint feedback on each story point within my Tableau story. Here are their comments, listed by story point, which reflect the design changes I outline in the preceding Post-Feedback Design section.

#### General across whole story
* Don’t capitalize data labels in text commentary (e.g. should be “suspended” not “Suspended”)


#### Providing Context

* Audience likely won’t know what a “linear trend” is
	* Make it more descriptive and less scientific language
	* Use “different growth patterns” for most accessible language 
* The population color needs to be darker, brighter, hard to see currently
* The axes are not synchronized so fraction of registered voters isn’t intuitive
* Remove the speculation about the non-voting immigrant population as you don’t have the data to back this up, even as a speculation
* Horizonal reference line for 2018 voting age population number to give clear sense of what the ultimate goal is

#### A Profile of Texas Voters

* What do you mean by edge cases…maybe use more accessible language (e.g. “the smallest groups”)
* Put the text so that it is on the left, put the active/suspended chart together with the gender chart
* The age distribution should be shades of purple, avoids confusing it with the Active filter which is also green
* In the visual you can just go to 100 years old
* Add language to text box letting readers know they should “click to filter” so they know about interactive filtering


#### Voter Registration Over the Decades

* Make the play button larger or at least provide instructions regarding how it should be used
* Once it finishes, animation shouldn’t loop
* Tell readers that they can’t filter on this screen or just make it clear on screens with interactive filters that they are interactive
* If possible, add an info box to the Age at Registration pane that points out how distribution of ages skews older in Presidential election years 
* Change axis title of longitudinal plot to make it clearer that the percentage shown is “percentage of all voters in 2018" (e.g. “All Current Voters”
* Floating text box to describe that the years labeled are Presidential election years


#### Find Them Where They Live

* Spelling mistake on Permanent
* Darken the background map so countries/other states are more visible
* Make permanent map blue color scale instead of purple, so you can use purple map color in next story point
* Make Mailing ZIP map a choropleth, with shades denoting number of registered voters (keep it orange)


#### Bringing It All Together

* Make color scale be “10%” not “0.1”
	* If not possible, change legend to “Fraction Registered of Total Possible Voters”
* Make map color a purple scale instead of blue, to avoid implicitly suggesting that the data are all for Females
* If you can create the info text, “click on the X to see this”
* Add text to make it clear that these are interactive filters



## Resources
Below is a list of resources that provided me with both general and specific help in executing this project. Largely, 
* [Dataquest](https://www.dataquest.io/blog/pandas-big-data/): this group provided info by way of a blog-based tutorial on optimizing pandas DataFrames in memory
* Scientists & Engineers for Civic Engagement: this group guided me towards the data used in this project and helped provide relevant context for the data, its role in the electoral process, different geospatial resolutions of relevance, etc.
* [Tableau Knowledge Base](https://www.tableau.com/support/knowledgebase): general tips and tricks for various specific aspects of visualizations I tried
* [Texas Secretary of State](https://www.sos.state.tx.us/): this group, along with the other Texas government groups/agencies, provided important context on things like historical TX population numbers, voting-age populations in 2018, field mappings for the data files, the data files themselves, etc.
* [Texas Legislative Council](https://tlc.texas.gov/redist/districts/congress.html): see comments for the TX Secretary of State
* [Texas State Library and Archives Commission](https://www.tsl.texas.gov/ref/abouttx/census.html): see comments for the TX Secretary of State* 