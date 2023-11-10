# RandAda project: Movie title semantics

Team members : Aurèle Baretje, Blanche Kerorgant, Clarisse Pierre, Émilie Monnet, Alice Granboulan.

## Abstract

How is a movie title designed? A movie title is the first thing we discover about a movie, **it is the hook that makes us want to see it**. Therefore it needs to be carefully designed.

While a compelling title doesn't guarantee the success of your movie, it plays a crucial role in attracting the attention of the public. An intriguing title serves as a gateway to getting your film noticed, establishing an initial link with the audience who will be more inclined to go to the cinema to see it.

We plan to analyze if a movie title can be linked to its **success**. We will study how explicit titles are by comparing them to plot summaries. We will examine the impact of factors like length or including the hero's name. Moreover, we will try to draw the different title strategies for different **movie genres**. Finally, we will do a **time series analysis**.


## Research questions
### Success
Does the length of a movie title influence its success?
What is the influence of the employed vocabulary? Should it be sustained or colloquial?
Does a title need to be explicit about the plot of the movie?
What is the influence of the presence of the main character name in the title?

### Movie genre
Is movie title length linked to its genre?
Are they specific lexical fields according to movie genre?

### Time series analysis
Does the parameters of title evolve through time?

### Diversity
*We will not explore further this idea. Translation of movie titles in English in order to compare them is hard to achieve, and its accuracy is hard to evaluate.*

Are there any specific parameters for film titles depending on the country where the film was made? 
Analyze how movie titles change when they are translated into different languages or adapted for different regions. Do title translations impact the movie's reception?


## Datasets
### CMU Movie Summary Corpus dataset
Data cleaning : 
- remove movies lasting less than one hour ([Wikipedia 'Feature film' definition](https://en.wikipedia.org/wiki/Feature_film)).

### Additional datasets
[IMdB](https://developer.imdb.com/non-commercial-datasets/) : to evaluate the success of a movie based on **IMDb average rating** and **number of votes** for more than a million of movies and series.
It is less biased than box office revenues because we can use the average rating which is not (less ?) linked to the number of ratings or the popularity of an actor/director.
The link between the CMU movie ID with the IMDb movie ID is made using 3 matching criteria: `Movie Name`, `Movie Release Date` and `Movie Runtime`. This brings us to about x matches out of x films in the CMU dataset.

[Rotten Tomatoes](https://www.kaggle.com/datasets/stefanoleone992/rotten-tomatoes-movies-and-critic-reviews-dataset) : to evaluate the success of a movie based on **regular users ratings** (audience score) and **critics ratings** (tomatoscore).

*List the additional dataset(s) you want to use (if any), and some ideas on how you expect to get, manage, process, and enrich it/them. Show us that you’ve read the docs and some examples, and that you have a clear idea on what to expect. Discuss data size and format if relevant.*

## Methods
### Imputation
Replace missing data with substituted values to avoid some biases.
[Wikipedia 'Imputation (statistics)'](https://en.wikipedia.org/wiki/Imputation_(statistics))

### NLP analysis
Use natural language processing techniques to extract keywords and topics from movie titles. Cluster movies based on similar title characteristics to identify patterns in successful movie titles.
Apply sentiment analysis to movie titles to determine the emotional tone conveyed by titles. Explore whether positive or negative sentiment in titles is associated with box office performance.

*add other methods?*

## Proposed timeline
### Until Project milestone 2

|    | Tasks |
| -----| :------- |
| Week 1 (30.10-05.11)  | <ul><li>Precise definition of the research questions.</li><li>Data scraping, pre-processing and dataset construction.</li></ul> |
| Week 2 (06.11-12.11)  | <ul><li>Creation of a ratings dataframe: merging the CMU dataset with IMdB dataset and/ot Rotten tomatoes dataset.</li><li>Getting familiar with NLP libraries.</li><li>Data crawling if important information is missing.</li></ul> |
| Week 3 (13.11-17.11)  | First clustering and first visualizations.  |

### Until Project milestone 3

|    | Tasks |
| -----| :------- |
| Week 4 (20.11-26.11)  | Classifying movies into sentiments from their title and from their plot using NLP. |
| Week 5 (27.11-03.12)  | Clustering and visualizations. |
| Week 6 (04.12-10.12)  | Detailed analysis for each research question. Finalization of the graphs. |
| Week 7 (11.12-17.12)  | Design the data story website. |
| Week 8 (18.12-22.12)  | Stick all the pieces together |

## Organization within the team
|  Teammate  | Contributions |
| -----| :------- |
| Aurèle | CMU dataset preprocessing. |
| Émilie | CMU dataset preprocessing. |
| Clarisse | Choice of NLP tools and libraries. |
| Blanche | IMdB dataset preprocessing. First visualizations. |
| Alice | Research questions definition. IMdB dataset preprocessing |

## Questions to mentor & TAs

