# P3 milestone

## Title
Testing Twitter computational social science propositions with Reddit dataset.

## Abstract
In the paper, the authors try to replicate 10 different propositions made in previous studies. Our goal is to take this idea further and test some of the propositions with another social media platform: Reddit. Reddit is different from Twitter in terms of user interaction. There isn’t the concept of followers. The idea is that users have a certain level of anonymity and can share and create content without it being linked to their real world identity. Therefore, it would be interesting to test if some of these propositions hold or not for this platform. Because we don’t have the concept of followers, follower-followee networks cannot be created. Therefore, we will only test the following 4 propositions:
- 20%-80% rule of content generation.
- Originality and sociability. (We are excluding syntactic use)
- Circadian rhythms.
- Attention and productivity.

Some of them will be reformulated to be applied to Reddit.

## Research Questions

- Does Reddit follow the 20/80 rule of content generation?
- What is the level of originality on Reddit and what are the most original subreddits?
- What is the level of sociability on Reddit and what are the subreddits with the highest level of sociability?
- Does Reddit activity follow circadian rhythms? 
- Does the number of upvotes affect the attention and productivity of users?

## Proposed dataset

The dataset to be used can be found at [May 2015 Reddit Comments](https://www.kaggle.com/reddit/reddit-comments-may-2015). The file to be downloaded contains an sql file of around 30Gb of data. This file should be used to populate a database, from which we will extract the data we need. The database table (it only contains one table) has a comment per row. In total it has around 54 million comments created during May 2015.

All the information we need is in this database.

## Methods

### Collection of users: 
We want to extract users randomly from this database table, similar to what was done in the Twitter paper. To accomplish that we take advantage of the column user_id in the database table, which indicates which user posted that comment. We can generate IDs randomly and then check which ones are valid based on whether or not they are found in the database. Our final dataset will contain the comments of our valid users.

### Features:
The database table has a total of 22 variables. To test our propositions we are only interested in created_utc (when the comment was created), subreddit_id, score_hidden (whether the score is hidden or not), subreddit, score and parent_id. Therefore, these are the only features we are going to extract from the database. With them, we can create a csv file to use for data analysis.

### Answer questions:
- ```20/80 rule```: we only need to know which comments each user created. With our extracted dataset, we just need to group it by user_id and obtain the count of rows per user. This will give the number of comments each user posted. We can then plot this information and test if it follows the 20/80 rule.
- ```Originality```: To measure originality we will use the formula number of posts / (number of posts + total number of comments) * 100. To obtain the posts we just need to consider the unique parent_ids of the root comments. The root comments are the ones whose parent_id starts with “t3_”. To evaluate this for subreddits we just need to compute the measure for each one and compare them.
- ```Sociability```: this would be given by the percentage of replies to comments (out of all comments). The replies are the comments whose parent_id starts with “t1_”. Replies to comments are all the ones that aren't root comments. To evaluate this for subreddits we just need to compute the measure for each one and compare them.
- ```Circadian rhythms```: we need the value of the column created_utc, which is the time the comment was created.
- ```Attention and productivity```: we will check if the score of a user affects how frequently he/she comments. We don’t have access to the complete score of a user, so we will consider the mean value of scores of all the user’s comments. Then, we can check whether or not users with higher scores also comment more frequently.

## Proposed timeline

```Week 1```: Download sql file, populate database and extract data to be used for analysis. Also, start data analysis on the data to answer the proposed questions.

```Week 2```: Finish data analysis and visualizations.

```Week 3```: Prepare data story and video.

## Organization within the team

```Dora```:
- Extract data from the database
- Data analysis on originality
- Prepare data story

```Haojun```
- Data analysis on 20/80 rule
- Data analysis on circadian rhythms
- Prepare data story

```Clément```
- Data analysis on attention and productivity
- Data analysis on sociability
- Prepare video


## Questions for TAs

We don't have any question.