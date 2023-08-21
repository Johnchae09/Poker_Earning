# Predicting Poker Players All Time Money List Using Machine Learning!

- Created a model that predicts poker players' live tournament plus some online earnings that are in the record (no cash game earnings)
- Scraped over 100 players in the HendonMob website which keep track of poker players' earnings using Python.
- Utilized min max scaler and LSTM to build the model

## Code and Resource Used
**Python Version**: 3.9

**Packages**: pandas, numpy, seaborn, sklearn, keras, matplotlib

**Scrape Website**: https://pokerdb.thehendonmob.com/ranking/all-time-money-list/

**Players Pick in Model**: Alex Foxen, Espen Uhlen Jørstad, and Mikita Bodyakovsky

## Web Scraping

First scraped all the hyperlinks from the Hendon mob website for each player and scraped relevant information such as players ranking, earnings, placement, and buy-ins for that tournament.

- Date
- Event Name (Comes with buy-ins, although no record of how many buy-ins)
- Placement
- Earnings

## Data Cleaning

After scraping the needed data, I cleaned it up a bit in order to use it for the model. I made the following changes

- Made the data go in an ascending order (Date) to track player history
- Added a column to showcase the incremental earning of the player (This information is not 100% accurate since it does not showcase how much they lost but rather just their wins)
- Parsed int value from the Event Name for the buy-in columns
- Parsed int value from the Placement column

## EDA 
For this example, I will be using Alex Foxen's data to visualize data and trends.

![CHEESE!](https://github.com/Johnchae09/Poker_Earning/blob/main/images/foxen_live_earning.png?raw=true)

![CHEESE!](https://github.com/Johnchae09/Poker_Earning/blob/main/images/foxen_correlation.png?raw=true)

![CHEESE!](https://github.com/Johnchae09/Poker_Earning/blob/main/images/foxen_tourney_wins.png?raw=true)

![CHEESE!](https://github.com/Johnchae09/Poker_Earning/blob/main/images/foxen_buy_ins.png?raw=true)

![CHEESE!](https://github.com/Johnchae09/Poker_Earning/blob/main/images/foxen_rank.png?raw=true)

**As you can see, after a big win in early 2018, that's when his tournament buy-ins increased which led to playing at a higher stake, ultimately winning more cash.**

**Notably a player who is capable of winning multiple tournaments, which is where all the money is in a tournament structure.**

## Model Building

The LSTM neural network architecture is defined using the Keras library. Two LSTM layers with 50 units each are stacked, followed by dense layers. The model is compiled with the Adam optimizer and Mean Squared Error (MSE) loss function. The model is trained on the training dataset. For each training sequence, the previous 40 earnings data points are used as input features, and the next earnings data point is used as the target. After training, the model is evaluated on the test dataset, and Root Mean Squared Error (RMSE) is calculated to assess its accuracy.

## Results

![CHEESE!](https://github.com/Johnchae09/Poker_Earning/blob/main/images/foxen_model.png?raw=true)

## More

Interesting player, Espen Uhlen Jørstad 2022 Main Event Champion winning 10,000,000 USD. Before the main event win, Espen was playing in low stakes and didn't have a notable win yet. Interesting to see how the model predicted his earnings. I've set the model to predict right before his Main Event Win of 10 Million dollars.

![CHEESE!](https://github.com/Johnchae09/Poker_Earning/blob/main/images/jorstad_model.png?raw=true)


