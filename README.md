# Microsoft Box Office!

# Overview

Due to the success of original content creation in various streaming platforms, Microsoft will be launching an in house movie studio. In order to optimize this venture, Microsoft has tasked us with conducting a data study that will produce actionable insights and guide them on creating optimum content. 

# Contents

1. Data: Repository for different databases used in project
2. Project Notebook - Microsoft Box Office: Jupyter Notebook with core analysis
3. Project PDF - Microsoft Box Office: PDF of Notebook for sharing purposes

# Data

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

# Results

1. Launch a Sci-Fi / Adventure film to compete for large shares of profitable markets off the bat
2. Launch a Sci-Fi / Western and forego potential revenue streams from Adventure
3. Launch a Sci-Fi / Animation Film to optimize for revenue generation and capitalize on an
unerserved market

