# Title to success

Team members : Aurèle Baretje, Blanche Kerorgant, Clarisse Pierre, Émilie Monnet, Alice Granboulan.


Datastory : https://blanchek.github.io/MovieTitles/movies-titles/

## Abstract

How is a movie title designed? A movie title is the first thing we discover about a movie, **it is the hook that makes us want to see it**. Therefore it needs to be carefully designed.

While a compelling title doesn't guarantee the success of your movie, it plays a crucial role in attracting the attention of the public. An intriguing title serves as a gateway to getting your film noticed, establishing an initial link with the audience who will be more inclined to go to the cinema to see it.

We plan to analyze if a movie title can be linked to its **success**. We will study how explicit titles are by comparing them to plot summaries. We will examine the impact of factors like length or including the protagonist's name. Moreover, we will try to draw the different title strategies for different **movie genres**. Finally, we will do a **time series analysis**.


## Research questions
### Time series analysis
Does the parameters of title (length, lexical fields, abstractness) evolve through time? 

### Success
Does the length of a movie title influence its success? How to evaluate the cofounders of movie success parameters?
What is the influence of the employed vocabulary? Should it be formal or colloquial?
Does a title need to be explicit about the plot of the movie?
What is the influence of the presence of the main character name in the title?

### Movie genre
Is movie title length linked to its genre?
Are they specific lexical fields according to movie genre?
Can we correlate the sentiment analysis of the title with the one of the full movie summary?

## Datasets
### CMU Movie Summary Corpus dataset
Data cleaning : 
- remove movies without title
- remove movies lasting less than one hour ([Wikipedia 'Feature film' definition](https://en.wikipedia.org/wiki/Feature_film)).
- remove movies released after 2012, as the CMU database was extracted from Freebase and Wikipedia in 2012.
- keep only movies with English language to get only titles in English because the semantic analysis will be in English.


Data preprocessing :
- group movies in 19 principal genres.
- add the list of characters for each movie from the CMU character metadata dataset.

### Additional datasets
#### Ratings
For the success analysis, using the `Box office revenues` parameter introduces a bias (because it is impacted by actor popularity for example). Additional datasets provide other success parameters with different cofounders (ratings).

[IMdB](https://developer.imdb.com/non-commercial-datasets/) : to evaluate the success of a movie based on **IMDb average rating** and **number of votes** for more than a million movies and series.

The link between the pre-processed CMU and IMDb datasets is made using 3 matching criteria: `Movie Name`, `Movie Release Date` and `Movie Runtime`. This brings us to about 13'825 matches out of 26'772 movies in the CMU dataset.

[Rotten Tomatoes](https://www.kaggle.com/datasets/stefanoleone992/rotten-tomatoes-movies-and-critic-reviews-dataset) : to evaluate the success of a movie based on **regular users ratings** (audience score) and **critics ratings** (tomatoscore).

The link between the pre-processed CMU and Rotten tomatoes datasets is made using 3 matching criteria: `Movie Name`  `Movie Release Date` and `Movie Runtime`. This brings us to about 2'549 matches out of 26'772 movies in the CMU dataset.

#### Financial
For the success analysis, we also want to investigate the financial success of a movie. The `Box office revenues` and `Budget` parameters will be used to do so. 

[Budget](https://www.kaggle.com/datasets/rounakbanik/the-movies-dataset) : import the `Budget` parameter as it is not present in the CMU dataset parameters. Budget info is used to calculate movie profit, which can be useful to analyse the movie success. This dataset was collected from TMDB and GroupLens.  

The link between the pre-processed CMU and xx datasets is made using 2 matching criteria: `Movie Name` and `Movie Release Date`. This brings us to about 779 matches out of 2'966 movies in the CMU-IMdB dataset (processed to keep only movies with box office data).

[CPI](https://stats.oecd.org/index.aspx?DataSetCode=PRICES_CPI#) : Consumer Price Indexes (CPI) were used to adjust movie box office revenues and film budgets for inflation rates spanning from 1913 to 2012. This dataset was sourced from OECD.stat.


#### Actor's fame
[Top100 actors](https://m.imdb.com/list/ls058011111/) To identify the 100 most famous actors of all time, a list was compiled from IMdB : top100 actors of all time.

## Methods
### NLP analysis
Use natural language processing techniques to extract keywords, entities (NER) and topics from movie titles. Cluster movies based on similar title characteristics to identify patterns in successful movie titles.

Apply sentiment analysis to movie titles to determine the emotional tone conveyed by titles. Explore whether positive or negative sentiment in titles is associated with box office performance.

### Machine Learning
Use Machine Learning to predict the movie genres using its title (for titles with more than 2 words). 


## Proposed timeline
### Until Project milestone 2

|    | Tasks |
| -----| :------- |
| Week 1 (30.10-05.11)  | <ul><li>Precise definition of the research questions.</li><li>Data scraping, pre-processing and dataset construction.</li></ul> |
| Week 2 (06.11-12.11)  | <ul><li>Creation of a ratings dataframe: merging the CMU dataset with IMdB dataset and/ot Rotten tomatoes dataset. Process of datasets linked financial success.</li><li>Getting familiar with NLP libraries.</li><li>Data crawling if important information is missing.</li></ul> |
| Week 3 (13.11-17.11)  | First clustering and first visualizations.  |

### Until Project milestone 3

|    | Tasks |
| -----| :------- |
| Week 4 (20.11-26.11)  | Classifying movies into sentiments from their title and from their plot using NLP. |
| Week 5 (27.11-03.12)  | <ul><li>Clustering and visualizations.</li><li>Brainstorm for the datastory.</li></ul> |
| Week 6 (04.12-10.12)  | Detailed analysis for each research question. Finalization of the graphs. |
| Week 7 (11.12-17.12)  | Design the data story website. |
| Week 8 (18.12-22.12)  | Stick all the pieces together |

## Organization within the team
|  Teammate  | Contributions (until week 3) |
| -----| :------- |
| Aurèle | CMU dataset preprocessing. |
| Émilie | CMU dataset preprocessing. |
| Clarisse | Choice of NLP tools and libraries. NLP first sentiment analysis visualizations. |
| Blanche | Financial success dataset preprocessing. Financial success & cofounders first visualizations. |
| Alice | Research questions. Rating datasets preprocessing. Success & genre first visualizations. |
