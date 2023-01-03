# Netflix Exploratory Content Launch Analysis 

VideoStreaming is one of the most evolved markets nowadays, mixing an emerging business model based of recurring payments with an innovative enterteinment idea, where you can find any movie or series without leaving home.

My approach with this analysis is to observe any seasonal trend in terms of launching more content at some point over the year and also to identify any possible strategies against their competitors.

/n

## Datasets

For this exercise I am using a set of Kaggle Databases referring to all the content uploaded from [Netflix](https://www.kaggle.com/datasets/shivamb/netflix-shows), [Hulu](https://www.kaggle.com/datasets/shivamb/hulu-movies-and-tv-shows), [Amazon Prime](https://www.kaggle.com/datasets/shivamb/amazon-prime-movies-and-tv-shows) and [Disney +](https://www.kaggle.com/datasets/shivamb/disney-movies-and-tv-shows) from 2018 to 2021. 
As programming language I will use Python based on a Jupyter notebook, to make it more visual.




### WebScrapping

Furthermore I decided to obtain information from the top [movies](https://www.imdb.com/chart/top/?ref_=nv_mv_250) and [series](https://www.imdb.com/chart/toptv/?ref_=nv_tvv_250) in Imdb, in order to have a quality classification approach of the content from the different websites.

In order to adecuate the information from the website to a useful dataset, we choose `BeautifulSoup` as a suitable webscrapping library, the code of how to organise the data can be seen at notebook directory or at [this link](https://github.com/NotCorrectlyDonated/Netflix_Exploratory_Analysis/blob/main/notebooks/PelisTop250.ipynb).


/n
/n

## Data Cleaning & Wrangling

In order to work throughout the data, we will use `pandas` library to correctly adress all the items and adecuate it correcly, this will be done in several phases. 

### Data Cleaning and Selection 

In order to provide useful information, we will first select to then clean the dataset obtained adecuating possible NaN or null items, as my analysis is related to a time-series, I selected the 3 most valuable columns that will help me at my analysis:

- `Type` (In order to differentiate between movies and TV shows)
- `Title` (As an indentifier of the content)
- `Date_added` (When the content was launched)

As most of the datasets are from 2020, or the data from previous years is doubtfully addressed, we will also clean previous data, obtaining content from 2020 and 2021.

In terms of cleaning and adecuating data, as most of the null values in the datasets are related to `Date_added` columns, we will need to have to make an strategy to handle these kind of values. Since there is less than 1% of NaN values in the column, we will delete the erratic rows.

<sub>(Note that, since the Amazon prime dataset had a lot more NaNs, we will not continue with its analysis since we might have a biased result.)</sub>


### Data Handling and Mining

Once we had our Dataset cleaned, we will now adecuate it to be addressed correctly. To do so we will address the `Date_added` columns as a `pandas.to_datetime` in order to be recognized as a time-series object.

Lastly, and to be provided with more information, we will merge both Imdb rating datasets in an outer form, as this will also provide us with information about if the content launched is top quality or not (as a quality measure of the company)

/n

## Data Visualization and Insights

In order to see any patterns and make usefull insights about the data, we will lean on `plotly`, as it has more visual interactive information and I found it more interesting in this project than using `seaborn` or `matplotlib`. 

To have a wide perspective of any trends the companies may have when launching content, I decided to group the data in 15 days, making it easier to see if there is any time over the year where it is prefferred to be launched a film or TV Show.


![hi](https://raw.githubusercontent.com/NotCorrectlyDonated/Netflix_Exploratory_Analysis/main/data/Charts/Film%20Netflix_Analysis.PNG)
<sub> TV shows launchs in Netflix </sub>

/n

After analyzing the TV Shows launches in Netflix, we can state that there are no seasonal trends in terms, since each year has different quantities of videostreaming information at the same months, what we may see is 2-3 months cycles between having a huge launching momentum. We can also identify some outliers that may suggest us this uploads may have some marketing purposes.


When analyzing the films, something happens:

![hi](https://raw.githubusercontent.com/NotCorrectlyDonated/Netflix_Exploratory_Analysis/main/data/Charts/Series%20Netflix_analysis.PNG)
<sub> Films launchs in Netflix </sub>

/n
/n
/n

The have a different schema, mantaining the 2-3 months of periodicity, and even extending, but, what is even more interesting is that we could identify an outlier in terms of launchs, that is directly correlated with the instauration of Disney+ platform, and, we could understand this situation as a "response" to this event.


When we analyse the content launched between all companies, we can then see more clearly if there is any trend they may follow when one of the competitors try tuo upload "an unsual amount of content".

![hi](https://raw.githubusercontent.com/NotCorrectlyDonated/Netflix_Exploratory_Analysis/main/data/Charts/Analysis%20market.PNG)
<sub> Market content launchs</sub>
/n

We can now see there are situations where there is one platflorm trying to "disrupt" by launching a lot of content compared to their competitors and how they, on the consequtive period, adapted and make a response, so it is clear they have not just internal decisions but they are also aware of the market when deciding how many content is needed to be launched.


