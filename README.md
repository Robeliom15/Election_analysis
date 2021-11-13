# Election_analysis

## Overview of Election Audit

### Purpose
I previously made code that focused on information for candidates that went into detail about their votes and who won the election. Now the committee would like more information that can help give a bigger picture of the election results. I want to produce data for the county voter turnout, percentage of county votes, and the highest turnout for each county. 

## Analysis

### Election Audit Results

- How many votes were cast in this congressional election?

Through the image at the bottom of the section, we can see that a total of 369,711 votes were cast during this congressional election. We got this information from the code below.

- Provide a breakdown of the number of votes and the percentage of total votes for each county in the precinct.

The Arapahoe and Jefferson counties have very small county turnouts compared to Denver. Denver has 306,055 votes (82.8%), Jefferson has 38,855 votes (10.5%), and Arapahoe has 24,801 (6.7%) votes.

To get this information, I used this code:
 ```
    for counties_name in counties_votes:
        County_vote = counties_votes.get(counties_name)
        Counties_vote_percentage = float(County_vote) / float(total_votes) * 100
        Counties_results = (
            f"{counties_name}: {Counties_vote_percentage:.1f}% ({County_vote:,})\n"
        print(Counties_results)

        txt_file.write(Counties_results)
        if(County_vote > County_vote_turnout) and (Counties_vote_percentage > Counties_winning_percentage):
            County_vote_turnout = County_vote
            winning_county = counties_name
            Counties_winning_percentage = Counties_vote_percentage
```

- Which county had the largest number of votes?

According to the picture below, Denver has the largest voter turnout

- Provide a breakdown of the number of votes and the percentage of the total votes each candidate received.

The candidate was similar to the county vote since one value had far more votes than the rest. Diana won with 272,892 (73.8%) of the votes. Charles Casper Stockham was in second with 85,213 (23.0%) of the votes. In last was Raymon Anthony Doane with 11,606 (3.1%) of the votes.

To get this information, I used this code:
```
    for candidate_name in candidate_votes:
        votes = candidate_votes.get(candidate_name)
        vote_percentage = float(votes) / float(total_votes) * 100
        candidate_results = (
            f"{candidate_name}: {vote_percentage:.1f}% ({votes:,})\n")
            
        print(candidate_results)
        txt_file.write(candidate_results)

        if (votes > winning_count) and (vote_percentage > winning_percentage):
            winning_count = votes
            winning_candidate = candidate_name
            winning_percentage = vote_percentage
```

- Which candidate won the election, what was their vote count, and what was their percentage of the total votes?

Diana won the election with a grand total of 272,892 votes which was 73.8% of the vote.



![ Election Result]( https://github.com/Robeliom15/Election_analysis/blob/main/Resources/Election%20Results.png?raw=true)

## Election Audit Summary



