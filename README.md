# Kickstarting with Excel: Catch the Fever

This analysis is designed to assist an up and coming playwright, Louise, in launching her dream production of a play called “Fever”.  Although she has never worked with raising funds through Kickstarter, she is estimating a need of $10,000 and is looking for support to executive this plan.
For this analysis, we have accessed information of over 4,000 Kickstarter campaigns and will use the information to give Louise the guidance she needs to make her dream come true.  We have looked at categories, goals, and success rates of these campaigns to provide Louise with the information, along with some additional questions, she needs to begin her journey.

### Analysis and Challenges
To make sense of the Kickstarter data, we needed to disaggregate what was given so we could clearly distinguish the category of campaigns we were investigating using the Text to Columns tool in Excel:

![New Row Headers](https://github.com/jakatz87/kickstarter-analysis/blob/main/Resources/Text_to_Columns.png)

We needed to make sure we were using information that would be most relevant to Louise.  Although there was plenty of data for the “Theater” category among the many other categories in the data set, we want to separate “Plays” from the other subcategories.  

Other challenges included:
- calculating funding success rates `=ROUND(E2/D2*100,0)`
- calculating average donations `=IFERROR(ROUND(E2/L2,2),0)`
- converting the Unix timestamps to easily readable dates `=(((J2/60)/60)/24)+DATE(1970,1,1)`

With this at hand, we were able use the necessary information that would guide Louise:
- Campaign Goals and Pledges
- Average Donation per Backer
- Timeframes of Campaigns

### Campaign Goals and Pledges
Using the data, we were able to establish some statistics for both Successful and Failed plays in the US to give Louise the most relevant data for her project:
- Mean Goal/Pledged: `=AVERAGE('Successful US Kickstarters'!D:D)`
- Median Goal/Pledged: `=MEDIAN('Successful US Kickstarters'!D:D)`
- Standard Deviation: `=STDEV.P('Successful US Kickstarters'!D:D)`
- Upper Quartile: `=QUARTILE.EXC('Successful US Kickstarters'!D:D, 3)`
- Lower Quartile: `=QUARTILE.EXC('Successful US Kickstarters'!D:D, 1)`
- InterQuartile Range: `=B7-B8`

![Relevant Statistics](https://github.com/jakatz87/kickstarter-analysis/blob/main/Resources/Statistics.png)

**Conclusion**
With this information, we could give Louise insight for her goal of $10,000.  Would that be a reasonable amount based on previous data and trends?  Based on a widely used statistical definition of an Outlier:  `>Q3+1.5*IQR` , her goal would not be an outlier in the data set.  

We were also able to investigate success rates for comparable goal amounts:

![Outcomes with Data](https://github.com/jakatz87/kickstarter-analysis/blob/main/Resources/Outcomes%20v%20Goals%20with%20Data.png)

**Conclusion**
For her goal, we can see there is about a 50% success rate. If she wants to adjust her goal based on a higher success rate, she can use the chart to see where her cutting threshold may be.

### Average Donation per Backer
Louise will need to know the work necessary to make her campaign successful.  She’ll need to know how many backers to pledge to the campaign and how much to ask from those backers. 

From this chart, we can let Louise know there have been successful campaigns around $10,000 with as few as 12 backers and as many as 288.  She can also see there is no evident pattern or trajectory for success based on the number of backers:

![Backers per Goal](https://github.com/jakatz87/kickstarter-analysis/blob/main/Resources/Backers%20per%20Goal.png)

From this chart, we can let Louise know successful campaigns with backers from 10 to 300 can have average donation amounts between $25 and $300.  She can see there is no evident pattern or trajectory here either.

![Average Donation](https://github.com/jakatz87/kickstarter-analysis/blob/main/Resources/Average%20Donations.png)

**Conclusion**
Since there is no evident trajectory and this is Louise’s first Kickstarter campaign, she may want to have aggressive targets for 250 backers with a $40 average donation.  

### Timeframes of Campaigns
Whatever Louise decides to do with her goal and plan for her campaign, it will be important for  her to know when to launch it.  The previous two questions we raised didn’t seem to have a pattern to them, as important as it was to ask.  This question does, in fact, have a pattern to it.
Consider the chart:

![Plays Outcomes](https://github.com/jakatz87/kickstarter-analysis/blob/main/Resources/Plays%20outcomes%20for%20analysis.png)

**Conclusions**
When launching a Kickstarter campaign for a play, there does seem to be a pattern:  it is best to launch the campaign in May/June.  She should also be aware of what happens in the December/January timeframe.  Not only can we tell that is not the best time to launch a campaign, she may want to expect her donations to be slow in that time period.

### Additional Information
There is missing data that would be helpful: do the successful campaigns include 'angel investors' or 'anchor gifts'? And if so, how early in the campaign were they secured? An additional data set may include, for each campaign, a list of each gift and when it was given, so charts can be created to display data for a given campaign beside average donation.

## Summary
We hope this analysis gives Louise the information she needs to pursue her dream.  She should see from our analysis that her dream is indeed possible, but it comes with some hard work and planning: starting the campaign in May/June and targeting 250 backers over the course of the year (knowing December and January will be slow). 
