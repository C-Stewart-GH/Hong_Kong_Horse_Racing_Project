<a name="BackToTop"></a>

# Hong Kong Horse Racing Performance Prediction using Machine Learning Methods

**Contributors: Cameron Stewart, Nathan Deinlein, Chris Roche, Ryan Kinney**

>The goal of this project was to classify the performance of horses during races in Hong Kong. The purpose of this project was purely academic to explore the use of many classification and clustering algorithms. The classification was for two target variables: Win and Show. Win represents whether or not a horse won the race and show represents whether or not the horse finished in the top three. Both are represented by a binary 0 or 1 value. Precision and AUC were used as the primary evaluation metrics in an imbalanced dataset. The project was sprit into 4 parts with a detailed report written for each. Part 1 - The team explored and visualized the data along with the relationships within and between variables. Part 2 and 3 - Explore using Logistic Regression, Support Vector Machines, KNN, Naive Bayes, and Random Forest for Classification. Part 4 - Explore using Clustering to create features that can be used for Classification. The detailed reports are linked below.

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
<img width="706" alt="image" src="https://user-images.githubusercontent.com/37990637/157994781-70e46845-b80d-4ac9-b466-678e813ab224.png">

All links in [References](#References)

<a name="P2"></a>

## Part 2 - SVM and LR Modeling
First, we looked at the response variable Texas Covid Case Count to determine stationarity. Based on the autocorrelations and the Parzen window, there is strong evidence of wandering and we see some evidence of a seven-day periodic trend both causing non-constant mean. We speculate the seven-day periodic trend is likely attributed to some sort of reporting bias. The first and second have autocorrelation comparison gives us confidence the autocorrelation is staying relatively constant. Since the data is non-stationary, the data will need to be differenced and/or have the frequency removed in the models to stationarize the data.

<img width="706" alt="image" src="https://user-images.githubusercontent.com/37990637/157996557-1dd21c09-dddc-4d7b-954a-16e351224524.png">

Next, we looked at the included features that could help us model the response. Google mobility trends offer us insight into the relative activity into different public sectors. Vaccinations contribute to decreasing the rate of spread. Covid testing can be a leading indicator that describes the relative proportion of the population who thinks they may have covid.

<img width="706" alt="image" src="https://user-images.githubusercontent.com/37990637/157996581-22939eac-6d0c-406d-875b-c0980beee62e.png">

[Back to Top](#BackToTop)

---

<a name="P3"></a>

## Part 3 - KNN, NB, and RF Modeling

The team first explored a simple univariate ARIMA model. By differencing the data and finding the lowest ARMA AIC, we were able to identify the ideal ARIMA model.

<img width="706" alt="image" src="https://user-images.githubusercontent.com/37990637/157997288-321870de-ed69-4f95-a23a-d9566b308052.png">

Plotting the 21-day forecast of Texas Covid Case Count with a 95% confidence interval.

<img width="427" alt="image" src="https://user-images.githubusercontent.com/37990637/157997317-9b0b6ce2-2d1c-412a-82f1-b1372065d3da.png">

Next, the team explored a multi-variate Vector Autoregressive (VAR) model. All the explanatory variables were included in this model. Utilizing AIC and BIC, we confirmed a lag of 8 was the ideal lag for this model. Plotted are the 95% confidence intervals for the forecast of all the included variables. To the right, are the features and coefficients in the model along with their significance.

<img width="706" alt="image" src="https://user-images.githubusercontent.com/37990637/157997444-03a944b9-90d5-49c0-86b1-3dcdc4e965d8.png">

Plotting the 21-day forecast of Texas Covid Case Count with a 95% confidence interval.

<img width="466" alt="image" src="https://user-images.githubusercontent.com/37990637/157997459-a3ecddb1-3045-4b8d-a09b-0cdb6cb70f89.png">

Moving into more complex models, the team trialed a Multi-Layer Perceptron (MLP) Model. Below, is a mapping of the network along with the chosen parameters of the model. The model was trained 20 different times and the median value of the different models was used as the forecast. The number of layers and nodes per layer was verified by cross validation.

<img width="706" alt="image" src="https://user-images.githubusercontent.com/37990637/157997503-639e5e6d-9f23-4ce0-82fb-9b65473b9aa4.png">

Plotting the 21-day forecast of Texas Covid Case Count. Colors: Blue - Actual Case Count, Black - Forecast of Case Count, Grey - 20 different trained models

<img width="478" alt="image" src="https://user-images.githubusercontent.com/37990637/157997520-d8b39f6b-0af2-4bf4-b984-c04e8f13288f.png">

With both the VAR and MLP models outperforming the more simplistic ARIMA model, and ensemble model was generated using both models. The mean of the forecast of both models was used to forecast Case Count. The plot shows the 21-day forecast of Texas Covid Case Count.

<img width="706" alt="image" src="https://user-images.githubusercontent.com/37990637/157997558-e4902723-0bf9-4c91-80fd-f427dcef1e5e.png">

To better see how the forecast of the ensemble model is performing, the last 100 observations were included in the plot.

<img width="706" alt="image" src="https://user-images.githubusercontent.com/37990637/157997581-e9e289cc-e59d-4517-adab-dbfa2bfa5ce6.png">

In the final comparison, we can see the RMSE of the ensemble model is the lowest for the short- and long-term forecast. Therefore, we will move forward with this as our final model.

<img width="706" alt="image" src="https://user-images.githubusercontent.com/37990637/157997604-5f7d9d67-ab11-4c51-836c-f3616020bbe9.png">

[Back to Top](#BackToTop)


---

<a name="P4"></a>

## Part 4 - Clustering

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
