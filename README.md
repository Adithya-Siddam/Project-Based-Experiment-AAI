<H3>ENTER YOUR NAME: S Adithya Chowdary</H3>
<H3>ENTER YOUR REGISTER NO: 212221230100</H3>
<H3>DATE: 15-05-2024</H3>
<H1 Align="center">Project Based Experiment<H1>
<H3>Objective:<H3>
To perform sentiment analysis using your Facebook data and count the number of Occurrences of Your Name as well as finding the number of positive, negative and neutral comments based on sentiments.

<H3>Program:</H3>
```python
import pandas as pd
from textblob import TextBlob

data = pd.read_csv("fb_sentiment.csv")

given_name = "Adithya Chowdary"

sentiment_counts = {'positive': 0, 'negative': 0, 'neutral': 0}

name_occurrences = sum(post.lower().count(given_name.lower()) for post in data['FBPost'])

for post in data['FBPost']:
    polarity = TextBlob(post).sentiment.polarity
    sentiment_counts['positive'] += polarity > 0
    sentiment_counts['negative'] += polarity < 0
    sentiment_counts['neutral'] += polarity == 0

print("Sentiment Analysis Results:")
for sentiment, count in sentiment_counts.items():
    print(f"{sentiment.capitalize()} comments: {count}")

print(f"Occurrences of '{given_name}': {name_occurrences}")

```
<H3>Output:</H3>
![image](https://github.com/Adithya-Siddam/Project-Based-Experiment-AAI/assets/93427248/cfcfbbd3-6a1c-4f21-867e-43eddcb39f2b)
<H3>Inference:</H3>
By exploring sentiment analysis techniques and applying them to social media data, I gained practical experience in extracting sentiment information and identifying patterns in text. Additionally, counting occurrences of specific names enhanced my understanding of text processing and how to extract meaningful information from large datasets.

