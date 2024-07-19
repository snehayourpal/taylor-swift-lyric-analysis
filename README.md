# taylor-swift-lyric-analysis
Data analysis and NLP Sentiment Analysis project analyzing Taylor Swift lyrics

# Taylor Swift Lyrics Analysis

## Overview
On October 21, 2022, Taylor Swift released her new album, *Midnights*. To see if she hinted about this album in her previous works, we analyzed all her lyrics. This project involves exploring her references to 'midnight', 'day', 'night', and 'time' in general. We also perform sentiment analysis to study her tone over her career and determine if she writes more favorably about day or night.

## Dataset
The dataset, compiled by Jan Llenzl Dagohoy and published on Kaggle, contains all of Taylor Swift’s albums up to October 20, 2022, including:
- Taylor Swift
- Fearless
- Speak Now
- Red
- 1989
- reputation
- Lover
- Folklore
- evermore

## Project Steps

### Load and Inspect Data
1. **Load the dataset**: Using pandas, load the dataset `taylor_swift_lyrics_2006-2020_all.csv`, save it as `lyrics`, inspect the first few rows, and use `.info()` to check the number of rows, missing values, and variable types.

### Add Essential Data
2. **Add year column**: Apply a function to the `lyrics` DataFrame to fill in the year based on the album name.

### Clean the Lyric Text
3. **Clean lyrics**: Lowercase all text, remove punctuation, exclude stop words, and save the cleaned text in a new column called `clean_lyric`.

### Find Keyword Mentions
4. **Count 'midnight' mentions**: Create a new column indicating if a lyric contains 'midnight' and check the count.

### Expand the Keyword List
5. **Expand search**: Create lists of 'night' and 'day' words, join them into regular expression strings, and create columns for each word category. Count occurrences and inspect the DataFrame.

### Visualize and Investigate the Data
6. **Visualize changes over time**: Create a `yearly_mentions` DataFrame that groups mentions by year and sums the columns. Plot a line chart showing night mentions over time.
7. **Identify focused albums**: Add album names back to the DataFrame, sort by night and day mentions, and identify the most focused albums.
8. **Compare day to night mentions**: Create a line chart comparing night and day mentions.
9. **Investigate position within albums**: Create a variable indicating the position of a lyric within an album, group by album position, and plot mentions as a position within the album.

### Sentiment Analysis
10. **Tokenize lyrics**: Tokenize the cleaned lyrics using the `word_tokenize` function from NLTK, and apply it to every row in the DataFrame with a lambda expression. Inspect the first few rows of the `lyrics` DataFrame.
11. **Count tokens**: Create a list of all the tokens in the `lyrics_tok` column, use the `Counter` function from the `collections` package to count the number of times each word appears, and sort the resulting dictionary.
12. **Analyze lyric sentiment**: Use the pre-trained sentiment classifier from NLTK to analyze sentiment. Apply the sentiment analyzer to the `clean_lyric` column with a lambda expression, and transform the dictionary into columns in the DataFrame.
13. **Corpus sentiment analysis**: Calculate the overall sentiment of her entire collection using the `pos`, `neg`, and `compound` columns. Visualize the overall sentiment of her albums over time using `groupby` and matplotlib.
14. **Day or Night? Positive or Negative?**: Create two DataFrames for lyrics mentioning night and day, respectively. Calculate and compare the sentiment for both using the `compound` value.
