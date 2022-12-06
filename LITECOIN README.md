# Project 2- Crypto Trading Advisory Bot 
 
## Litecoin trading advisory bot

### Three main concepts being used for Litecoin trading and testing:

- AdaBoost Classifier utilized as model training and testing (New model not covered in class)
- Neural Network backtesting and prediction on trading type
- Bollinger Bands indicator application and visualization

Litecoin is one of our selection on trading analysis for the usage of trading bot. At the beginning, I use CoinGecko API to get Litecoin 7 years data from 2013 to 2022. However, CoinGecko is only able to pull open price, not closed price. If we want to get closed price over 30 days, it has to pay for membership. Becuase of this limitation, I change the way to get dataset from Yahoo Finance by importing Yahoo Finance library. 

After dataframe being cleaned up, I need to get an significant indicator for the preparation of trading bot, model testing and prediction, which is simple moving average(SMA). I set two simple moving average 20 days versus 100 days. Also, I made a trading type to be included in dataframe for the decision of trading Litecoin, buy, sell or hold.

AdaBoost Classifier also called Adaptive Boosting is a technique in Machine Learning used as an Ensemble Method, it bulds a model and gives equal weights to all the data points. It then assigns higher weights to points that are wrongly classified. That's why I choose AdaBoost model testing and further predictio,  which can fairly weight my dataframe. Although the accuracy from classification report is only 49%, recall on predicting 'Actual Return is positive percentage' is 74%, which is not bad. Also, according to my chart below, prediction for cumulative Actual Returns(Strategy Return) is very close to actual percentage before January 2021 even though sometimes is overvalued or undervalued, but the percentage is similar to cumulative actual returns percentage. During the period of Januart 2021 and May 2022, there is a high discrepency, which means those period prediction cannot be trusted, After May 2022, the prediction is undervalued but it can be used for further investment consideration.

![Project-2--Crypto-Trading-Advisory-Bot-](../Project-2--Crypto-Trading-Advisory-Bot-/AdaBoost%20Model%20-%20Actual%20Returns%20vs%20Strategy%20Returns.png)

Keras Sequential model is a linear stack of layers, it is a common model to be used in Neural Network for backtesting. I use Sequential and LabelEncoder model together on predicting trade type as a trading advisory bot. After adding multiple layers, 120 epochs training dataset, evaluate test data, I get 53% accurancy on test data, 51% on train data. Obviously, the accurancy is not high enough, but I have tried my best to find a proper model for backtesting on trading type. As a result, I get 391 count for 'buy' decision, 332 count for 'sell' decision.

Bollinger Band is a technical analysis tool defined by a set of trendlines plotted two standard deviations(positively and negatively) away from a SMA of a security's price. It is also a signal for oversold or overbought. Bollinger Bands are composed by 3 lines: Upper, middle and lower band. I use this indicator under Finta library for visualization, which is very useful for investment and overlook the general picture of Litecoin performance. Please see below graph of Bollinger Bands with closed price movement. Orange line are upper and lower bands, blue line represents middle band, grey line represents closed price.

![Project-2--Crypto-Trading-Advisory-Bot-](../Project-2--Crypto-Trading-Advisory-Bot-/Litecoin%20Closed%20price%20with%20Bollinger%20Bands.png)

In addition, I made a graph for SMA with closed price movement as well, which is also useful to see the general performance on Litecoin and provide some direction for Litecoin investment.

![Project-2--Crypto-Trading-Advisory-Bot-](../Project-2--Crypto-Trading-Advisory-Bot-/Litecoin%20Closed%20Price%20with%20SMA%2020%20Days%20vs%20100%20Days.png)

In summary, my model cannot be used in reality, the accurancy is low, which is around 50%. Prediction are not always accurate and unstable. I still need to try other models for backtesting until all analysis of data looks good.