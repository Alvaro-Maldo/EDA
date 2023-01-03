# Netflix Exploratory Content Launch Analysis 

VideoStreaming is one of the most evolved markets nowadays, mixing an emerging business model based of recurring payments with an innovative enterteinment idea, where you can find any movie or series without leaving home.

My approach with this analysis is to observe any seasonal trend in terms of launching more content at some point over the year and also to identify any possible strategies against their competitors.



## Datasets

For this exercise I am using a set of Kaggle Databases referring to all the content uploaded from [Netflix](https://www.kaggle.com/datasets/shivamb/netflix-shows), [Hulu](https://www.kaggle.com/datasets/shivamb/hulu-movies-and-tv-shows), [Amazon Prime](https://www.kaggle.com/datasets/shivamb/amazon-prime-movies-and-tv-shows) and [Disney +](https://www.kaggle.com/datasets/shivamb/disney-movies-and-tv-shows) from 2018 to 2021.



### WebScrapping

Furthermore I decided to obtain information from the top [movies](https://www.imdb.com/chart/top/?ref_=nv_mv_250) and [series](https://www.imdb.com/chart/toptv/?ref_=nv_tvv_250) in Imdb, in order to have a quality classification approach of the content from the different websites.

In order to adecuate the information from the website to a useful dataset, we choose `BeautifulSoup` as a suitable webscrapping library, the code of how to organise the data can be seen at notebook directory or at [this link](https://github.com/NotCorrectlyDonated/Netflix_Exploratory_Analysis/blob/main/notebooks/PelisTop250.ipynb).





## Data Cleaning & Wrangling

In order to work throughout the data, we will use `pandas` library to correctly adress all the items and adecuate it correcly, this will be done in several phases. 

### Data cleaning and Selection 

In order to provide useful information, we will clean the dataset obtained to adecuate possible NaN or null items, as my analysis is related to a time-series, and most of the null values in the datasets are related to this column, we will have to make an strategy to handle these kind of values. Since there is less than 1% of NaN values in the column, we will delete the erratic rows.

<sub>Note that, since the Amazon prime dataset had a lot more NaNs, we will not continue with its analysis since we might have a biased result.</sub>

and we will select the 3 most valuable columns for our analysis:

- `Type` (In order to differentiate between movies and TV shows)
- `Title` (As an indentifier of the content)
- `Date_added` (When the content was launched)



