Many people struggle to get loans due to insufficient or non-existent credit histories. And, unfortunately, this population is often taken advantage of by untrustworthy lenders.

Home Credit strives to broaden financial inclusion for the unbanked population by providing a positive and safe borrowing experience. In order to make sure this underserved population has a positive loan experience, Home Credit makes use of a variety of alternative data--including telco and transactional information--to predict their clients' repayment abilities.

In this project I evaluated, cleaned, and combined data from many sources to create both an rpart model and an lm model to predict default risk.

In-sample performance of the regression model is 91.8% and the out of sample-performance is 73.3%. Kaggle Score: 0.72385 - this translates to an accuracy of 72.4%. As the top Kaggle score is around 0.8, there is obviously room for improvement. Furthermore, the recall and sensitivity was quite low indicating a need for further aggregation.

Because of the sheer amount of data, a good portion of it had to be sifted and filtered in order to find the most important factors. Even then, the graph of the first decision tree model was far too complex to interpret. Several factors were removed, as including them in prediction models could be considered discriminatory.

The top two predictors for the TARGET variable were EXT_SOURCE_3 and EXT_SOURCE_2 indicating that the scores HomeCredit received from external data sources were valuable information. The next group of predictors were related to occupation, which does make sense as we would expect to see a difference across occupations in lending. The group after this takes the client's credit history into account, examining the status of previous loans and late payments, which could also be natural predictors, and even red-flags for potential lenders. As much of this data came from files outside of the main data frames, it's clear that extending our analysis was worth the effort.

It is not surprising to find that some of the least valuable predictors dealt with the client's living space. As there are very large houses in destitute regions of the country, and very small apartments in some of the most wealthy regions, and vice-versa, any correlation with these variables to the target would have been difficult to determine.
