🏠💰 House Price Predictions

Author: Enrique Companioni

💾 Data Insights

- The dataset contains many missing values and outliers. These missing values are mainly in categorical features, where the absence of the feature is represented with a NaN value. The outliers are across various features, but they become particularly noticeable when the sale price is high.
- The data is right-skewed in the majority of the features, included the Sale Price of the Houses.
- The target value (Sale Price of the Houses) is correlated with Overall Quality and Ground Living Area, and to some degree with Garage Cars and Garage Area.

🔄 Data Processing

- Handling Outliers: The most correlated features with the sale price of the houses were treated by removing their most influential outliers.
* Handling Missing Values: The missing values in the categorical features, where absence of the feature was recorded as NaN, were filled with the appropriate value of "No ...(feature related)". Additionally, the absence of the feature induced NaN values in other numerical features, so they were filled with the appropriate values.
- Transform skewed data: Skewed data was transformed to achieve a more normal distribution.
- Encoding data: The categorical data was encoded using Label Encoding for features that were naturally label-encoded. Additionally, the categorical features were transformed using the get_dummies function from the pandas library.
- Add Missing Categorical Features: After removing outliers, some categories were lost. Therefore, the encoded columns need to be added back before passing through the models. Additionally, some columns were reordered.

🧠 Modelling

Eight models (Lasso, Ridge, Support Vector Machine, Elastic Net, KNN, Random Forest, XGBoost, and Gradient Boosting) were trained using the K-Fold technique, specifically with k=7. Then, the best models were chosen and different combinations of predictions were tried to determine the best performance with all the data. Finally, a 50/50 weighted combination of predictions from the Gradient Boosting model and the XGBoost model was chosen. The performance of each model was as follows:
|Model|Mean score|Mean RMSE|
|--|--|--|
|Ridge|0.8943|0.1319|
|SVM|0.9173|0.1159|
|ElasticNet|0.9023|0.1230|
|KNN|0.8600|0.1359|
|RF|0.8652|0.1504|
|XGBoost|0.8991|0.1243|
|GBR|0.9385|0.0930|
