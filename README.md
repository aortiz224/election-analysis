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
  
  ![image](https://user-images.githubusercontent.com/74662680/102675858-feabac80-4168-11eb-92d5-43b2b3d7e8b9.png)

- The county with the largest number of votes was **Denver**.

      # With an if statement, we were able to determine the winning county and get its vote count.
        if (votes > winning_county_votes):
          winning_county_votes = votes
          winning_county = county_name

- The breakdown of the number of votes and the percentage of the total votes each candidate received is detailed below.

  ![image](https://user-images.githubusercontent.com/74662680/102676225-8c3bcc00-416a-11eb-817d-99e69ceedd8c.png)

- Below is a summary of the candidate who won the election, what was their vote count, and what was their percentage of the total votes.

  ![image](https://user-images.githubusercontent.com/74662680/102676289-d755df00-416a-11eb-9cc4-1bcf0dedb320.png)

## Election-Audit Summary

In a summary statement, provide a business proposal to the election commission on how this script can be used—with some modifications—for any election. Give at least two examples of how this script can be modified to be used for other elections.

There is a statement to the election commission that explores how this script can be used for any election, with two examples for modifying the script.
