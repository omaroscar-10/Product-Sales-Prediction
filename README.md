#**Product-Sales-Prediction**

Predicted the total number of people who buy the product after seeing the ad. 


# **1. Introduction**

The purpose of marketing is to drive sales and although the goal of each ad campaign will vary, the goal of businesses and companies is to sell more to more people, more often and at higher prices. 

**Problem:**  Some small and large businesses lose a lot of money on bad marketing campaigns because they are not targeting potential customers.

As a small business, we cannot afford to lose money on bad marketing campaigns; we need to get our marketing message directly to prospective consumers, not to everyone.

**Solution:** predicting the number of sales can save businesses a lot of money by not targeting people who might have a low probability of buying a product or service. Forecasting sales will allow them to focus on those who have the highest likelihood of buying a product or service.

In a performance-based model, advertisers pay for consumers activities that drive a campaign goal (**sales**). That’s why predicting the number of sales is an important information for companies and advertisers. Because knowing the number of sales in advance can help businesses and other entities figure out if their advertising strategy is worth it or not. After all, we want to make money, not lose it. 

Therefore, this analysis will predict the total number of people who buy the product after seeing the ad (Approved Conversion).


#**2. Data**

The original dataset is called *Sales Conversion Optimization* and was downloaded from Kaggle website: [Sales Conversion Optimization](https://www.kaggle.com/loveall/clicks-conversion-tracking)
The data is about an organization's social media ad campaign. It contains 1143 observations and 11 variables. 

Approved Conversion, which represents the total number of people who bought the product after seeing the ad, will be the target variable. Because it's a continuos variable, we are dealing with a regression task.


#**3. Methodology**

###**Data Cleaning:** In this step, I will eliminate any problems from the dataset which would prevent further analysis.

###**Data Exploration:** In this step, I will apply statistics and visualization techniques to gain a better understanding of the dataset.

###**Feature engineering:** In this final step of Exploratory Data Analysis (EDA), I will select the most useful features or create new features from the existing ones.

###**Modelling:** Apply several models to predict the number of sales and select the best performing model.


**Model 1: Random Forest Regression**

I will use random forest in the model which can be used for both classification and regression tasks by constructing a multitude of decision trees (generally outperform decision tress). The main difference is how the votes are aggregated. As a classifier, the most popular outcome (the mode) is returned. And as a regression, it is typically the average (the mean) that is returned.


**Improving the model**

To grow profitably in today’s market, advertisers need to target key conversion metrics and analyze consumers behaviors. 

Some of the KPIs that digital advertisers use to identify prospects who are most likely to convert are: CPC, CPM, and CVR. 

**Cost Per Click (CPC)**: measures the cost you pay for each unique visitor from an online paid media ad.

**Cost Per Mile (CPM)**: is the cost advertisers pay for every thousand impressions during an ad campaign.

**Conversion Rate (CVR)**: refers to the percentage of users who view a mobile ad and click on it before completing some conversion activity.

Therefore, I will create these new features and use them to predict Approved Conversion. I will not include the age dummy variable in the feature set. And I will change some of the parameters of the RandomForestRegressor() function (n_estimators=250, criterion="mse", max_depth=6, max_features=2).


**Model 3: Gradient Boosting Regressor**

Although random forest is a strong performer; one of its disadvantages is that it will not predict outside of the sample.

Taking this into consideration, I will use Gradient Boosting Regressor to improve the prediction of Approved Conversion.


#**4. Results**

We kept Impressions, Clicks, Spent, and Total Conversion features because they have the strongest correlation to the outcome (Approved Conversion).

In addition, we also added CPC, CPM, and CVR because these conversion metrics increase the predictive power of the model. 

**Based on the R-squared, MAE, MSE, and RMSE values Model 4 is the top performer**. It has the highest R-squared value(0.9734) and the lowest MAE, MSE, and RMSE values (0.0691, 0.0820, and 0.2865 respectively). As a result, Model 4 predicts Approved Conversion better than the other models.


# **5. Discussion & Recommendations**

To reach an audience and make sales, advertisers need a solid marketing strategy because good marketing it’s not successful marketing until the customer has bought a product or service.

From this supervised learning experiment, interested parties will be able to determine whether they should renew the campaign or try another method of outreach. If businesses are not pleased with the number of predicted sales, then they can improve their marketing strategy to attract potential customers in their products and/or services and persuading them to choose them over those of their competitors.

As further analysis, it is recommended to measure and track the price of the product or service. When establishing a price, companies must also consider their marketing costs. However, predicting sales will allow companies determine an adequate price point to sell their products for.

In conclusion, companies or advertisers are expected to increase their customer acquisition volume and number of sales by making the appropriate improvements to their marketing plan.
