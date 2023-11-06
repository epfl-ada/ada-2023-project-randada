# RandAda project: Movie title semantics

Team members : Aurèle Baretje, Blanche Kerorgant, Clarisse Pierre, Émilie Monnet, Alice Granboulan.

## Abstract (from Milestone 1 -> to modify)

A movie title is the first thing we discover about a movie, it is the hook that makes us want to see it. Therefore it needs to be carefully designed.

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

### IMdB dataset
To evaluate the success of a movie.
Less biased than box office revenues because we can use the average rating which is not (less ?) linked to the number of ratings or the popularity of an actor/director.

## Methods
### Imputation
Replace missing data with substituted values to avoid some biases.
[Wikipedia 'Imputation (statistics)'](https://en.wikipedia.org/wiki/Imputation_(statistics))

### NLP analysis
Use natural language processing techniques to extract keywords and topics from movie titles. Cluster movies based on similar title characteristics to identify patterns in successful movie titles.
Apply sentiment analysis to movie titles to determine the emotional tone conveyed by titles. Explore whether positive or negative sentiment in titles is associated with box office performance.

## Milestones
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
| x | x |

## Questions to mentor & TAs

