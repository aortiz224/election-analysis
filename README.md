# Election Analysis

## Overview of Election Audit
The election commission has requested some additional data to complete the audit:
- The voter turnout for each county
- The percentage of votes from each county out of the total count
- The county with the highest turnout

The purpose of this analysis is to show the additional data requested and explain how we retrieved that data through coding.

## Resources
- Data Source: [Election Results CSV File](Resources/election_results.csv)
- Software: Python 3.7.6, Visual Studio Code 1.52.1

## Election-Audit Results :white_check_mark:
The details below summarize the election outcomes.

*Note: References to code is only partial and for illustration of key points. Refer to the full code [here](PyPoll_Challenge.py).*

- The total number of votes that were cast in the congressional election were **369,711**.

      # With the use of a For Loop, we were able to read through all rows of the CSV file and count the total votes of the election.
        for row in reader:
            total_votes = total_votes + 1

- The breakdown of the number of votes and the percentage of total votes for each county in the precinct is detailed below.

  ![image](https://user-images.githubusercontent.com/74662680/102676478-be016280-416b-11eb-9c24-47ef084e17da.png)

      # With the use of a For Loop, we were able to retrieve the county name, county vote count, and percentage of votes for each county.
      for county_name in county_votes:
        votes = county_votes.get(county_name)
        vote_percentage = float(votes) / float(total_votes) * 100
        county_results = (f"{county_name}: {vote_percentage:.1f}% ({votes:,})\n")

- The county with the largest number of votes was **Denver**.

      # With an IF statement, we were able to determine the winning county and get its vote count.
        if (votes > winning_county_votes):
          winning_county_votes = votes
          winning_county = county_name

- The breakdown of the number of votes and the percentage of the total votes each candidate received is detailed below.

  ![image](https://user-images.githubusercontent.com/74662680/102676225-8c3bcc00-416a-11eb-817d-99e69ceedd8c.png)

      # With a For Loop, we were able to retrieve the final candidate vote count and percentage.
        for candidate_name in candidate_votes:
          votes = candidate_votes.get(candidate_name)
          vote_percentage = float(votes) / float(total_votes) * 100
          candidate_results = (
            f"{candidate_name}: {vote_percentage:.1f}% ({votes:,})\n")
            
- Below is a summary of the candidate who won the election, their vote count, and their percentage of the total votes.

  ![image](https://user-images.githubusercontent.com/74662680/102676289-d755df00-416a-11eb-9cc4-1bcf0dedb320.png)

      # With an IF statement, we were able to determine the winning candidate, their winning votes and percentage of winning votes.      
        if (votes > winning_count) and (vote_percentage > winning_percentage):
            winning_count = votes
            winning_candidate = candidate_name
            winning_percentage = vote_percentage

## Election-Audit Summary

The script above was instrumental in generating the results in this analysis, but it doesn't have to stop there. This same script, with a few minor changes, can be used for any election. For example:
- The script can be modified to be used in a Presidential election. The county names and votes can be replaced by state names and votes in my For Loop to decide the outcome of a Presidential candidate by state. We can further modify the script to assign the number of electoral votes by state to the winning candidate of that state. In addition, for the 2 states that split their electoral votes, the script for these 2 states can be further modified to split the electoral votes based on majority at the county level.
- The script can also be modified to be used on Ballot Measures at the state or local level that have them. These are usually voted on with a 'Yes' or 'No' answer. We can modify the script to determine the number of 'Yes' voters on a particular issue or legislation and quantify the percentage of 'Yes' over the total votes to determine if a majority has been reached to pass the ballot measure.
