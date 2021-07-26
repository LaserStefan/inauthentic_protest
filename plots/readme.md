[![CC BY-NC-SA 4.0][cc-by-nc-sa-shield]][cc-by-nc-sa]

This work is licensed under a
[Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License][cc-by-nc-sa].

[![CC BY-NC-SA 4.0][cc-by-nc-sa-image]][cc-by-nc-sa]

[cc-by-nc-sa]: http://creativecommons.org/licenses/by-nc-sa/4.0/
[cc-by-nc-sa-image]: https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png
[cc-by-nc-sa-shield]: https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg

# Frequencies

This files briefly explains the main plots and their general meaning. See ```code``` to understand the reasoning

For a start, here are key frequencies from the ```greenwashing.csv``` dataset:

- greenwashing: 943225 Tweets
  max tweet_count    6831, : Name: 2019-12-02,
- 395542 users are tweeting about Greenwashing.
- 681353 users have provided a location

## Plots
The code for these plots can be found in ```code```.

- **Wordtrees_entire_dataset**: This folder presents results from wordtrees from the main dataset.
- **greenwashing_follower_...**: Three graphs illustrate the differences between the users that are shaping certain events.
- **greenwashing_types**: Comparing the types of tweets across different events.
- **greenwashing_verified**: Comparing the types of accounts (verified/non-verified) across different events.
- **greenwashing_lang**: Comparing the languages used across different events.
- **greenwashing_tweet_types**: Comparing the types of tweet through events. Bar plot.
- **greenwashing_freq_stacked**: This is a time series plot that we used for the presentation. Created by density design scholars.
- **twitter_keywords_entire_dataset**: Time series subplots comparing keywords used during one year.
- **Greenwashing_alldates_slope_truth**: Slope chart comparing keywords across events. We used events from both our Twitter research and the larger research project. Note that the distance on the x axis is not true to scale.
- **profile_pictures_time_series**: This is a creative time series graph created by density design scholars exploring the active users through profile pictures.
- **greenwashing_freq_linear**: This time series plot displays all tweet activities from 2014 until today with a matplotlib line graph. It uses tweets per day as the basic unit. Included in the graph are annotations for three significant spikes. What we can see here is that discussions revolving around greenwashing are relatively new (also compared with the longer history of activities on Twitter). It is a significant term from 2018 onwards.
- **greenwashing_freq_linear_zoom**: By zooming in into the same data we get a more detailed view the most recent year of activities and spikes.
- **greenwashing_freq_log**: This plot presents an alternative view on the tweet activities since 2014, using a logarithmic scale and average tweet values for 7 days. Spikes are thus reduced, we can see the trend of growing activities from 2018 more clearly. Note that spikes are more difficult to acknowledge.
- **greenwashing_users_freq**: This is a rather boring plot, only showing one plot with total users. We might use the visualization for comparisons later. Now it simply displays the 395542 unique users.
- **greenwashing_follower_user**: The plot groups the users by followers. The majority of accounts have <1,000 users, yet a significant part of the users has >10,000 users. 
- **greenwashing_freq_interactive.html**: This gives the frequency of all tweets per hour in an interactive plotly file. Open the .html and zoom in/out. You may also implement this on websites.

## Networks

- **Greenwashing_mentions_network_regions:** Presents a Twitter mention network (autor – mentions) using Gephi. Forceatlas2 was used, thus filtering and showing only the most referenced accounts (<2% of all accounts in the data), and adjusting size through the pagerank algorithm. Clusters were stretched and coloured manually. In short, the network highlights regional/language clusters, with strong separate networks for French, Spanish, Great-British and German discussions. The European Union forms a strong semi-separate hub. In the middle of all interactions are a) activists like Thunberg and NGOs such as Greenpeace, b) news outlets, and c) large multinational companies, Shell being the most mentioned all-together. Interestingly, there is one strong separate hub of critical voices that assemble around palm oil and agriculture, which is very direct in addressing actors like the European Union.

