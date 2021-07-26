# inauthentic_protest
This is a collaborative research project resulting from the Digital Methods Initiative Summer School 2021. It uses methods from data analytics and brings in interpretative social science methods. The main report of the research group is published on the DMI Wiki website. The original name of the project was "Inauthentic Protest?", emphasizing the ambigious nature of protest language on social media and the web. During the course of the project, we shifted the focus on the case of Greenwashing accusations, where inauthenticity is negotiated on multiple layers.

### Group Members

Stefan Laser (facilitator), Maria Lompe, Suay Melisa Ozkula, Estrid Sørensen, Lena Teigeler, Mariangela Vespa, Tianshi Zhao, Xinyue Chen. Designers: Matteo Bettini, Valentina Pallacci, Fabiola Papini, Marìa Paula Vargas Triana.

## Data  

### Included Datasets

We included different data sets relating to the theme of #greenwashing. We use a multi-platform approach and split the work into two groups. This repository focuses on the most extensive dataset: Twitter data. The following sets are ranked by time and size.

- **greenwashing_count**. Time period: since 2006, when Twitter was established. This is a simple ```count``` dataset that gives us the tweets per day. We used this data to decide what our focus should be.
- **greenwashing**.  Time period: 01.01.2014 until 07.07.2021. This is the most extensive database which includes 943225 tweets. The most active day is 2019-12-02: 6831 tweets.
- **account_replies**. We have multiple smaller files that only include replies to certain company accounts that are correlated with the term "greenwashing." This includes vw, hm, shell, and db_bahn.
- **greenwashing_correlated_hashtags**. From the main dataset (greenwashing) we took the top and most relevant correlated hashtags and queried twitter activity for June 2021. This gave us a dataset representing climate change discussions.

Drawing on the basic dataset, smaller sets were produced that allow specific analysis:

- **greenwashing_top_hashtags**:  Provides a list of top hashtags.

- **greenwashing_most_active_users**: Presents a users ranked by activity.

- **greenwashing_urls**: Outputs all urls as a list.

- **topicmodeling**: This is based on LDA topic-modeling and uses probabilities of co-occurrence. Words are tokenized and lemmatized (cutting it to its bare minimum). The selection of the number of categories is subjective. Topic modelling was conducted both for this Twitter group and the second group of the larger research project. We tested the datasets prior to select the model with the best number of topics. The results indicate that fewer topics producer more coherent topic models. The best model for the Twitter data is k=5 topics. However, we compared the results of various sizes (from k=3 to k=100) quantitatively (looking at coherence via GridSearchCV) and qualitatively (interpreting classifications) to explore the robustness of results and detect prevalent themes that might fall through the cracks. The results of the test and the main result (presented via PyLDAvis) can be found in ```data```. 

  Group 1:

  Best Model's Params: {'learning_decay': 0.7, 'n_components': 5}
  Best Log Likelihood Score: -7815893.048581155
  Model Perplexity of the best topic: 2524.550237801022

  Group 2:
  Best Model's Params: {'n_components': 5}
  Best Log Likelihood Score: -1688114.8155490216
  Model Perplexity of the best topic: 1664.793701726140

All data sets were downloaded using twarc, using the script ```code/Greenwashing_get_and_freq_clean``` (see section [Getting data from Twitter](#getting-data-from-twitter)). Files are stored in a different repository that is not open to the public.

In this repository we store only the Tweet IDs and Conversation IDs of the Tweets and conversations that were included in the data analysis. We do not store full tweets, due to restrictions in the Twitter terms of use. Using the Tweet IDs stored in ```data/tweet-IDs```, you can "rehydrate" the corresponding tweets, using for example [twarc](https://scholarslab.github.io/learn-twarc/06-twarc-command-basics#rehydrate-a-dataset) by typing  

```twarc2 hydrate tweet_ids.txt > tweets_hydrated.jsonl```  

in your command line. Similarly, by using the [twarc conversations](https://twarc-project.readthedocs.io/en/latest/twarc2/#conversations) utility, you can retrieve all Tweets belonging to a converation ID  

```twarc2 conversations conversation_ids.txt conversations.jsonl```

### Getting data from Twitter

Data from Twitter can be scraped via the [Twitter v2 API](https://developer.twitter.com/en/docs/twitter-api/early-access). To get access to full archival search (i.e. be able to search for Tweets that were tweeted longer than one week ago), you will need ["academic access"](https://developer.twitter.com/en/products/twitter-api/academic-research) to the twitter API. Once you have access, scraping tweets is fairly easy, using for example the command line tool [twarc](https://twarc-project.readthedocs.io/en/latest/twarc2/#conversations). We provide scripts that scrape the data for our hashtag(s) of interest in the folder ```code```(see ```get_data.ipynb```). 

### More Information

More information on plots can be found in the ```readme.md``` in the ```plots``` folder. 

