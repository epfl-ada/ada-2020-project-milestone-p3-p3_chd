# P3 milestone

## Title
Testing social science propositions on Reddit.

## Abstract
In the paper, the authors try to replicate 10 different propositions made in previous studies. Our goal is to take this idea further and test some of the propositions with another social media platform: Reddit. Reddit is different from Twitter in terms of user interaction. There isn’t the concept of followers. The idea is that users have a certain level of anonymity and can share and create content without it being linked to their real world identity. Therefore, it would be interesting to test if some of these propositions hold or not for this platform. Because we don’t have the concept of followers, follower-followee networks cannot be created. Therefore, we will only test the following 3 propositions:
- 20%-80% rule of content generation.
- Sociability. (We are excluding syntactic use and originality)
- Attention and productivity.

Some of them will be reformulated to be applied to Reddit.

## Research Questions

- Does Reddit follow the 20/80 rule of content generation? Do subreddits follow the 20/80 rule?
- What is the level of sociability on Reddit? What is the level of sociability on subreddits? 
- Does the average score affect the attention and productivity of users?

## Proposed dataset

The dataset to be used can be found at [May 2015 Reddit Comments](https://www.kaggle.com/reddit/reddit-comments-may-2015). The file to be downloaded contains an sqlite file of around 30Gb of data. This file should be used to populate a database, from which we will extract the data we need. The database table (it only contains one table) has a comment per row. In total it has around 54 million comments created during May 2015.

All the information we need is in this database.

## Methods

### Collection of users: 
We want to extract users randomly from this database table. To accomplish that we take advantage of the column author in the database table, which indicates which user posted that comment. We will extract comments for a set of half a million users, which were chosen randomnly from the set of all users in the database.

### Features:
The database table has a total of 22 variables. To test our propositions we are only interested in author, subreddit, score and parent_id. Therefore, these are the only features we are going to extract from the database. With them, we can create a csv file to use for data analysis.

### Answer questions:
- ```20/80 rule```: we only need to know which comments each user created. With our extracted dataset, we just need to group it by author and obtain the count of rows per user. This will give the number of comments each user posted. We can then plot this information and test if it follows the 20/80 rule. The same can be done for the subreddits.
- ```Sociability```: this would be given by the percentage of replies to comments (out of all comments). The replies are the comments whose parent_id starts with “t1_”. Replies to comments are all the ones that aren't root comments. To evaluate this for subreddits we just need to compute the measure for each one.
- ```Attention and productivity```: we will check if the score of a user affects how frequently he/she comments. We don’t have access to the complete score of a user, so we will consider the mean value of scores of all the user’s comments. Then, we can check whether or not users with higher scores also comment more frequently.

## Proposed timeline

```Week 1```: Download sqlite file, populate database and extract data to be used for analysis. Also, start data analysis on the data to answer the proposed questions.

```Week 2```: Finish data analysis and visualizations.

```Week 3```: Prepare report and video.

## Organization within the team

```Dora```:
- Task 1: Extract data from the database
- Task 2: Data analysis on sociability
- Prepare part of the report related to tasks 1 and 2
- Prepare part of the video related to tasks 1 and 2

```Haojun```:
- Task 3: Data analysis on 20/80 rule
- Prepare part of the report related to task 3
- Prepare part of the video related to task 3

```Clément```:
- Task 4: Data analysis on attention and productivity
- Prepare part of the data report related to task 4
- Prepare part of the video related to tasks 4


## Questions for TAs

We don't have any question.

## Contributions

Everyone did their assigned tasks. Also, Dora wrote the abstract and introduction on the report and Clément wrote the conclusion.