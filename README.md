# Election-Analysis-Challenge-module-3

## Overview of Election Audit: 
The purpose of this analysis was to audit the tabulated election results of a US Congressional Precinct for the Colorado Board of Elections.  Data collected from three sources (mail in votes, punch card votes, and electronic votes) had already been combined into a single csv file, named election_results.csv, which was the data source for this exercise.  The initial work was focused on extracting the total number of votes cast, the total number of votes for each candidate, the percentage of votes for each candidate, and the winner of the election based on the popular vote.  Then I performed an additional analysis of the total votes cast by county, the percentage of votes registered by each county, and determination of which county had the largest turnout of voters.

## Election-Audit Results: 
First I will describe the high level results and then provide a walkthrough of the highlights of the code utilized to achieve the results. 
Top line results:
- In the US Congressional Precinct analyzed, there are three counties (Jefferson County, Denver County, and Arapahoe County).  The total number of votes cast in this election across all three counties is 369,711.
- The number of total votes in each county breakdown as follows: Jefferson County had 38,855 total votes, Denver County had 306,055 total votes, and Arapahoe County had 24,801 total votes.  In terms of percentage of total, Jefferson County represented 10.5% of the total vote, Denver County represented 82.8% of the total vote, and Arapahoe County represented 6.7% of the total vote.
- Denver County was the county with the largest turnout in terms of absolute number of votes cast.
- The three candidates in this election were Charles Casper Stockham, Diana DeGette, and Raymon Anthony Doane.  Charles Casper Stockham received 85,213 votes, representing 23.0% of the total votes.  Diana DeGette received 272,892 votes, representing 73.8% of the total votes.  And Raymon Anthony Doane received 11,606, representing 3.1% of the total votes.
- Diana DeGette is determined to be the winner of the election, having received 73.8% (272,892) of the total votes (369,711).

The following methodology was used to obtain the above results.  To calculate the total number of votes, I first created a total_vote counter and set it to zero.

![image](https://user-images.githubusercontent.com/90977689/136279087-7b3b9a8a-27e4-46c5-8757-0267dec7b306.png)

I then created empty lists, dictionaries, and vote counters to hold values associated with each candidate and counties.

![image](https://user-images.githubusercontent.com/90977689/136279940-75cc0119-ffda-41d3-9ef0-cab42a185e90.png)

After importing the csv file and skipping the header row, I set up a for loop to enable me to add one vote to the vote counter, extract candidate name, and extract county name from each row.  

![image](https://user-images.githubusercontent.com/90977689/136281246-d94b05ea-2910-4dd0-a55e-7fc6935ae03d.png)

This was followed by an if statement to determine if the candidate name was already in the candidate list.  If it was not, the follwoing code added the candidate name to the candidate list and began tracking the candidate votes (being sure to set the candidate votes counter to zero first).

![image](https://user-images.githubusercontent.com/90977689/136281703-1f5c37d7-22f8-474e-8d73-3b25662d6cf4.png)

I then set up a similar if statement to perform a similar function for county.

![image](https://user-images.githubusercontent.com/90977689/136281911-2f21dcaf-d212-4181-90c1-de1154d53c1e.png)

Once the information was extracted from each row, I wrote a for loop to retrieve the county names and votes from the dictionary created earlier.  I then used that information to calculate the percentage of votes for each county.  It was also important within the for loop to create an if statement to determine the winning county and get its vote count.  The code is shown below.  It should be noted that the code block shown also includes the code I used to write this portion of the analysis to the election_results.txt file as well as to print to the terminal.  This challenge asked for these print and write tasks to be done in stages throughout the program.  I include this one as an exemplar because it was important for this (and subsequent code) to remember to use the "a" in the open(file_to_save, "a") as text file line.  If I had used "w", this code would have overwritten the vote total information I had written to the txt file earlier.



![image](https://user-images.githubusercontent.com/90977689/136288664-2f585645-3846-4a7b-93ef-fd8d74fddfeb.png)

Similar code was used for the candidates and is not shown in this write up.  Like the previous code for county, within this candidate for loop an if statement was used in this case to determine the winning vote count, winning percentage, and winning candidate as shown below.  It is important to note that the print statements for the County with largest turnout and for the winning candidate have to be outside the loops.

![image](https://user-images.githubusercontent.com/90977689/136290775-1cab6573-e0bd-4b37-933c-92d94cb331bf.png)

For the complete code, please see the file PyPoll_Challenge_Sheehan_vf.py in this repository.


## Election-Audit Summary: 

In summary, we have developed a robust and extensible code for auditing elections.  I propose that this code could easily be adapted to audit city government elections.  Certainly city elections would collect similar data at the polling location level as opposed to the county level.  As such, one would just need to locate the labels in the current code that currently deal with county and change them to appropriate labels for polling location.  Of course you would also have to make sure you are pulling data from the correct row in your new city data spreadsheet as well. The code as currently constructed is not limited by number of candidates or locations.  And of course, this code could be extended to a national election, changing counties for states.

Another low cost opportunity for modification of this code would be to pull in population data to enrich the insights delivered by our analysis.  For example in the code above, we could easily insert a calculation using the population of each county to report out the percent turnout by county.  Enabling us to know which county had the highest turnout as a percentage of their population would provide us with additional context and insight into voter enthusiasm at the local level. 
