# Project 2- Crypto Trading Advisory Bot 
 
## Litecoin trading advisory bot

### Three main concepts being used for Litecoin trading and testing:

- AdaBoost Classifier utilized as model training and testing (New model not covered in class)
- Neural Network backtesting and prediction on trading type
- Bollinger Bands indicator application and visualization

Litecoin is one of our selection on trading analysis for the usage of trading bot. At the beginning, I use CoinGecko API to get Litecoin 7 years data from 2013 to 2022. However, CoinGecko is only able to pull open price, not closed price. If we want to get closed price over 30 days, it has to pay for membership. Becuase of this limitation, I change the way to get dataset from Yahoo Finance by importing Yahoo Finance library. 

After dataframe being cleaned up, I need to get an significant indicator for the preparation of trading bot, model testing and prediction, which is simple moving average(SMA). I set two simple moving average 20 days versus 100 days. Also, I made a trading type to be included in dataframe for the decision of trading Litecoin, buy, sell or hold. Here is the graph to show the general idea of trading bot.
![Project-2--Crypto-Trading-Advisory-Bot-](../Project-2--Crypto-Trading-Advisory-Bot-/Litecoin%20Price%20history%20with%20buy%20and%20sell%20signals.PNG)

AdaBoost Classifier also called Adaptive Boosting is a technique in Machine Learning used as an Ensemble Method, it bulds a model and gives equal weights to all the data points. It then assigns higher weights to points that are wrongly classified. That's why I choose AdaBoost model testing and further predictio,  which can fairly weight my dataframe. Although the accuracy from classification report is only 50%, recall on predicting 'Actual Return is positive percentage' is 97%, which is a high percentage. Also, according to my chart below, prediction for cumulative Strategy Returns(Strategy Return) aligned with actual return from 2017 to 2019. After 2019, prediction are slightly undervalued. However, it is better than overvalued. Overall, this model can be trusted for Litecoin return prediction.

![Project-2--Crypto-Trading-Advisory-Bot-](../Project-2--Crypto-Trading-Advisory-Bot-/AdaBoost%20Model%20-%20Actual%20Returns%20vs%20Strategy%20Returns.png)

In order to improve the model, I tried with SVM model, this model works better, prediction are closedly aligned with actual return. 
![Project-2--Crypto-Trading-Advisory-Bot-](../Project-2--Crypto-Trading-Advisory-Bot-/SVM%20Model%20-%20Actual%20Returns%20vs%20Strategy%20Return.png)

Keras Sequential model is a linear stack of layers, it is a common model to be used in Neural Network for backtesting. I use Sequential and LabelEncoder model together on predicting trade type as a trading advisory bot. After adding layers dropout and regularizer, 120 epochs training dataset, evaluate test data, I get 99% accurancy on test data, 97% on train data. Obviously, the accurancy looks too perfect, which does not make sense, but I have tried my best to find a proper model for backtesting on trading type. 

Bollinger Band is a technical analysis tool defined by a set of trendlines plotted two standard deviations(positively and negatively) away from a SMA of a security's price. It is also a signal for oversold or overbought. Bollinger Bands are composed by 3 lines: Upper, middle and lower band. I use this indicator under Finta library for visualization, which is very useful for investment and overlook the general picture of Litecoin performance. Please see below graph of Bollinger Bands with closed price movement. Orange line are upper and lower bands, blue line represents middle band, grey line represents closed price.

![Project-2--Crypto-Trading-Advisory-Bot-](../Project-2--Crypto-Trading-Advisory-Bot-/Litecoin%20Closed%20price%20with%20Bollinger%20Bands.png)

In addition, I made a graph for SMA with closed price movement as well, which is also useful to see the general performance on Litecoin and provide some direction for Litecoin investment.

![Project-2--Crypto-Trading-Advisory-Bot-](../Project-2--Crypto-Trading-Advisory-Bot-/Litecoin%20Closed%20Price%20with%20SMA%2020%20Days%20vs%20100%20Days.png)

In summary, my model cannot be used in reality, the accurancy is too close to 100%, which is too perfect. Something is wrong and need to be improved, also, prediction are not always accurate and unstable. I still need to try other models for backtesting until all analysis of data looks good.