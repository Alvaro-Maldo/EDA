# Netflix exploratory content launch analysis 

VideoStreaming is one of the most evolved markets nowadays, mixing an emerging business model based of recurring payments with an innovative enterteinment idea, where you can find any movie or series without leaving home.

My approach with this analysis is to observe any seasonal trend in terms of launching more content at some point over the year and also to identify any possible strategies against their competitors.

##Datasets

For this exercise I am using a set of Kaggle Databases referring to all the content uploaded from [Netflix](https://www.kaggle.com/datasets/shivamb/netflix-shows), [Hulu](https://www.kaggle.com/datasets/shivamb/hulu-movies-and-tv-shows), [Amazon Prime](https://www.kaggle.com/datasets/shivamb/amazon-prime-movies-and-tv-shows) and [Disney +](https://www.kaggle.com/datasets/shivamb/disney-movies-and-tv-shows) from 2018 to 2021.

#WebScrapping

Furthermore I decided to obtain information from the top [movies](https://www.imdb.com/chart/top/?ref_=nv_mv_250) and [series](https://www.imdb.com/chart/toptv/?ref_=nv_tvv_250) in Imdb, in order to have a quality classification approach of the content from the different websites.

In order to adecuate the information from the website to a useful dataset, we will use the following Webscrapping libraries.

`from bs4 import BeautifulSoup`




