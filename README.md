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

To work on the data, I used `pandas` library, following different phases:


### Data Cleaning and Selection 

As my analysis is just focused on time-series and type of content (either if it is a TV Show or a film), I worked on just only 3 columns of the initial dataset.

- `Type` (In order to differentiate between movies and TV shows)
- `Title` (As an indentifier of the content)
- `Date_added` (When the content was launched)


In terms of cleaning and adecuating data, I found out that the dataset contained missing values, mostly related to `Date_added` columns, needing to make an strategy to handle these kind of values. Since there is less than 1% of NaN values in the column, we will just delete the erratic rows.[^1]

[^1]: Note that, since Amazon Prime dataset had a lot more missings (>60%), we will not continue with its analysis since we might have a biased result.


### Data Handling and Mining

Once we had our Dataset cleaned and transformed, we will now adecuate it to be addressed correctly, transforming the data contained in `Date_added` columns as a `pandas.to_datetime` in order to be recognized as a time-series object.

Lastly, and to be provided with more information, we will merge both Imdb rating datasets in an outer form, as this will also provide us with information about if the content launched is top quality or not (as a quality measure of the company)



## Data Visualization and Insights

In order to see any trends to get insights, we will lean on `plotly`, as it shows interactive information and I found it more interesting in this project than using other visualization libraries as `seaborn` or `matplotlib`. 

To have a wide perspective of any trends the companies may have when launching content, I decided to previously group the data in 15 days, making it easier to see if there is any time over the year where it is prefferred to be launched a film or TV Show.


![hi](https://raw.githubusercontent.com/NotCorrectlyDonated/Netflix_Exploratory_Analysis/main/data/Charts/Film%20Netflix_Analysis.PNG)
<sub> TV shows launching in Netflix </sub>



After analyzing the TV Shows launches in Netflix, we can state that there are no seasonal trends in terms, since each year has different quantities of videostreaming information at the same months, what we may see is that they follow a 2-3 months cycles between having a huge launching momentum. We can also identify some outliers that may suggest us this uploads may also be influenced by market behaviour.


When analyzing the films:

![hi](https://raw.githubusercontent.com/NotCorrectlyDonated/Netflix_Exploratory_Analysis/main/data/Charts/Series%20Netflix_analysis.PNG)
<sub> Films launching in Netflix </sub>


The have a different schema, mantaining the 2-3 months of periodicity, and even extending, but, what is more interesting is that I could address an outlier to a market situation, the instauration of Disney+ platform, it can be understood this situation as a "response" Netflix has made to this event to protect their users.


When we analyse the content all companies launched, it can be seen more clearly if there is any trend they may follow when one of the competitors try to upload "an unsual amount of content".

![hi](https://raw.githubusercontent.com/NotCorrectlyDonated/Netflix_Exploratory_Analysis/main/data/Charts/Analysis%20market.PNG)
<sub> Market content launching</sub>

There are situations where there is one platflorm trying to "disrupt" by launching a lot of content compared to their competitors and how they, on the consequtive period, adapted and make a response, so it is clear they have not just internal decisions but they are also aware of the market when deciding how many content is needed to be launched.


