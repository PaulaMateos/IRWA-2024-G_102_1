# Part 1: Text Processing and Exploratory Data Analysis / 2024 UPF G_102_1

## Overview
This project focuses on text processing and exploratory data analysis (EDA) of tweets related to the Farmers' Protests. The aim is to analyze the content of tweets, uncover trends, and visualize key insights using various Python libraries. The project includes data loading, preprocessing, EDA, and visualization techniques to extract meaningful information from the dataset.

## Table of Contents
- [Usage](#usage)
- [Functionality](#functionality)
  - [1. Data Loading](#1-data-loading)
  - [2. Text Processing](#2-text-processing)
  - [3. Exploratory Data Analysis](#3-exploratory-data-analysis)
- [Prerequisites](#prerequisites)
- [Running the Code](#running-the-code)

## Functionality

### 1. Data Loading
The project begins by loading the required datasets from specified file paths. This includes tweets data in JSON format, a mapping of tweet document IDs, and evaluation data.

- **`Load Data`**:
  - Loads tweets from a JSON file.
  - Merges tweet data with document ID mappings for further processing.

### 2. Text Processing
Text preprocessing is crucial for effective analysis. The system preprocesses tweet content by removing stop words, punctuation, and applying stemming.

- **`preprocess_tweet(tweet_content)`**: 
  - Converts tweets to lowercase, removes stop words, and stems words.
  - Returns processed tweets as a string.

### 3. Exploratory Data Analysis
The EDA section explores various aspects of the tweet data through visualizations and statistical analysis.

- **Word Count Distribution**: Analyzes the distribution of word counts in tweets.
- **Vocabulary Size**: Calculates the unique vocabulary used in the tweets.
- **Top Retweeted Tweets**: Identifies the most retweeted tweets.
- **Word Cloud**: Visualizes the most frequent words in the tweets.
- **Entity Recognition**: Uses NLP to identify named entities in sample tweets.
- **Hashtag Frequency Treemap**: Visualizes the frequency of hashtags used in tweets.
- **Time Series Analysis**: Analyzes tweet activity over time.
- **Top Users by Tweet Count**: Identifies the most active users in terms of tweet volume.
- **Retweets vs Likes Correlation**: Analyzes the relationship between retweets and likes.
- **Heatmap**: Visualizes tweet activity patterns by hour and day of the week.

### Prerequisites
This project is designed to be run in Google Colab. Necessary datasets and libraries, including `nltk`, `matplotlib`, `pandas`, and `seaborn`, are pre-installed in the Colab environment.

### Running the Code
1. **Loading Datasets**
   Start by loading the necessary datasets and mapping tweet IDs:
   ```python
   evaluation = '/content/drive/Shared drives/IRWA/ProjectPart1/inputs/evaluation_gt.csv'
   farmers_tweets = '/content/drive/Shared drives/IRWA/ProjectPart1/inputs/farmers-protest-tweets.json'
   tweet_document_ids = '/content/drive/Shared drives/IRWA/ProjectPart1/inputs/tweet_document_ids_map.csv'
   ```

2. **Preprocessing Tweets**
   Apply preprocessing to clean and prepare tweet content:
   ```python
   for index, tweet in df_tweets.iterrows():
       df_tweets.at[index, 'processed_content'] = preprocess_tweet(tweet['content'])
   ```

3. **Performing Exploratory Data Analysis**
   Execute various EDA functions to gain insights from the tweet data:
   ```python
   # Example: Visualizing word count distribution
   df_tweets['word_count'].plot(kind='hist', bins=20, title='Word Count Distribution')
   plt.show()
   ```

### Example Analysis
You can visualize and analyze different aspects of the dataset as shown below:
```python
# Generate a word cloud
wordcloud = WordCloud(width=800, height=400, background_color='white').generate(' '.join(all_words))
plt.figure(figsize=(10, 5))
plt.imshow(wordcloud, interpolation='bilinear')
plt.axis('off')
plt.show()
```
