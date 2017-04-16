# 2016.M3.TQF-ML.cross-currecy-basis

## Project description
Cross currency basis swap is a floating/floating swap through which two counterparties exchange different currencies. The EURUSD basis has been negative and more volatile since 2008. This project tries to predict the changes of 2y EURUSD basis by determining effective features. 

## Features 
Changes of basis during period t-1.
US Dollar Index published by Bloomberg which indicates the dollar strength in the spot FX market
Reverse Yankee issuance which is the Euro debt issued by US companies
USD LIBOR/OIS spread which indicates credit risk
CME global volatility index (VIX) 
ted spread (3m US libor-3m treasury yield)
BAML GFSI Solvency Component which indicates global solvency risk

## Methods
Try KNN/logistic/SVM/RandomForest/bagging/AdaBoost to choose a better model.
