# Multi-Cryto Trading Bot

### Background

In this project we are creating a Multi-Cryoto Trading Advisor Bot. This bot will be taking live hiostorical data through Yahoo Finance API for the period between 2014-2022.
The bot will generate buy, sell and hold signals for a portfolio of four coins. In order to generate the mentioned signals, the machine will run through seires of indicators and models 
to populate signals, which later will be backtested by sequential modeling. 


### Establish a Baseline Performance

1.  Import the OHLCV dataset into a Pandas DataFrame from Yahoo Finanace 

2.  Generate trading signals using short- and long-window SMA values.

3.  use a for loop statement, with if, else and elif, to generate Trade Type signals (Buy, Sell, Hold)

4.  Split the data into training and testing datasets.

5.  Used SVC classifier model from SKLearn's support vector machine (SVM) learning method inorder to fit the training data and calculated predictions based on the testing data. Review the predictions.

6.  Review the classification report associated with the SVC model predictions.

7.  Create a predictions DataFrame that contains columns for “Actual Returns”, and “Strategy Returns”.

8.  Use HVPLOT, to plot and display “Actual Returns”, vs “Strategy Returns”.


### Tune and evaluate the model by using a second Machine Learning Classifier 

1.  Import the OHLCV dataset into a Pandas DataFrame from Yahoo Finance.

2.  Generate trading signals using short- and long-window SMA values.

3.  use a for loop statement, with if, else and elif, to generate Trade Type signals (Buy, Sell, Hold)

4.  Split the data into training and testing datasets.

5.  Used LogistRegression classifier model from  sklearn linear_model learning method inorder to fit the training data and calculated predictions based on the testing data. Review the predictions.

6.  Review the classification report associated with the LogisticRegression model predictions.

7.  Create a predictions DataFrame that contains columns for  “Actual Returns”, and “Strategy Returns”.

8.  Use HVPLOT, to plot and display “Actual Returns”, vs “Strategy Returns”.

 Use PSAR to generate market trend through out the period.
 Use PSAR to generat Buy and Short Signals 
 Plot findings 

### Backtest the better performing model

1.  Use Neural Networks deep learning multiclass to back test the model. 

### API
Yahoo Finanace 

### Coin Portfolio

Bitcoin, LiteCoin, XRP, DogeCoin

### Models Used
SVM(Support Vector Machine)
LogisticRegression 

### Indicators 
SMA long and short 
EMA long and short
PSAR 






