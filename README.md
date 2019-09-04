<img src="https://bit.ly/2VnXWr2" alt="Ironhack Logo" width="100"/>

# SEARCHING FOR ARBITRAGE OPPORTUNITIES IN THE FX MARKET (on the paper)
*Pau Ferri Lloveras*

*Data Analytics Bootcamp, Ironhack Barcelona, June 2019*

## Content
- [Project Description](#project-description)
- [Hypotheses / Questions](#hypotheses-/-questions)
- [Dataset](#dataset)
- [Cleaning](#cleaning)
- [Analysis](#analysis)
- [Model Training and Evaluation](#model-training-and-evaluation)
- [Conclusion](#conclusion)
- [Future Work](#future-work)
- [Workflow](#workflow)
- [Organization](#organization)
- [Links](#links)

<a name="project-description"></a>

## Project Description
Since long time ago I started to search for arbitrage opportunities in the sport bookmakers and I realized that someone can obtain net profits on it, I did it.  
The topic of the following project is about the arbitrage opportunities in the forex (foreign exchange) market.
The main purpose of the project has been find arbitrage opportunities on the paper (with prices in the past) obtained from a database and apply the habilities and skills learned during the bootcamp.

What is an arbitrage in a market?
The definition of arbitrage is buying a security or product in one market and simultaneously (in a very short time period) selling it in another market at a higher price. This is considered a risk free profit for the trader.


<a name="hypotheses-/-questions"></a>

## Hypotheses / Questions
This first question that appears suddenly it is that:
* This is possible?
Well in fact, in real time, finding an arbitrage is very difficult. We are talking about the inefficiencies of the markets, once they disappear the arbitrage is gone. Usually this opportunities have a short period of existence less than a minute even some seconds. So in real time, is pretty hard to catch an arbitrage in Forex.

In this scenario, considering a virtual case not real, we are analyzing the past with a database, these has been some questions:
* What percentage represents a good opportunity? 
* They appear regularly?
* Which paths or ways would be the more usual?
* What algorithm is the appropriate to find an arbitrage opportunity?

<a name="dataset"></a>

## Dataset
The data has been obtained and downloaded directly from Kaggle. This is the link [dataset from Kaggle](https://www.kaggle.com/yurisa2/forex-rsi-and-bbpp-multiperiod-m1h4)  

The storage of this raw data is more than 5GB, to be true this has been pretty huge and some times hard to deal with a laptop in terms of processing.
The raw data then was compounded by 48 csv files, which every file represents a different currency pair with the price of this pair for every minute during 3 years in time.

<a name="cleaning"></a>

## Cleaning
Once the database was downloaded the first step was open it with pandas (library of python).
It has been done the initial common visualization like searching the nan values, see the shape of the DataFrames, and the type of data were stored in it.
As told in the point above the raw database was conformed with 48 files csv. Each of these file represents a currency pair, these were the follow:

USD/ZAR, GBP/NZD, USD/CAD, GBP/CHF, EUR/JPY, GBP/SGD, SGD/JPY, NZD/USD, USD/DKK, GBP/CAD, USD/MXN, AUD/CHF, GBP/SEK, EUR/TRY, AUD/JPY, USD/JPY, EUR/CHF, AUD/NZD, USD/NOK, EUR/HKD, AUD/USD, GBP/NOK, CHF/SGD, EUR/USD, GBP/USD, USD/CHF, USD/SEK, EUR/NZD, CAD/JPY, NZD/CAD, GBP/AUD, AUD/CAD, USD/SGD, EUR/AUD, NZD/CHF, EUR/NOK, EUR/GBP, EUR/CAD, USD/HUF, CHF/JPY, GBP/DKK, EUR/SGD, CAD/CHF, NZD/JPY, USD/PLN, EUR/SEK, EUR/ZAR, GBP/JPY. A total of 18 currencies.

From each file only two columns have been selected to merge in one new file: the price of each pair of currency and the time. Meaning a new file csv was created with 48 columns (every column representing each pair of currency) and the time as index. The time has selected as index because has been detected that despite of the position of the rows, for example the first row of each of the 48 should match with exactly the same time and it has not happened. In this case would be incoherent match these rows. So the solution has been select the currency with less number of rows and use their time as a reference then compare the timestamps coincide with all the others pairs. The timestamp has been 1,3M rows aprox.

The third step was try to create a matrix for every minute, it means 1,3M square matrix filled with the numbers of each pair if exists and if not with a Nan values. In the real world only could achieve 50000 instaed 1,3M due computational time and cost to execute it.

<a name="analysis"></a>

## Analysis
The first idea was to do an analisis with arbitrage opportunities founded but due the less time left it would not been possible to achieve. The main time has been invested on coding to obtain arbitrage opportunities from the dataset and understand which algorithm could fit better to find them. The algorithm used to find the arbitrage opportunities is called Bellman Ford, this one is similiar as Dijkstra but more robust less fast due permit the negative paths. The algorithm find one of the shortest path from a source to a target. [link for more information about Bellman Ford Algorithm](https://www.sciencedirect.com/topics/computer-science/bellman-ford-algorithm)

Some percentages have been showed in the presentation.

[link of the 50000 pairs table obtained after data wrangling and cleaning](https://wetransfer.com/downloads/fb8ddab0be2a19ff81203fce45ad017b20190822192220/d0954dde17daccdc879c811c9698dc3020190822192220/5764dd)

[link of the 48currencies as columns and 1,3M rows as timestamp](https://we.tl/t-4jVhVHivk1)

<a name="model-training-and-evaluation"></a>

## Model Training and Evaluation
*Include this section only if you chose to include ML in your project.*
* Describe how you trained your model, the results you obtained, and how you evaluated those results.

<a name="conclusion"></a>

## Conclusion
Despite of the fact that the analysis part has been very poor, I am happy with the work done, it has not been easy at all and enjoyed programming. Regarding the hypotheses asked I am quite surprised how regularly appeared arbitrage opportunities.

<a name="future-work"></a>

## Future Work
Keep track with the project and found some statistical results once the data is obtained.

<a name="organization"></a>

## Organization
Gitkraken for the repository on Github and Trello.

<a name="links"></a>

## Links
Include the links to your repository, slides and trello. Feel free to include any other links associated to your project. 

[Repository](https://github.com/haule92/Project-Week-8-Final-Project)  
[Slides](https://docs.google.com/presentation/d/1x_eFBEfIDHTuGaB2d-6b449l23CeruHT9RvrTq0kpuU/edit?usp=sharing)  
[Trello](https://trello.com/en)  
