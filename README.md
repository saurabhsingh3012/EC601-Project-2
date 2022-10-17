## EC601-Project-2
# Twitter Sentiment Analysis
## Saurabh Singh

### User Story
As a user, I want to know which movie is more popular so I can decide the movie I should buy the ticket for.

### MVP
To judge the popularity of a movie using sentiment analysis based on the number of mentions of the topic in tweets.

### Report
For safety reasons, I have not put the access codes for the program on the Github page and have replaces them with a string of ‘xxxxxxxxxxxxxxxxxxxxxx’.

For this project, I am using Tweepy to build a connection to Twitter API for Authentication and access to real-time tweets. Tweepy is an open source python package that gives you a way to access the twitter API using Python.

I am using TextBlob for NLP analysis as it is beginner friendly. Textblob is a Python library for processing textual data. It provides a simple API for using common NLP processing.

What TextBlob does is look at each word and determine whether the word is positive or negative, and then adds the sentiment of each word. But the simplicity of the model may create certain problems. For example, it might not analyze the words in the right context, thus giving a skewed result. For example, the words “not happy” may have some positive bias as the word ‘happy’ has positive sentiment. One way to overcome this problem is to use greater number of tweets. The more tweets we use, the more ‘accurate’ our results are bound to get. 

![Polarity by ana](https://github.com/saurabhsingh3012/EC601-Project-2/blob/main/Images/Screenshot%20(1044).png)
*Figure1. Polarity obtained by analysing 200 tweets*

![](https://github.com/saurabhsingh3012/EC601-Project-2/blob/main/Images/Screenshot%20(1045).png)
*Figure2. Polarity obtained by analysing 500 tweets*

As we can see from the above screenshots, the polarity is far greater for 500 tweets than for 200 tweets due to the greater number of tweets evaluated.

It is important to note that the language of the tweets should be specified in order to get ‘proper’ results. This is because sentiment analysis on TextBlob only gives accurate results for English texts.

Another thing to note is that Twitter’s search service and, by extension, the Search API is not meant to be an exhaustive source of Tweets. Not all Tweets will be indexed or made available via the search interface. So there would also be some biases in the tweets scanned.

It is important to use the text method defined in tweepy, otherwise the return value of the library would contain parameters that are not required for NLP analysis. This can be seen from the screenshots below.

![](https://github.com/saurabhsingh3012/EC601-Project-2/blob/main/Images/Screenshot%20(1046).png)
*Figure3.*

![](https://github.com/saurabhsingh3012/EC601-Project-2/blob/main/Images/Screenshot%20(1047).png)
*Figure4.*

Tweets are usually quite messy as they contain ‘mentions’, URLS, tags, hyperlinks, etc. The TextBlob algorithm prefers ‘pure text’ to be passed to it to be analyzed. Thus, the tweets have to be cleaned. The cleaned tweets are shown in the figure below. 

![](https://github.com/saurabhsingh3012/EC601-Project-2/blob/main/Images/Screenshot%20(1048).png)
*Figure5.*

As discussed earlier, the results of the NLP processor usually have a positive bias. Thus in order to determine sentiment of the tweets, we can set an empirical threshold that could used as to determine the ‘absolute’ sentiment of a tweet. This also happens partly because generally tend to avoid using nrgative terms. For example, instead of using the term ‘bad’, people usually use ‘not good’, which has a slight positive bias. But as we are comparing the polarities of two separate keyword searches, the biases within the results could be assumed to be roughly the same, which in turn would be ineffective when comparing the results of the topics as we are.

The final result of the program is given below, where I am comparing the movies ‘superman’ and ‘batman’. 

![](https://github.com/saurabhsingh3012/EC601-Project-2/blob/main/Images/Screenshot%20(1049).png)
*Figure6.*
