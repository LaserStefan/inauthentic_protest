# inauthentic_protest
This is a collaborative project during the Digital Methods Initiative Summer School 2021

## Data  

### Included Datasets

So far, we included different data sets relating to the theme of #greenwashing. We use a multi-platform approach. This repository focuses on the most extensive dataset: Twitter data. The following sets are ranked by time and size.

- greenwashing_count. Time period: since 2006, when Twitter was established. This is a simple ```count``` dataset that gives us the tweets per day. We used this data to decide what our focus should be.
- **greenwashing**.  Time period: 01.01.2014 until 07.07.2021. This is the most extensive database which includes 943225 tweets. The most active day is 2019-12-02: 6831 tweets.
- **account_replies** We have multiple smaller files that only include replies to certain company accounts that are correlated with the term "greenwashing." This includes vw, hm, shell, and db/bahn.

All data sets were downloaded using twarc, using the script ```code/get_data.ipynb``` (see section [Getting data from Twitter](#getting-data-from-twitter)). The respective queries for each data set are stored in the folder ```code/queries```. Files are stored in a different repository that is not open to the public.

In this repository we store only the Tweet IDs and Conversation IDs of the Tweets and conversations that were included in the data analysis. We do not store full tweets, due to restrictions in the Twitter terms of use. Using the Tweet IDs stored in ```data/tweet-IDs```, you can "rehydrate" the corresponding tweets, using for example [twarc](https://scholarslab.github.io/learn-twarc/06-twarc-command-basics#rehydrate-a-dataset) by typing  

```twarc2 hydrate tweet_ids.txt > tweets_hydrated.jsonl```  

in your command line. Similarly, by using the [twarc conversations](https://twarc-project.readthedocs.io/en/latest/twarc2/#conversations) utility, you can retrieve all Tweets belonging to a converation ID  

```twarc2 conversations conversation_ids.txt conversations.jsonl```

### Getting data from Twitter

Data from Twitter can be scraped via the [Twitter v2 API](https://developer.twitter.com/en/docs/twitter-api/early-access). To get access to full archival search (i.e. be able to search for Tweets that were tweeted longer than one week ago), you will need ["academic access"](https://developer.twitter.com/en/products/twitter-api/academic-research) to the twitter API. Once you have access, scraping tweets is fairly easy, using for example the command line tool [twarc](https://twarc-project.readthedocs.io/en/latest/twarc2/#conversations). We provide scripts that scrape the data for our hashtag(s) of interest in the folder ```code```(see ```basic-twarc-code.txt``` and ```get_data.ipynb```).
