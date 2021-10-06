# Election-Analysis-Challenge-module-3

## Overview of Election Audit: 
The purpose of this analysis was to audit the tabulated election results of a US Congressional Precinct for the Colorado Board of Elections.  Data collected from three sources (mail in votes, punch card votes, and electronic votes) had already been combined into a single csv file, named election_results.csv, which was the data source for this exercise.  The initial work was focused on extracting the total number of votes cast, the total number of votes for each candidate, the percentage of votes for each candidate, and the winner of the election based on the popular vote.  Then I performed an additional analysis of the total votes cast by county, the percentage of votes registered by each county, and determination of which county had the largest turnout of voters.

## Election-Audit Results: 
First I will describe the high level results and then provide a walkthrough of the highlights of the code utilized to achieve the results. 
Top line results:
- In the US Congressional Precinct analyzed, there are three counties (Jefferson County, Denver County, and Arapahoe County).  The total number of votes cast in this election across all three counties is 369,711.
- The number of total votes in each county breakdown was as follows: Jefferson County had 38,855 total votes, Denver County had 306,055 total votes, and Arapahoe County had 24,801 total votes.  In terms of percentage of total, Jefferson County represented 10.5% of the total vote, Denver County represented 82.8% of the total vote, and Arapahoe County represented 6.7% of the total vote.
- Denver County was the county with the largest turnout in terms of absolute number of votes cast.
- The three candidates in this election were Charles Casper Stockham, Diana DeGette, and Raymon Anthony Doane.  Charles Casper Stockham received 85,213 votes, representing 23.0% of the total votes.  Diana DeGette received 272,892 votes, representing 73.8% of the total votes.  And Raymon Anthony Doane received 11,606, representing 3.1% of the total votes.
- Diana DeGette is determined to be the winner of the election, having received 73.8% (272,892) of the total votes (369,711).

The following methodology was used to obtain the above results.  To calculate the total number of votes, I first created a total_vote counter and set it to zero.
![image](https://user-images.githubusercontent.com/90977689/136279087-7b3b9a8a-27e4-46c5-8757-0267dec7b306.png)

I then created empty lists and dictionaries to hold values associated with each candidate and counties.

![image](https://user-images.githubusercontent.com/90977689/136279940-75cc0119-ffda-41d3-9ef0-cab42a185e90.png)



## Election-Audit Summary: 
In a summary statement, provide a business proposal to the election commission on how this script can be used—with some modifications—for any election. Give at least two examples of how this script can be modified to be used for other elections.
