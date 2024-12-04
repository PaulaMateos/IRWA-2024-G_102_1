# Information Retrieval and Web Analysis Final Project 2024 / UPF G_102_1

## Overview  
This project presents a comprehensive web-based application for information retrieval and web analysis. It leverages a custom-built search engine to process and analyze tweets related to the *Farmers' Protests* and offers real-time user interaction and sentiment analysis. The platform integrates user analytics, geographical data, and personalized dashboards, providing both search functionality and insightful visualizations. The goal is to explore user interactions, analyze document relevance, and track user engagement in a dynamic web environment.

---

## Table of Contents  
1. [Usage](#usage)  
2. [Functionality](#functionality)  
   - [Data Loading](#1-data-loading)  
   - [Search Engine and Text Processing](#2-search-engine-and-text-processing)  
   - [User Analytics](#3-user-analytics)  
   - [Dashboard and Visualizations](#4-dashboard-and-visualizations)  
   - [Sentiment Analysis](#5-sentiment-analysis)  
3. [Prerequisites](#prerequisites)  
4. [Running the Code](#running-the-code)

---

## Usage  
The application allows users to:  
- Search for tweets related to the Farmers' Protests using custom queries.  
- View search results with detailed information about each tweet.  
- Track and visualize user engagement statistics such as clicks, dwell time, and session activity.  
- Analyze user behavior based on browser, location, and device type.  
- Perform sentiment analysis on user-provided text.

---

## Functionality  

### 1. Data Loading  
The project begins by loading a corpus of tweets from a JSON file. The tweet data is indexed and stored in memory for fast retrieval during user searches.

- **`load_corpus(file_path)`**: Loads the JSON file containing tweet data. Each tweet is indexed by a unique document ID.  
- **Corpus Example**:  
```python
loaded corpus. first elem: {'id': 1, 'content': 'Protesters gather...', 'likes': 1200}
```

---

### 2. Search Engine and Text Processing  
The search engine allows users to search the tweet corpus using keywords. It preprocesses the text by removing punctuation, converting to lowercase, and applying stemming for better search accuracy.

- **Search Functionality**:  
   - Users submit queries through a web form.  
   - The search engine returns matching tweets ranked by relevance.  
   - Results include the tweet's content, date, and number of likes and retweets.

- **Text Preprocessing**:  
   - Converts tweets to lowercase.  
   - Removes stop words and punctuation.  
   - Stems words for normalization.

---

### 3. User Analytics  
The application captures and logs user activity for further analysis. Key features include:  

- **Session Tracking**:  
   Each user session is tracked using a unique session ID. The session captures user details like browser type, device type, and IP address.  

- **Geolocation**:  
   Uses the user's IP address to estimate their geographical location (city and country).  

- **Click and Dwell Time Logging**:  
   Tracks which search results users click and how long they engage with the content.  

- **Browser and Device Statistics**:  
   Aggregates user data to provide insights on the most common browsers, devices, and operating systems used.

---

### 4. Dashboard and Visualizations  
The dashboard provides real-time analytics on user engagement and document relevance. It includes:

- **Visited Documents**:  
   Displays a list of documents clicked by users, sorted by click count.  

- **Browser Statistics**:  
   Visualizes the distribution of browsers and devices used by visitors.

- **Location Statistics**:  
   Shows the geographical distribution of users based on city and country.  

- **Query Statistics**:  
   Tracks the most popular search queries and their frequency.  

- **Rank Distribution**:  
   Displays the average ranking positions of clicked documents, providing insights into search relevance.

---

### 5. Sentiment Analysis  
The application includes a sentiment analysis feature that allows users to analyze the sentiment of custom text input.

- **Sentiment Analysis Process**:  
   - Users input a text through a web form.  
   - The system uses the *VADER* SentimentIntensityAnalyzer from the *nltk* library to calculate a sentiment score.  
   - The sentiment score is displayed, indicating whether the text is positive, neutral, or negative.

---

## Prerequisites  
This project requires the following Python libraries:  
- `Flask`: For building the web application.  
- `SQLAlchemy`: For managing the database of user analytics.  
- `nltk`: For sentiment analysis.  
- `httpagentparser` and `user_agents`: For parsing user-agent data.  
- `geoip2`: For IP-based geolocation.  
- `matplotlib` and `seaborn`: For data visualization.  
- `requests`: For interacting with external APIs like ipinfo.io.

---

## Running the Code  

1. **Clone the Repository**:  
   Clone this project from the GitHub repository.  

2. **Install Dependencies**:  
   Install the required Python libraries using `pip`:  
   ```bash
   pip install Flask SQLAlchemy nltk matplotlib seaborn requests geoip2 user_agents httpagentparser
   ```

3. **Run the Application**:  
   Start the Flask web server to run the application:  
   ```bash
   python web_app.py
   ```

4. **Access the Application**:  
   Open your browser and navigate to `http://localhost:8088` to access the application.

---

## Example Analysis  

### Search and Document Click  
Users can search for tweets using a keyword like *"protest"*. The system returns a list of matching tweets, allowing users to click on any result to view detailed information.  

### Sentiment Analysis Example  
Users can enter a custom sentence, and the application will return a sentiment score:  

- Input: *"The protest was a success!"*  
- Sentiment Score: `0.88` (Positive)

---

This project showcases a complete pipeline for web-based information retrieval, user engagement analytics, and sentiment analysis, providing both technical depth and practical insights into user behavior and document relevance.
