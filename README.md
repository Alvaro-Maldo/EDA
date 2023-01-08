# Netflix Exploratory Content Launch Analysis 

VideoStreaming is one of the [most developed](https://www.statista.com/outlook/dmo/digital-media/video-on-demand/video-streaming-svod/worldwide#revenue) markets nowadays, which mixes an emerging business model based on recurring payments with an innovative idea where you can find any movies or TV shows without leaving home.

My approach to this exploratory data analysis is to determine if companies follow any seasonal trends in terms of launching content (maybe it is optimal to launch more films during summer vacation than when they are working since they don't have a routine) and also to identify any possible strategies taken by their competitors.



## Datasets

For this exercise I am using a set of Kaggle Databases referring to all the content uploaded from [Netflix](https://www.kaggle.com/datasets/shivamb/netflix-shows), [Hulu](https://www.kaggle.com/datasets/shivamb/hulu-movies-and-tv-shows), [Amazon Prime](https://www.kaggle.com/datasets/shivamb/amazon-prime-movies-and-tv-shows) and [Disney +](https://www.kaggle.com/datasets/shivamb/disney-movies-and-tv-shows). 

For programming I will use ``python`` language code.




### Web Scraping

Furthermore I decided it will make sense to unite my initial database with the top [movies](https://www.imdb.com/chart/top/?ref_=nv_mv_250) and [series](https://www.imdb.com/chart/toptv/?ref_=nv_tvv_250) in Imdb in order to also have an idea of the quality of the leading companies in the market.

To extract the information from the website, I chose the `BeautifulSoup` library which can be seen [here](https://github.com/NotCorrectlyDonated/Netflix_Exploratory_Analysis/blob/main/notebooks/PelisTop250.ipynb).




## Data Handling

To work on the data using `pandas` library I followed different phases:


### Data Cleaning and Selection 

As my analysis is only focused on time-series and the type of content (whether it is a TV Show or a film), I only worked on 3 columns from the initial dataset:

- `Type` (In order to differentiate between movies and TV shows)
- `Title` (As an indentifier of the content)
- `Date_added` (When the content was launched)


In terms of cleaning and making the data adecuate, I found out that the dataset contained missing values, mostly related to the `Date_added` column. Since there is less than 1% of null values in the column, I decided to just delete the erratic rows.[^1]

[^1]: Please note that since Amazon Prime dataset had a lot more missing values (>60%) I will not continue with its analysis as we might have a biased result.


### Data Handling and Mining

Once we have our Dataset cleaned and transformed, we will now make it adecuate to be addressed correctly by transforming the data contained in `Date_added` columns to a `pandas.to_datetime` in order for it to be recognized as a time-series object.

Finally, in order to be provided with more information we will combine both Imdb rating datasets as this will also provide us with information if the content launched is top quality.



## Data Visualization

In order to see any trends to get insights, we will lean on `plotly`, as it shows interactive information and I found it more interesting than using other visualization libraries such as `seaborn` or `matplotlib`. 

To have a wide perspective of any trends the companies may have when launching content, I decided to previously group the data in 15 days, making it easier to see if there is any time patterns over the year where it is preferable for a film or TV Show to be launched.


![hi](https://raw.githubusercontent.com/NotCorrectlyDonated/Netflix_Exploratory_Analysis/main/data/Charts/Film%20Netflix_Analysis.PNG)
<sub> TV shows launching in Netflix </sub>



After analyzing the TV Shows launched in Netflix, we can state that there are no seasonal trends, since each year has different quantities of videostreaming launches in the same months, what we see is that they follow 2-3 months cycles between each launching momentum. We can also identify some outliers that may suggest this uploads are also influenced by external market behaviour.


When analyzing the films:

![hi](https://raw.githubusercontent.com/NotCorrectlyDonated/Netflix_Exploratory_Analysis/main/data/Charts/Series%20Netflix_analysis.PNG)
<sub> Films launching in Netflix </sub>


It has a different scheme, mantaining the 2-3 months of periodicity, and even more, but, what is more interesting is that I could identify an outlier to a market situation: the creation of Disney+ platform, this situation can be understood as a "response" Netflix has made to this event to protect their users.


When we analyse the content all companies have launched, it can be seen more clearly if there is any trend they may follow when one of the competitors tries to upload "an unsual amount of content".

![hi](https://raw.githubusercontent.com/NotCorrectlyDonated/Netflix_Exploratory_Analysis/main/data/Charts/Analysis%20market.PNG)
<sub> Market content launching</sub>

There are situations where one platflorm tries to "disrupt" by launching a lot of content and how they, in the consecutive period, adapted and made a response. It is clear they have not just internal decisions but they are also aware of the market when deciding how much content is needed to be launched.


