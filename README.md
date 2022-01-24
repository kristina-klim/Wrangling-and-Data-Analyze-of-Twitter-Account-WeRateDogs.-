# Wrangling and Data Analyze of Twitter Account “WeRateDogs”
## Introduction
People love their pets; they love sharing pictures of their pets on social media. WeRateDogs goes further and rates dogs’ images by a fair system. And it is almost always cute and fun.

Real-world data rarely come clean. Using Python and its libraries, we will gather data from various sources and in a variety of formats, assess its quality and tidiness, then clean it. This is called data wrangling.

We will be wrangling the dataset is the tweet archive of Twitter user @dog_rates, also known as WeRateDogs. WeRateDogs is a Twitter account that rates people's dogs with a humorous comment about the dog. These ratings almost always have a denominator of 10. The numerators, though? Almost always greater than 10. Why? Because "they're good dogs Brent."

**Data contains three pieces of separate data frames.**
- twitter_archive: the dataset were downloaded by WeRateDogs and sent to Udacity directly. Data set contains information about tweets: ID, timestamp, post texts, information about retweets, URLs, ratings (numerators and denominators), names and dog "stage" (doggo, floofer, pupper, and puppo)
- Image Predictions File: Udacity mentor ran every image in the WeRateDogs Twitter archive through a neural network that can classify breeds of dogs, and as a result, we have data with tweet_id, image URL, image number, and information of 3 predictions algorithms.
- tweet_json.txt: contains each tweet's retweet count and favorite ("like") count

## The project consists of the steps listed below:
- 1: Gathering data
- 2: Assessing data
- 3: Cleaning data
- 4: Storing data
- 5: Analyzing, and visualizing data
- 6: Reporting

Data Gathering We will gather tree files by the different methods.
- First, twitter_archive_enhanced.csv: is directly download and read by pd.read_csv() function.
- Second, image prediction file: required to use requests.get() and pd.read_csv() functions.
- Third, originally were required to use Twitter API, but recently Twitter chanced it, and we downloaded tweet_json.txt directly.


## Analyzing and Visualizing Data
In this section, we will answer the following question:
- Q1: What are the most common breeds found by the neural networks?
- Q2: What is the best time to post tweets for being more favorite? 
- Q3: Is there a correlation between retweet_count and favorite_count?

## Summarize the analyzing and visualizing process.
![image](https://user-images.githubusercontent.com/84743536/150867424-191c40af-2dae-47ba-b2ba-5af0b9c3d259.png)

After using the plot_bar function and visualizing the most common breeds for each prediction, we conclude that Golden Retriever is the most common breed. But other questions remain open: Golden Retriever is the most common breed because it is easy for a neural network to recognize or just because it has more tweets in general.

![image](https://user-images.githubusercontent.com/84743536/150867489-924ad972-7370-4498-b30d-e77efe74c47d.png)

We build an excellent visualization for question two, with a time of day on the x-axis and favorites on the y-axis. According to the plot, the best time for posting tweets is 12 am to 2 am and between 4 pm and 5 pm. But we can see a huge gap between 6 am and 3 pm. Why is that? Not enough data? Corrupt data? Incorrect cleaning process?

![image](https://user-images.githubusercontent.com/84743536/150867530-8b2756d4-1846-42d9-9f5f-67fd7e151cc9.png)

And last but not least, the correlation between retweet_count and favorite_count. The Pearson correlation test shows a coefficient of 0.77, a strong positive correlation. But on the plot, we can see a strong correlation just before 1500 retweets.


