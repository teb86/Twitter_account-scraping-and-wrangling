# Twitter_account-scrapping-and-wrangling

<h3>Project:</h3>

I wrangled and analyzed data from Twitter user @dog_rates , also known as WeRateDogs. This Twitter account rates people's dogs with a humorous comment about the dog

<h3>Datasets:</h3>

* twitter_archive_enhanced.csv = contains many useful information, like the names of dogs, the stages, the timestamp the tweet ids, etc
* image_predictions.tsv = contains the results of a neural network analysis which gives the breed of dogs based on the image provided in the teweet
* twitter_counts.csv  = includes the two variables favorite_count and retweet_count, gathered from Twitter by using twitter api and then stored in a JSON file (tweet_json)

<h3>Packages:</h3>

Python 3 + pandas, numpy, requests, tweepy, json

<h3>Steps:</h3>

1. Steps to gathering data from twitter: 

The WeRateDogs Twitter archive contains basic tweet data for all 5000+ of their tweets, but not everything. I needed two more information for my analysis, favorite and retweet

- Using the tweet IDs in @dog_rates Twitter archive (Twitter_archive_enhanced.csv) , I queried the Twitter API for each tweet's JSON data using Python's Tweepy library

- Then, I stored each tweet's entire set of JSON data in a file called tweet_json.txt file

- Finally, I read this .txt file line by line into a pandas DataFrame with tweet ID, retweet count, and favorite count (twitter_counts.csv). 

Note that Twitter's API has a rate limit. Rate limiting is used to control the rate of traffic sent or received by a server. As per Twitter's rate limiting info page: Rate limits are divided into 15 minute intervals.
To query all of the tweet IDs, 20-30 minutes of running time can be expected. So, I used a used a code timer  and I also set the wait_on_rate_limit and wait_on_rate_limit_notify parameters to True in the tweepy.api class

2. The second part of this project focused on the assessment of the data gathered. This consists of identifying some structural (tidiness issues) and some content (quality) issues.

Many issues were erroneous data types, unnecessary columns (for our analysis), and untidy data.

3. In the third section of this project, I started by defining all the needed operations to handle the issues previously identified. Then, I began the cleaning operation and simultaneously testing the outcomes.

The cleaning consisted also of merging two tables, namely the tweet_archive_enhanced and
the tweet-image-prediction which were given a different name.

4. Finally, I stored the two remaining data sets into new csv files, respectively called twitter_archive_master and im_master.
