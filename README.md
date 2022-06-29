# Data Science Project | The Impact of Donald Trump on the Public via Twitter


## Phase 1 - Project introduction

**Submitted by:**

* Matam Rodinsky
* Ron Hugi

**Research question:**
By using his tweeter account for over 11 years with a followers base of over 88 million former presidents of the USA Donald J Trump influenced the American people and the rest of the world on a variety of issues. Our research question is - on which subject did Trump have the most impact on public opinion?
**We intend:**
To dissect all 50K+ of Trump's tweets and find out by using unsupervised learning, which cluster of tweets had the most impact on public opinion over the years. We will achieve that by counting the number of likes and shares of each cluster.
**Features:**
7  columns are mentioned below:
ID – TYPE INT
TEXT – TYPE STRING
DATE – TYPE DATE
RETWEETS – TYPE INT
LIKES – TYPE INT
IS DELETED FROM TWEETER – TYPE BOOL
IS RETWEETED – TYPE BOOL
Instances:
 over 50,000 rows, each row will contain past tweets from Donald J Trump, the number of likes they received, retweets of them, and more.
**Data sources:**
The Trump Archive – A website that archived all of Donald Trump's tweets – 56,571 tweets from 2009 up until 2021 when Twitter blocked him from the platform.
https://www.thetrumparchive.com/
**Data mining methods:  **
Crawling from a website: thetrumparchive.com
Libraries – Selenium

**Planned visualizations: **
Two-dimensional visualizations including – tables, scatter plots, pie charts, etc.
**Planned models:**
Unsupervised learning - clustering, elbow, silhouette. 
**Validation methods:**
R^2.



## Phase 2 - Crawling with Selenium
Inside **scroll_inifint_page()** function we are:
* Open website with web driver
* Get the page height for calculations
* Continue to scroll until we calculate that we get all the infinite page
* Every 3 seconds we scroll, its 3 secs for the site will get that data from its server

Inside **get_from_page()** function we are:
* To get the number of the tweets we get the HTML element with CSS class "results___1pfEc"
* To get all the tweet data using the CSS class "tweet___2xXtA"
* For loop to get all the tweeets, in the "div" element there is a json with the data


## Phase 3 - Data Handling
### During this phase we created 4 functions that manipulate the data:

# Functions:
* **function tokenizeTweets** - returns a list of words that are tokenized without stopwords, stopwords are common words in English that do not give any information about the twite).
* **function cleanPunctuation** - cleaning punctuations from a twitte.
* **function cleanLinks** - cleaning any links for twitt.
* **function remove_emoji** - remove any emojis.
* **function stemming** - create a stemming word list from a word list that will insert into the function.
* **function lemmataizeSentance** - create a lemmataizing word list from a word list that will insert into the function.
* **function replace_empty_to_nan** And **remove_nan_rows** - cleans any empty rows that in the date frame.
* **function remove_unnecessary_data** - the main function in the phase, it calls all the phases to the twittes in the data frame by this stages: 
1) lower case all twitts
2) remove all emojis
3) clean the links
4) clean punctuation
5) tokenize twitts

create two dataframs for comparations df_stem - call stemming() , df_lemmatize - lemmataizeSentance()


## Phase 4 - Analyzing the data and clustering.
# Functions:
* **function create_clusters(df,number_of_clusters, colors ,title)** - using **Doc2Vec** algorithm to vectotize the given data frame, create the amount of given clusters with the givem colors. after vectorize we are using PCA algorithm the minimize the number of vectors to two so we can visualize it.

* **TfIDF code block** - there are a few blocks thet runs the same code but with different inputs, once with the twists that tokenized with **stemming** and once with **lemmataize**
![](Pictures/LemCluster.PNG)
![](Pictures/stCluster.PNG)

* **Cluster centroid** - print the centered word in each cluster that was created with Doc2Vec and  sum the like and the retweets each cluster got.

* **Print cluster** - Printing the clusters scatter plot - X = Retweets, Y = Likes
![](Pictures/TFIDF.PNG)


## LDA algorithm 

* **LDA code blocks** - Using LDA algorithm with both stemming & lemmatizing to compare the LDA module & the TF-IDF module word clusters

**Print the LAD Graph**  - 
* we can see the clusters, the words in each cluster, and בrosscheck information with different topics
* **The Slide Bar:**
* 1 = The frequency that the word accrued in the cluster 
* 0 = The frequency that the word accrued in the corpus divided by all the words in the corpus
![](Pictures/LDA.PNG)
