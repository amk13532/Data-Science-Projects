# Microsoft Box Office!

**Authors**: Matthe Gayanelo

## Overview

Due to the success of original content creation in various streaming platforms, Microsoft will be launching an in house movie studio. In order to optimize this venture, Microsoft has tasked us with conducting a data study that will produce actionable insights and guide them on creating optimum content. 

## Business Problem

Summary of the business problem you are trying to solve, and the data questions that you plan to answer to solve them.

There are several data sets available to preform insight analysis, and moreover several metrics that could define success. Fundamentally, this study will look to answer the following questions:

1. Which genres generated the highest amount of domestic revenue per movie?
2. Which genres had the highest measurable amount of engagement?
3. When an audience does engage, which genres garnered the most positive response?

In order to address these questions, the following will be used as succcess metrics:

1. Average Domestic Gross per Movie by Genre
2. Average Votes per Movie by Genre
3. Average Rating per Movie by Genre

A firm unerstanidng of these metrics will provide a holistic understanding of revenue generation, the measured emotional engagement of the audience, and how positive/negative nature of that audience engagement is.

## Data

In order to meet the time requirements, and achieve an optimal data study, the following data sets have been chosen to conduct our analytics:

IMDB Titles / Genre Classificaitons

Source: IMDB
Analytical Prupose: General Classification
Target Variable: 'tconst' (unique identifier) & 'genres'
Target Variable Use: 'tconst' will be used to match IMDB titles with IMDB Ratings in order to bucket the final dataset
IMDB Ratings

Source: IMDB
Analytical Prupose: Measure Engagement & Average Rating
Target Variable: 'tconst' (unique identifier), 'averagerating' & 'numvotes'
Target Variable Use: 'tconst' will be used to match IMDB titles with IMDB Ratings in order to bucket the final dataset, 'averagerating' will be used to measure positivity/negativity of engagement & 'numvotes' will be used to measure size of engagement
Box Office Movie Gross

Source: Box Office Mojo
Analytical Prupose: Measure Domestic Gross
Target Variable: 'title' & 'domestic gross'
Target Variable Use: 'title' will be used to merge this data set into the final data frame, while 'domestic gross' will be used to measure revenue generation on a per genre basis.
***

## Methods

Data Preparation: IMDB Titles / Genre Classificaitons (df_basics)
Variables Dropped / Created:

'updated_original_title' was created to mitigate 21 NaN Values in 'original_title'. Values in the 'updated_original_title' were derived from the 'primary_title' when available or the 'original_title' if found to be NaN. This column would act as a placeholder for future merges in the event that 'original_title' would be required

Missing/NaN Values Solutions:

5,408 rows were dropped due to the missing 'genres' data, since 'genres' were the main data point required from the set

2,072 rows were dropped due to being 'studio', 'year', and 'primary_title' duplicates.

31,739 NaN values were found in the 'runtime_minutes' column, but since this data point was not relevant to our core analytics these rows were left intact

Justification:

Data cleanup primarily focused on 'genres' and 'updated_primary_title' as the former would act as the main data point needed to bucket revenue, ratings, and votes in the IMDB ratings Data Set while the former would act as a potential unique identifier in future mergers. Dropping the selected rows was deemed permissable as this only comprised less than ~5% of the total database.
***

Data Preparation: IMDB Title Ratings (df_ratings)
Variables Dropped / Created:

None

Missing/NaN Values Solutions:

None

***

Data Preparation: IMDB Title Ratings (df_gross)¶
Variables Dropped / Created:

None

Missing/NaN Values Solutions:

28 'domestic_gross' line items dropped due to NaN values

Justification:

All other NaN values were retained as they would not influence the analytics moving forward

***

Data Preparation: Joining df_basics and df_ratings (df_titles_and_ratings)
Variables Dropped / Created:

Genre Columns: Genre categories were isolated into seperate columns to determine their isolated revenue, engagement and ratings metrics.

Weighted Score: Created to determine the weighted rating of each genre, basing the statistical weight of each movie by the votes garnered.

Missing/NaN Values Solutions:

All relevant missing data/NaN line items solved for before merge

***

Data Preparation: Creating df_rev_and_ratings (df_titles_and_ratings + df_gross)
Variables Dropped / Created:

'unique id': A unique identifier created out of the 'primary_title' and the 'year for df_gross and made out of the 'title' and 'year' for df_titles_and_ratings. This identifier will be used to merge both dataframes.

Missing/NaN Values Solutions:

All relevant missing data/NaN line items solved for before merge

***

Data Preparation: Creating the Final Aggregated Data Frame
Variables Dropped / Created:

'ADG per Movie' was created to determine the average Domestic Gross a movie in each genre would generate
'Average Votes per Movie' was created to determine to total amount of engagement each movie genre recieved per movie
'Total Movies' was created to help calculate the two metrics above
All NaN values in 'Domestic Gross' were dropped, due to this being the main data point
All 'No Genre' line items were dropped, as this was a nescessary unique classifier
'News' was dropped as a genre type as only 1 movie in our data set was categroized under this genre
Missing/NaN Values Solutions:

All relevant missing data/NaN line items solved for before merge

## Results

Evaluation & Conclusion

Our analysis has reuslted in the following findings:

1. Which genres generated the highest amount of domestic revenue per movie?

Scifi, Animation and Adventure dominate our per revenue analysis. Each genre averaged over 1 Billion Dollars in domestic gross, more than 2x the average across all Genres.

2. Which genres had the highest measurable amount of engagement?

Scifi, Adventure, and Western dominated our per voting/engagement analysis. In particular, Sci-Fi garnered an average 387k votes per movie, a staggering 2.5x the mean votes per genre. Adventure scored impressively as well, garnering ~228k votes, or 1.5x the mean votes per genre.

3. When an audience does engage, which genres garnered the most positive response?

Western, Biography, and History garnered the highest weighted scores, earning 7.52, 7.48 and 7.39 respectively. However, it is worth noting that the average weighted score for all genres rests at 7.06. This means that even our highest rated genre only scores 7% above the mean.

Moreover, Genre's that experienced success in the prior 2 metrics such as Scifi, Adventure and Animation all scored above the average (7.13, 7.06, and 7.13 respectively).

## Conclusions

Provide your conclusions about the work you've done, including any limitations or next steps.

***
Questions to consider:
* What would you recommend the business do as a result of this work?
* What are some reasons why your analysis might not fully solve the business problem?
* What else could you do in the future to improve this project?
***

## For More Information

For any additional questions, please contact **Matthew Gayanelo & matthew.gayanelo@gmail.coml*

## Repository Structure

Describe the structure of your repository and its contents, for example:

```
├── README.md                           <- The top-level README for reviewers of this project
├── dsc-phase1-project-template.ipynb   <- Narrative documentation of analysis in Jupyter notebook
├── DS_Project_Presentation.pdf         <- PDF version of project presentation
├── data                                <- Both sourced externally and generated from code
└── images                              <- Both sourced externally and generated from code
```
