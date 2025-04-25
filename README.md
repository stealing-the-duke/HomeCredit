Many people struggle to get loans due to insufficient or non-existent credit histories. And, unfortunately, this population is often taken advantage of by untrustworthy lenders.

Home Credit strives to broaden financial inclusion for the unbanked population by providing a positive and safe borrowing experience. In order to make sure this underserved population has a positive loan experience, Home Credit makes use of a variety of alternative data--including telco and transactional information--to predict their clients' repayment abilities.

In this project we evaluated, cleaned, and combined data from alternative sources to create an rpart model and an lm model to predict a given individuals likelihood of default. With the model HomeCredit can expand its business to those without credit histories, while still avoiding unnecessary risk.

In our modelling process we first examined the overall structure of the data and removed variables that could be discriminatory such as age and gender. Then we cleaned it by removing null values, removing variables with near-zero variance, removing variables that were highly correlated with other variables, and by factoring necessary data types. We used the skimr package to identify skew and likely predictors, and finally, we joined the data sources into one data frame and separated it into testing and training data frames based on a 70% split.

In-sample performance of the regression model is 91.8% and the out of sample-performance is 73.3% with a Kaggle Score of 0.72385 - this translates to an accuracy of 72.4%. As the top Kaggle score is around 0.8, there is obviously room for improvement, but the metrics are still fairly decent. That said, the recall and sensitivity is lower than we would like, indicating a definite need for further aggregation.

Because of the sheer amount of data, a good portion of it had to be sifted and filtered in order to find the most important factors. Even then, the graph of the first decision tree model took a very long time to generate and was far too complex to interpret.

The top two predictors for the TARGET variable were EXT_SOURCE_3 and EXT_SOURCE_2 indicating that the scores HomeCredit received from external data sources were quite valuable. The next group of predictors were related to occupation and income, which is what we would expect to see. The group after this takes the client's credit history into account, examining the status of previous loans and late payments, which could also be natural predictors.

In retrospect, I would have used a different model type like a neural network or XGBoost for model building, or even a random forest to enhance recall. Additionally, I would use 10 fold cross validation to partition and train the data for better training.
