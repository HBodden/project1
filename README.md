# project1
Gamerlytics

Presented by nOObs
Huntley Bodden – Github manager and API calls
Nicoleta Cosereanu – Data analytics and researcher
Yi Lu – Statistics and research
Devin Sherwood – Hypothesis and testing

Project scope: Analyze data from the popular gaming platform, Steam, to understand how key influencers such as price and game ratings are driving gamer behavior and game popularity.

Git Hub files and file structure 
The project 1 repo Jupyter notebook contains all files created for this project to include ‘scratch’ paper. Provided below is a description of each:

Not shown in the notebook is the config.py file. This file contains the API key for the STEAM site. In order to run the code, the user will need to create a config.py file containing the API key.

Gamerlytics - Group Power Point Presentation

SEAMS.ipynb – This is the primary file used by the team for final analysis and chart development. The file is broken into two sections. The first section contains the code used to explore the API sites, pull in data and create the data frame that was used for analysis. Each code block is commented to describe the actions that were taken to develop what was ultimately the final dataset. An API key, not included, is required to successfully run all of the code in this section. 
The second section of the notebook contains the code that the group used to conduct the analysis and generate charts for the presentation. In order to get the most data, calls to the … site was completed using an iterative process because the url connection frequently timed-out. As a result, several .CSV files were generated and later combined into one (Final_Combined_DataF.csv) file which represents the data the team worked from. 

nOObs.ipynb – This file is scratch paper that was used by a group member to explore different APIs. This file remains in the notebook because we were instructed to leave all work created for the project, to include scratch work, in the repo.

untitled.ipynb - This file is scratch paper that was used by a group member to explore different APIs. This file remains in the notebook because we were instructed to leave all work created for the project, to include scratch work, in the repo.

Action_Genre_Data.csv – SEAMS data pull of all available games in the ‘action’ genre. This data set represents the foundation of the total data used in this analysis. The file contains 24,710
Data included in in the file is:
•	appid - Steam Application ID. 
•	name - game's name
•	developer - comma separated list of the developers of the game
•	publisher - comma separated list of the publishers of the game
•	score_rank - score rank of the game based on user reviews
•	owners - owners of this application on Steam as a range.
•	average_forever - average playtime since March 2009. In minutes.
•	average_2weeks - average playtime in the last two weeks. In minutes.
•	median_forever - median playtime since March 2009. In minutes.
•	median_2weeks - median playtime in the last two weeks. In minutes.
•	ccu - peak CCU yesterday.
•	price - current US price in cents.
•	initialprice - original US price in cents.
•	discount - current discount in percents.
•	tags - game's tags with votes in JSON array.
•	languages - list of supported languages.
•	genre - list of genres.

AppID_PlayerCount.csv – AppID_PlayerCount_7.csv – These files contain the player count by appid. The appid was generated in the Action_Genre_Data pull. This file was merged with the Action_Genre_Data.csv to create the final data set used in the project. The seven files represent the iterative approach needed to capture as much data as possible. Total lines of data in this file is, 21,119. The iterative approach was used to counter the API website timing out during the ‘get’ process. 
 
Final_Combined_Data.csv – This file was created by reading all csv files back into the data frame and creating on consolidated file. 

Final_Combined_DataF.csv - This file was created after performing some modifications using formulas in MS excel, this file is the file that the group used for the final analysis. This data set includes initial and final price (converted to dollars), discount, total score mark and tier and all of the elements listed for Action Genre.

SEAMS_Data.csv – Exploratory file pulled during the initial stages of the project contains data on the games that are owned by 1000 – 2000 users 

Top100.csv – Exploratory file pulled during the initial stages of the project. Contains the top 100 games 

The following charts were created to show some of the results of the analysis 
Mixed_Charts.png – Line chart showing the number of positive and negative comments compared to average player time 
Player Count v Avg Player Time.png - Scatter plot / regression showing the relationship between player count and Avg Player Time 
Player Count v Positive Comments.png – Scatter plot / regression showing the relationship between player count and positive comments 
Player v Average Play Time.png – Line chart showing the average player time compared to player count 
Player v Comments.png – Line chart showing the positive and negative comments as compared to player count. 
Project purpose: Analyze data from the popular gaming platform, Steam, to understand how key influencers such as price, discount and game ratings are driving gamer behavior and game popularity.

Steam API url: https://partner.steamgames.com/doc/webapi/ISteamUserStats 
Steam Spy url: https://steamspy.com/api.php 

Null Hypothesis: Our Null Hypothesis suggests the price of the Steam game is a factor in game popularity
Alternative Hypothesis: Our Alternative Hypothesis suggests price of a game is NOT a factor in game popularity

Data collection, investigation and cleansing 
•	Data was retrieved via API calls from various Steam sources and combined
•	Steamspy.com was used to retrieve game info: ID, game name, developer, publisher, positive & negative ratings, owners, price info, concurrent users and game time averages [returned 24,735 records]
•	Api.steampowerd.com was used to retrieve current player count by game id [returned 1095 records]
•	After analyzing the retrieved data, we identified the 

Definitions and context 
•	Owner Tiers: A(most) to M(least)
  
•	Game Rating:  Calculated using positive and negative ratings as follows:
•	If positive ratings are higher than negative, % positive of total shown as positive value
•	If negative ratings are higher than positive, % negative of total shown as negative value
•	Players: number of current registered users for each game
•	Concurrent users: number of people playing a game at the same time

Research Topics 
•Hypothesis test:
H0 : Price is a factor R$-pc != 0​
HA: [Price] is NOT a factor in [game popularity] R$-pc=0​
When running our hypothesis test, we used a two-sided t-test. We use this test by observing the correlation between price and player count of the games. The test measures whether the average (expected) values are either significant or are not significantly connected across the samples. The test(this graph using pearsons correlation test) shows a weak/no clear correlation of 0.04 as well as (t-test)showing a small p-value threshold of 0.000020, less than 0.05(5%), thus we can reject our null hypothesis and our alternative hypothesis is supported.
•	Correlations and Trends:   
•	Identify correlations between game price and number of players - with a correlation factor of 0.04, it is not surprising that the most expensive games (Owner Tier A) have more players than free games.
•	Identify correlations between game ratings and number of players/concurrent users – by analyzing the rating and price we concluded that price is not an important factor in a game’s rating. The correlation factor between the two is .03. Owner Tier A has the highest price, yet not the highest rating. 
•	Players and average game time – by analyzing player count and average player time we found that having the most registered players does not result in having the highest player time.  The correlation factor between player count and average player time is .05
•	Players and positive rating - there is a positive correlation between player count and player feedback 
•	Gamer Engagement Analysis:
•	There is no strong relationship between player count and median playtime difference ​
There are 1% of the gamers increased median playtime in past two weeks​

Conclusions:
•	Reject the null Hypothesis. Gamers do not choose a game based on price
•	Gamers do not equate the quality of a game with the price they pay for it
•	A game with many users is not always the most played game
•	Positive comments for a game attract players
•	99% of the games  are losing interest over time


