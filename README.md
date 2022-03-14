
<a name="BackToTop"></a>


# Hong Kong Horse Racing Performance Prediction using Machine Learning Methods

**Contributors: Cameron Stewart, Nathan Deinlein, Chris Roche, Ryan Kinney**

>The goal of this project was to classify the performance of horses during races in Hong Kong. The purpose of this project was purely academic to explore the use of many classification and clustering algorithms in Python's Scikit-Learn. The classification was for two target variables: Win and Show. Win represents whether or not a horse won the race and show represents whether or not the horse finished in the top three. Both are represented by a binary 0 or 1 value. Precision and AUC were used as the primary evaluation metrics in an imbalanced dataset. The project was sprit into 4 parts with a detailed report written for each. Part 1 - The team explored and visualized the data along with the relationships within and between variables. Part 2 and 3 - Explore using Logistic Regression, Support Vector Machines, KNN, Naive Bayes, and Random Forest for Classification. Part 4 - Explore using Clustering to create features that can be used for Classification. The detailed reports are linked below.

[Part 1 - EDA Report](../main/1_EDA/EDA_Final.ipynb)

[Part 2 - SVM and LR Modeling Report](../main/2_SVM_LR_Modeling/SVM_LR_Modeling_Final.ipynb)

[Part 3 - KNN, NB, and RF Modeling Report](../main/3_KNN_NB_RF_Modeling/KNN_NB_RF_Modeling_Final.ipynb)

[Part 4 - Clustering Report](../main/4_Clustering/Clustering_Final.ipynb)

---

## Table of Contents
- [Part 1 - EDA](#P1)
- [Part 2 - SVM and LR Modeling](#P2)
- [Part 3 - KNN, NB, and RF Modeling](#P3)
- [Part 4 - Clustering](#P4)
- [References](#References)

---

<a name="P1"></a>

## Part 1 - EDA

[Part 1 - EDA Report](../main/1_EDA/EDA_Final.ipynb)

All feature and response descriptions are discussed in detail inside the report. Every observation is the result of a single horse in a race. First, the team looked at missing values in the dataset. Any yellow horizontal bar represents an observation missing from that variable. The team recognized the position_sec, behind_sec, and time 4-6 were heavily missing. This is because of the non-standard sectioning of the races at different tracks. For this reason the team dropped these features from consideration. Place odds is the only other feature with missing data with 4.7% missing. The team decided to impute the missing place_odds values with the mean. The total observations to 79,445.

<img width="700" alt="image" src="https://user-images.githubusercontent.com/37990637/158272715-96d4496d-3eee-4303-8409-6be82e9fce5d.png">

Next, the team reviewed correlations between the variables which allow you to see where there a significant positive or negative relationships.

<img width="700" alt="image" src="https://user-images.githubusercontent.com/37990637/158272622-64bfc1d7-84e8-41df-9749-9e758ab2665c.png">

Using the correlation between variables, the team could dive deeper to visualize the relationships between variables. For, example the relationship between the horse's age and place odds can be seen below:

<img width="502" alt="image" src="https://user-images.githubusercontent.com/37990637/158274095-22a7ae46-821f-4939-bbb8-4d85ba9edf47.png">

Using the relationship insights from this EDA, the team was able to effectively create classification models using relevant features such as: Draw, Win_Odds, Place_Odds, Horse_Age, etc.

[Back to Top](#BackToTop)

<a name="P2"></a>

## Part 2 - SVM and LR Modeling

[Part 2 - SVM and LR Modeling Report](../main/2_SVM_LR_Modeling/SVM_LR_Modeling_Final.ipynb)

The full step-by-step analysis is included in the detailed report. Using standardization and one-hot encoding, the team uses Logistic Regression and Support Vector Machines to classify Win and Show. The team used 80% of the data for training and 20% for testing. The team outputted the models in a confusion matrix (shown below for the top SVM model) and reported key metrics such as accuracy and auc. The team began including precision in Part 3 which is the best metric for this specific use case.

<img width="634" alt="image" src="https://user-images.githubusercontent.com/37990637/158275271-6696fed0-1be6-47e8-b309-2c877173b624.png">

Next, the team looked at feature importance. Shown below, the team looked at the importance from the top logistic regression model. The feature is more significant as the value goes to -1 or 1. If the feature is close to 0 then it is insignificant. We can see win_odds is the most significant feature.

<img width="381" alt="image" src="https://user-images.githubusercontent.com/37990637/158275549-2901fdc3-4496-46c1-817c-c463a7d5aebb.png">

Support Vector Machines outperformed Logistic Regression in this classification.

[Back to Top](#BackToTop)

---

<a name="P3"></a>

## Part 3 - KNN, NB, and RF Modeling

[Part 3 - KNN, NB, and RF Modeling Report](../main/3_KNN_NB_RF_Modeling/KNN_NB_RF_Modeling_Final.ipynb)

The full step-by-step analysis is included in the detailed report. The team moved to a stratified 10-fold cross validation to better account for the imbalance in the data while training and testing. The team also shifted to precision as the highest importance measurment metric. Using standardization and one-hot encoding, the team optimized models for K-Nearest Neighbors, Naive Bayes, and Random Forest Models. For KNN, the team explored multiple distance calculations and number of neighbors. For Naive Bayes, the team explored the Gaussian and Complement methods while optimizing the smoother parameter. For Random Forest, the team tuned the number of trees and the depth of the model. The model results on the testing data were outputted into a confusion matrix with the key metrics as shown below:

For Predicting Win:

<img width="630" alt="image" src="https://user-images.githubusercontent.com/37990637/158277331-4efbaf75-ea2b-4dc5-aa76-9f47af867ddc.png">

For Predicting Show:

<img width="634" alt="image" src="https://user-images.githubusercontent.com/37990637/158278163-db8238a3-c774-4e89-bbe6-0817b7b42401.png">

The report reviews models created using manual feature selection vs recursive feature selection. An example of the recursive feature selection plot is shown below.

<img width="398" alt="image" src="https://user-images.githubusercontent.com/37990637/158277875-71919306-6ad2-4085-b6ee-c62b21a7155b.png">

Also, the report tests if the results of the models are significantly different statistically and the feature importance of the features in the models. The top model for predicting Win and Show were both by the Random Forest model. The Random Forest model also beat out the previous Support Vector Machine.

[Back to Top](#BackToTop)


---

<a name="P4"></a>

## Part 4 - Clustering

[Part 4 - Clustering Report](../main/4_Clustering/Clustering_Final.ipynb)

The goal here was to forecast Texas Covid Case Count with Time Series analysis. After extracting and cleaning the data for analysis, our team performed a thorough analysis using simple and complex models such as ARIMA, VAR, MLP, and Ensembling Techniques. The final model with ensembling VAR and MLP achieved a final RMSE of 903 for the one week forecast and 1032 for the three-week forecast. For a state with over 29 million people, this forecast using mobility, vaccinations, and testing data is more than sufficient to give policy makers a clear idea of the upcoming covid case trends. With this information, more informed policy decisions can be made.

[Back to Top](#BackToTop)

---

<a name="References"></a>

## References

[Kaggle Dataset](https://www.kaggle.com/gdaley/hkracing)

[Part 1 - EDA Report](../main/1_EDA/EDA_Final.ipynb)

[Part 2 - SVM and LR Modeling Report](../main/2_SVM_LR_Modeling/SVM_LR_Modeling_Final.ipynb)

[Part 3 - KNN, NB, and RF Modeling Report](../main/3_KNN_NB_RF_Modeling/KNN_NB_RF_Modeling_Final.ipynb)

[Part 4 - Clustering Report](../main/4_Clustering/Clustering_Final.ipynb)


##### Technologies
R Studio  
R version 4.1.2

[Back to Top](#BackToTop)
