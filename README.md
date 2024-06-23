# Prediction of Real Estate Prices
## Project Overview
This project aims to predict sale prices of real estate using a dataset of known houses and its prices in the housing market. We implement a Random Forest Regression Algorithm to predict Real Estate prices based on features such as YearBuilt, HouseStyle, Utilities and many more.
In this project, I have implemented data preprocessing using pipeline which fills in missing data on both categorical and numerical columns using SimpleImputer and encodes categorical data using the OneHotEncoder function from ```scikit-learn```. I also implemented GridSearchCV for hyperparameter tuning to achieve the best estimator of models with varying parameters
## Dataset
The dataset used in this project is ```houses.csv```,which contains 1460 observations and 81 total features that determine house sale prices. During data preprocessing, some of these features that exhibit high cardinality will be removed due to its irrelevance and troublesome-ness when one-hot encoding
## Feature Manipulation
1. Implemented KMeans Clustering, an unsupervised ML algorithm, of a few existing numerical and continuous features  and added a Cluster column to the houses dataset
2. Made use of the "Elbow" method, which plots the WCSS (Within Cluster Sum of Squares) for different number of clusters, to find the optimal ```n_clusters```. This graph is uploaded as a .jpg file under the same directory as this README.md file. 
## Data Preprocessing
Several preprocessing steps were implemented on the dataset to allow for accurate predictions
1. Removing categorical columns with high cardinality, as implementation alongside OneHotEncoding will result in too much columns
2. In the data preprocessing pipeline, implement ```SimpleImputer``` and ```OneHotEncoding```
   
## Model Training and Hyperparameter Tuning
This project utilises GridSearchCV to perform hyperparameter tuning on 3 distinct parameters of RandomForestRegressor, mainly number of estimates, maximum depth of trees and the minimum number of samples required to split a node.
## Results
1. Best Parameters for Random Forest:
   ```
   {'model__max_depth': 10, 'model__min_samples_split': 2, 'model__n_estimators': 300}
   ```
2. Best Model Score: ```0.8591347585695386```
3. MAE: ```17527.008006470056```
4. R-Squared score: ```0.84```
5. Accuracy: ```84%```
6. Predictions:
```
    Id     Predicted Sale Price
0  530         209075.729548
1  492         149656.917865
2  460         107802.979228
3  280         223541.245586
4  656          92775.964414
```
## Conclusion
The Random Forest regression model equipped with optimal hyperparameters was able to demonstrate a strong ability in predicting house sale prices through its highly minimzed MAE (Mean Absolute Error) and relatively high accuracy and R Squared score. The steps I took during the Data Preprocessing stage proved to be beneficial to the model trained. With these results, it indicates that the model is relatively competent in estimating sale prices based on a large set of features.
