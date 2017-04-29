## 2016.M3.TQF-ML.cross-currecy-basis


### Project description
Cross currency basis swap is a floating/floating swap through which two counterparties exchange different currencies. The EURUSD basis has been negative and more volatile since 2008. This project tries to predict the changes of 2y EURUSD basis by determining effective features. See the [proposal](Proposal.pdf). 


### Features 
Changes of basis during period t-1

US Dollar Index published by Bloomberg which indicates the dollar strength in the spot FX market

Reverse Yankee issuance which is the Euro debt issued by US companies

USD LIBOR/OIS spread which indicates credit risk

3m Euribor-3m EONIA

CME global volatility index (VIX) 

ted spread (3m US libor-3m treasury yield)

3m Euribor-3m Generic Germany bond yield 

BAML GFSI Solvency Component which indicates global solvency risk


### Methods
Try KNN/logistic/SVM/RandomForest/bagging/AdaBoost to choose a better model.


### Data
（more detail in [data description](data/data_description.pdf)）

It’s a dataset of 2 year EURUSD basis and its possible contributors. 

Include data of changes of basis, Bloomberg US Dollar index, CME global volatility index, ted spread (3m US libor-3m treasury yield), 3m Euribor-3m Generic Germany bond yield, overnight Libor/OIS spread, 3m Euribor-3m EONIA, American corporates’ issuance of Euro bonds and BAML GFSI Solvency Component.

There are respectively weekly data(622 samples) and daily data(2958 samples) from 2005/4/26 to 2017/4/10.


### Implementation
* [Python notebook file: Daily Data](basis_prediction(daily%20data).ipynb)
* [Python notebook file: Weekly Data](basis_prediction(weekly%20data).ipynb)


### Conclusion
None of the algorithms have satisfying performances. And they have higher probability in predicting negative changes of basis, which may be caused by number of negative d(basis) much highr than those of positive ones in samples.

When it comes to different data frequencies, algorithms using daily data have higher test accuracies(above 58% in daily data and around 50% in weekly data) and smaller standard deviations of cross validation accuracies. It may be caused by much samller number of weekly data samples for time limitation.

when it comes to different algorithms, Logistic Regression and SVM have better performance. Although all the algorithm have similar test accuracies, Random Forest and KNN show significant overfitting problems.

In addition, the performance doesn't show improvement after add in two features( EuriborEONIA and Euribor-GGB), which is contrast to intuition.
