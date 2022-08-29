# Data_Slinging_Slasher

Rakamin Batch 23

Data Set: E-Commerce

1. I Putu Agastya (Lead)
2. Ahdan A R
3. Ahmad Afif
4. Alfredo Meirexa
5. Almas Rausan Fikri
6. Arsya Chairani
7. Riyandhika

Dataset: https://www.kaggle.com/datasets/prachi13/customer-analytics

## Context
An international e-commerce company based wants to discover key insights from their customer database. They want to use some of the most advanced machine learning techniques to study their customers. The company sells electronic products.

## Dataset Explanation
The dataset used for model building contained 10999 observations of 12 variables.
The data contains the following information:

* ```ID```: ID Number of Customers.
* ```Warehouse block```: The Company have big Warehouse which is divided in to block such as A,B,C,D,E.
* ```Mode of shipment```:The Company Ships the products in multiple way such as Ship, Flight and Road.
* ```Customer care calls```: The number of calls made from enquiry for enquiry of the shipment.
* ```Customer rating```: The company has rated from every customer. 1 is the lowest (Worst), 5 is the highest (Best).
* ```Cost of the product```: Cost of the Product in US Dollars.
* ```Prior purchases```: The Number of Prior Purchase.
* ```Product importance```: The company has categorized the product in the various parameter such as low, medium, high.
* ```Gender```: Male and Female.
* ```Discount offered```: Discount offered on that specific product.
* ```Weight in gms```: It is the weight in grams.
* ```Reached on time```: It is the target variable, where 1 Indicates that the product has NOT reached on time and 0 indicates it has reached on time.

## Summary
On the first stages we already did an exploratory data analysis, visualization, and pulling out business insights. From the results of analysis and visualization, it is known that at discounts above 10%, all goods are delayed, while discounts below 10% are goods that arrive on time and there are goods that are late with the ratio of the number of goods arriving on time is higher (53%) . So we from the data science team provide recommendations to the business team to limit the discount rate below 10% so that it can increase the reach on time ratio (on time). Lowering the discount assuming our delivery is late because the shipping cost is not enough or less, due to being cut off by the discount. After the weight segment was implemented, it was found that the 0-2kg, 2-4kg, and 6-8 weight segments experienced a lot of delays, but not the 4-6kg weight segment. So we from the data science team provide recommendations to the business team to recommend customers to become the 4-6kg heavy segment by giving a discount of less than 10% for the 4-6kg weight segment in order to increase the reach on time ratio (on time).

While on second stage we did Data Cleansing and Feature Engineering. There are several features that have high relevance including (weight_in_gms), (discount_offered), (cost_of_the_product), and (product_importance_high). Therefore, these four features will be used to make feature extraction. However, because there are only a few original features and there is an assumption that the model will be underfit, all features, except ID, will still be used. We added some feature extraction such as profit, shipping cost, is expensive, is important, and repeat order.

The third stage is Machine Learning Modelling and Evaluation. There are four datasets that are modeled: Dataset with handling outliers based on IQR, Dataset with handling outliers based on 90th percentile, Dataset without handling outliers, (1) Original and (2) Added feature extraction (profit, shipping cost)To find the baseline, we use several algorithms, namely: AdaBoost, Logistics Regression, Decision Tree, Random Forest, SVC, KNN, Xgboost.
The main model selection is based on the best fit value of ROC AUC data testing and training data. We are looking for a baseline model that is neither overfitting nor underfitting. After that, we look for the model with the highest precision value on label 0, and the recall value on label 1 with the highest. we have ensured that the model has the best fit on the AdaBoost model after feature extraction, with the ROC AUC value in training and testing the same value of 0.76. The ROC AUC value above 0.7 also indicates that the model prediction is feasible to use and is better than random guessing.
