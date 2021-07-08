# Frequencies

This files briefly explains the main plots and their general meaning. See ```code``` to understand the reasoning

For a start, here are key frequencies from the ```greenwashing.csv``` dataset:

- greenwashing: 943225 Tweets
  max tweet_count    6831, : Name: 2019-12-02,
- 395542 users are tweeting about Greenwashing.
- 681353 users have provided a location

## Plots

- **greenwashing_freq_linear**: This plot displays all tweet activities from 2014 until today with a matplotlib line graph. It uses tweets per day as the basic unit. Included in the graph are annotations for three significant spikes. What we can see here is that discussions revolving around greenwashing are relatively new (also compared with the longer history of activities on Twitter). It is a significant term from 2018 onwards.
- **greenwashing_freq_linear_zoom**: By zooming in into the same data we get a more detailed view the most recent year of activities and spikes.
- **greenwashing_freq_log**: This plot presents an alternative view on the tweet activities since 2014, using a logarithmic scale and average tweet values for 7 days. Spikes are thus reduced, we can see the trend of growing activities from 2018 more clearly. Note that spikes are more difficult to acknowledge.
- **greenwashing_users_freq**: This is a rather boring plot, only showing one plot with total users. We might use the visualization for comparisons later. Now it simply displays the 395542 unique users.
- **greenwashing_follower_user**: The plot groups the users by followers. The majority of accounts have <1,000 users, yet a significant part of the users has >10,000 users. 
- **hashtag_correlation_greenwashing**: This matrix shows us co-hashtag occurence and draws on a mathematical model to display correlations between tweets. Credits go to [Our Coding Club and James](https://ourcodingclub.github.io/tutorials/topic-modelling-python/). The hashtags included in the ```entities.hashtags``` were collected and cleaned (merging similar hashtags, like Climatechange and climatechange). Correlations range from +1 until -1. This indicates probabilities, colours represent the values. A value of "0" implies no directed correlation, although hashtags might appear together. Positive correlations imply that it is more likely that terms appear together, a negative correlation indicates that when x hashtag appears, it is less likely that a respective other hashtag occurs.
- **hashtag_correlation_greenwashing_heatmapz**: This is the same matrix, but with one additional visual clue. Apart from colouring correlations are also reflected through size. The same values are used for this calculation. In theory, this enables finding significant correlations more easily.
- **greenwashing_freq_interactive.html**: This gives the frequency of all tweets per hour in an interactive plotly file. Open the .html and zoom in/out. You may also implement this on websites.

