# Title to success

Team members : Aurèle Baretje, Blanche Kerorgant, Clarisse Pierre, Émilie Monnet, Alice Granboulan.


Datastory : https://blanchek.github.io/MovieTitles/movies-titles/

Website github : https://github.com/BlancheK/MovieTitles

## Abstract

How is a movie title designed? A movie title is the first thing we discover about a movie, **it is the hook that makes us want to see it**. Therefore it needs to be carefully designed.

While a compelling title doesn't guarantee the success of your movie, it plays a crucial role in attracting the attention of the public. An intriguing title serves as a gateway to getting your film noticed, establishing an initial link with the audience who will be more inclined to go to the cinema to see it.

We plan to analyze if a movie title can be linked to its **success**. We will study how explicit titles are by comparing them to plot summaries. We will examine the impact of factors like length or including the protagonist's name. Moreover, we will try to draw the different title strategies for different **movie genres**. Finally, we will do a **time series analysis**.


## Research questions
### Time series analysis
Does the parameters of title (length, lexical fields, abstractness) evolve through time? 

### Success
Does the length of a movie title influence its success? How to evaluate the confounders of movie success parameters?
What is the influence of the employed vocabulary? Should it contain verbs or nouns?
Should a title convey a positive or negative sentiment?
What is the influence of the presence of a protagonist name in the title?

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
For the success analysis, using the `Box office revenues` parameter introduces a bias (because it is impacted by actor popularity for example). The IMdB dataset provides an other success parameter with different confounders (ratings).

[IMdB](https://developer.imdb.com/non-commercial-datasets/) : to evaluate the success of a movie based on **IMDb average rating** and **number of votes** for more than a million movies and series.

The link between the pre-processed CMU and IMDb datasets is made using 3 matching criteria: `Movie Name`, `Movie Release Date` and `Movie Runtime`. This brings us to about 13'825 matches out of 26'772 movies in the CMU dataset.

#### Financial
For the success analysis, we also want to investigate the financial success of a movie. The `Box office revenues` and `Budget` parameters will be used to do so. 

[Budget](https://www.kaggle.com/datasets/rounakbanik/the-movies-dataset) : import the `Budget` parameter as it is not present in the CMU dataset parameters. Budget info is used to calculate movie profit, which can be useful to analyse the movie success. This dataset was collected from Full MovieLens.  

The link between the pre-processed CMU and Full MovieLens datasets is made using 2 matching criteria: `Movie Name` and `Movie Release Date`. This brings us to about 779 matches out of 2'966 movies in the CMU-IMdB dataset (processed to keep only movies with box office data).

[CPI](https://stats.oecd.org/index.aspx?DataSetCode=PRICES_CPI#) : Consumer Price Indexes (CPI) were used to adjust movie box office revenues and film budgets for inflation rates spanning from 1913 to 2012. This dataset was sourced from OECD.stat.


#### Actor's fame
[Most famous actors of all times](https://m.imdb.com/list/ls058011111/)  We select a list of the 100 most famous actors, tu disciminate movies with famous or not famous actors.

#### Director's fame
[Most famous directors of all times](https://thecinemaarchives.com/2020/08/17/the-250-best-directors-of-all-time/)  We select a list of the 50 most influential directors, to discriminate movies directed by famous or not famous directors.

#### Studio's fame
[Most important movie production compagnies of all times](https://en.wikipedia.org/wiki/Major_film_studios#:~:text=Today%2C%20the%20Big%20Five%20majors,to%20afford%20to%20watch%20films) A list of famous movie studios was designed to discrimate movies produced by famous or not famous studios. The information of the studio production of each movie was found on the [additionnal dataset](https://www.kaggle.com/datasets/rounakbanik/the-movies-dataset).

## Methods
### NLP analysis
Use natural language processing techniques to extract keywords, entities (NER) and topics from movie titles. Cluster movies based on similar title characteristics to identify patterns in successful movie titles.

Apply sentiment analysis to movie titles to determine the emotional tone conveyed by titles. Explore whether positive or negative sentiment in titles is associated with box office performance.

Genre lexical fields => Clarisse

### Machine Learning
Use Machine Learning to predict the movie genres using its title (for titles with more than 2 words). 

Random forest => Aurèle

## Project timeline

|    | Tasks |
| -----| :------- |
| Week 1 (30.10-05.11)  | <ul><li>Precise definition of the research questions.</li><li>Data scraping, pre-processing and dataset construction.</li></ul> |
| Week 2 (06.11-12.11)  | <ul><li>Creation of a ratings dataframe: merging the CMU dataset with IMdB dataset and/ot Rotten tomatoes dataset. Process of datasets linked financial success.</li><li>Getting familiar with NLP libraries.</li><li>Data crawling if important information is missing.</li></ul> |
| Week 3 (13.11-17.11)  | First clustering and first visualizations.  |
| Week 4 (20.11-26.11)  | <ul><li>Classifying movies into sentiments from their title and from their summary using NLP.</li><li>Additional datasets for confonders.</li></ul> |
| Week 5 (27.11-03.12)  | <ul><li>Brainstorm for the datastory.</li><li>Extraction of lexical fields and movie genre prediction.</li></ul> |
| Week 6 (04.12-10.12)  | Detailed analysis for each research question. Finalization of the graphs. |
| Week 7 (11.12-17.12)  | <ul><li>Design the data story website.</li><li>Success prediction tool based on title using random forest.</li></ul> |
| Week 8 (18.12-22.12)  | Stick all the pieces together |

## Organization within the team
|  Teammate  | Contributions (until week 3) |
| -----| :------- |
| Aurèle | <ul><li>CMU dataset preprocessing.</li><li>Confounders visualization</li><li>Prediction tool design.</li></ul> |
| Émilie | <ul><li>CMU dataset preprocessing.</li><li>Confounders visualizations & correlation analysis (statistical tests).</li><li>Final text for the data story.</li></ul> |
| Clarisse | <ul><li>Choice of NLP tools and libraries.</li><li>NLP sentiment and vocabulary analyses for title key features.</li><li>Genre prediction based on created lexical fields.</li></ul> |
| Blanche | <ul><li>Confounders datasets preprocessing.</li><li>Confounders visualizations.</li><li>Genre prediction based on created lexical fields.</li></ul> |
| Alice | <ul><li>Research questions. Rating datasets preprocessing.</li><li>Time series analysis of title key features.</li><li>Website design & creation interactive graphs.</li></ul> |
