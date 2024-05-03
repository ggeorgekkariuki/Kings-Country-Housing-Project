

## Project Overview
The project aims to analyze home prices and market trends using the King County House Sales dataset. It utilizes data analytics and predictive modeling techniques to identify improvements that result in the highest return on investment. The primary goal is to develop an advisory system for a real estate agency in King County, Washington. This system will aid homeowners in understanding how various modifications to their homes affect the projected value of their property.
![alt text](beachhouses.jpg.webp)
### Business Problem
The goal is to deliver insights to the real estate agency on how to improve return on investment by predicting the price of estates by homeowners based on specific factors. Some of the key objectives include:

Examining which renovation factors have the biggest effects on raising a home's assessed value, i.e. 

- how much will the sale price likely increase by adding floors?

- how much will the sale price likely increase by adding bedrooms?

- what is the expected rise in the selling price of a house that has an addition to its living area?

Nevertheless, there are additional goals as well: developing a predictive model that projects a home's market value growth depending on renovation elements; and tracking trends in the real estate market.
###  Objectives

**To determine Current Market Trends and Best-Performing Features**

- What factors distinguish top-performing properties in terms of sale price?

- Which variables (e.g bedrooms and floors) of the residences raise sale prices?

**To Investigate Popular Features and Preferences Across Time**

- Which housing features and attributes have proven most popular and successful throughout time?

- What types of home features appeal to potential buyers?

**To Investigate How Home Renovations affect Sale Price**

- How does adding floors affect the sale price of a home?

- How does the addition of bedrooms affect the sale price of a home?

- What is the predicted rise in the selling price of a home after an addition to its living space?

**To Inspect Seasonal Trends & Optimal Time to Sell**

- Do home sales and prices follow seasonal patterns?

- When is the greatest time to sell a home for the highest possible price?


## Business Understanding
Background information King County, Washington, is a diversified area encompassing urban, suburban, and rural areas. The housing market is fiercely competitive, fueled by substantial demand from homebuyers and investors. The county provides a variety of housing alternatives, including single-family houses, condominiums, townhouses, apartments, and luxurious estates. The county is home to exceptional schools and educational organizations, including the University of Washington.
The county's robust transportation system effects home demand and pricing. Hiking, skiing, boating, and fishing are all outdoor recreational activities. King County homes provide a desirable balance of natural beauty, economic prospects, and quality of life amenities, making them a popular choice for both homeowners and investors. However, successfully navigating the housing market involves careful study, planning, and consideration of individual requirements and preferences

## Data Understanding
In order to predict the sales price of properties in King County, the research extracts data from the King County House Sales dataset, which includes the kc_house_data.csv file.

It includes 20 homes, 21,597 housing observations, and a column containing the home ID. Homes sold between May 2014 and May 2015 are included in the data. The following are a few pertinent columns to be used in this analysis: price - the amount at which the property was previously sold, bedrooms - the number of bedrooms, bathrooms - the number of bathrooms, sqft_living - the square footage of the home's living area, sqft_lot - the square footage of the lot, floors - the total number of levels in the house, and grade - the overall grade of the property. Concerning the building and layout of the house as well as the year the house was built (yr_built)


### Variables
The aim variable in this project is the "price" of the properties. This suggests that the result or objective variable is predicted or explained by other independent factors, such as the property's characteristics (square footage, number of bedrooms, location, etc.). In statistical modelling and analysis, the variable being modelled or projected based on the values of other variables is the price of a property. These variables will be utilized to provide answers to the data inquiries and provide the real estate firm with useful information on how to forecast prices based on characteristics that influence sales. Additional variables consist of bedrooms, square footage, flooring, grade, year of construction, year of renovation, and sale date. More information on the variables is given at the end of the document.


## Modeling
The modeling process involves employing simple linear regressions using the `visualize_and_evaluate_regression` function. This function enables the analysis of relationships between two variables by visualizing their correlation via scatter plots and fitting a linear regression line to the data. Evaluation metrics such as Mean Squared Error (MSE), Root Mean Squared Error (RMSE), and R-squared (R²) values are computed to assess model performance. For instance, when examining the correlation between the number of bathrooms and home prices in the King County dataset, this function generates scatter plots to visualize the relationship and then trains and tests a linear regression model. By analyzing the resulting evaluation metrics, including MSE, RMSE, and R², insights into the predictive capability of the model are gained, facilitating informed decision-making in real estate analysis.
![Regression models] (main/predictive-modeling-diagram.png)
![alt text](predictive-modeling-diagram.png)
### Simple Linear Regressions
The function `visualize_and_evaluate_regression` serves as a comprehensive tool for analyzing the relationship between the number of features and the price of homes in the King County dataset using simple linear regression. It begins by visually representing these relationship through scatter plots, allowing for a visual inspection of how house prices vary with the features. These visualizations offer an initial understanding of the correlation between these variables, highlighting any potential trends or patterns.

Following the visualization, the function proceeds to fit a linear regression model to the data. This entails determining the best-fitting line that minimizes the squared differences between the observed house prices and the corresponding predictions based on the features. By employing this regression model, the function aims to capture the underlying relationship between the independent variables and the dependent variable (house prices).

Moreover, the function goes a step further by evaluating the performance of the regression model. This evaluation involves partitioning the dataset into training and testing sets to assess how well the model generalizes to unseen data. Subsequently, the function computes various evaluation metrics to gauge the model's predictive accuracy. These metrics include the Mean Squared Error (MSE), which quantifies the average squared difference between predicted and actual house prices, and the Root Mean Squared Error (RMSE), which provides a more interpretable measure of prediction error in the same units as the target variable.

Additionally, the function calculates the R-squared (R²) value, which represents the proportion of variance in house prices that is predictable from the features. A high R-squared value indicates that a significant portion of the variability in house prices can be explained by variations in the features, thereby suggesting a strong relationship between these variables.

Our analysis underscores the crucial role of square footage in determining house prices:

`sqft_living`: Each additional square foot in the living area is associated with a substantial increase in house price, with a coefficient of 282.2015.

`sqft_above`: The above-ground square footage positively influences house prices, with a coefficient of 269.3903, albeit with slightly lower impact compared to living area square footage.

`sqft_basement`: While positively correlated with house prices, the impact of basement square footage is relatively lower, with a coefficient of 273.5959.

These insights highlight the significance of property size in driving house values, providing valuable guidance to the real estate developer in making informed decisions regarding property investments and renovations.
### Multi-Linear Regression Modelling
The model evaluation highlights a strong overall performance, with an R-squared value of 0.706 indicating that approximately 70.6% of the variance in house prices can be explained by the included independent variables. Significantly, the F-statistic's associated p-value of 0.00 confirms the model's statistical significance, affirming the presence of meaningful relationships between the predictors and house prices. While both training and test set errors, as measured by MAE and RMSE, are slightly higher than ideal, their consistency suggests minimal overfitting. Individual coefficients further elucidate the factors influencing house prices, with features such as bathrooms, sqft_living, and waterfront view demonstrating notable impacts. Overall, the model presents a robust foundation for understanding and predicting house prices, offering valuable insights for real estate analysis and decision-making.
**Model Performance:**
- The R-squared value of 0.706 suggests that approximately 70.6% of the variance in house prices can be explained by the independent variables included in the model.
- The F-statistic's associated p-value of 0.00 indicates that the model is statistically significant, suggesting that at least one independent variable has a non-zero coefficient.
- Mean Absolute Error (MAE) and Root Mean Squared Error (RMSE) measures assess the average magnitude and magnitude of errors in predictions, respectively. A lower value indicates better model performance.

**Analysis:**
- Both training and test set MAE and RMSE values are relatively close, indicating consistent model performance between the training and test datasets.
- Although the test set MAE and RMSE are slightly higher than the training set values, the difference is not significant, suggesting minimal overfitting.
- Lower MAE and RMSE values indicate better predictive performance, indicating that the model effectively predicts house prices.

**Coefficient Interpretation:**
- The coefficients represent the change in the target variable (house price) for a one-unit change in the corresponding predictor variable, holding all other predictors constant.
- Positive coefficients imply that as the feature increases, the house price tends to increase, while negative coefficients suggest the opposite.
- For instance, a positive coefficient for "bathrooms" indicates that houses with more bathrooms tend to have higher prices, while a negative coefficient for "yr_built" suggests that older houses tend to be cheaper.

**Recommendation:**
- Given the high R-squared value and statistical significance of the model, further investigation into the individual coefficients can provide valuable insights into the factors influencing house prices, guiding decision-making in real estate analysis. Specifically, features such as bathrooms, sqft_living, and waterfront view (as indicated by their coefficients) warrant deeper exploration due to their significant impact on house prices.
## Regression Results
The initial simple linear regression analysis revealed limitations in the model's predictive capability, as indicated by low R-squared values and high Mean Squared Error (MSE). Despite identifying variables such as sqft_living, sqft_above, and bathrooms with relatively higher R-squared values, they alone had a limited ability to predict house prices. Consequently, a recommendation was made to conduct a multiple regression analysis to explore these features collectively. The subsequent multiple linear regression analysis demonstrated a strong overall performance, with an R-squared value of 0.844 indicating a substantial proportion of the variance in house prices explained by the model. The statistical significance of the model was confirmed by the F-statistic's associated p-value of 0.00, while individual coefficients provided valuable insights into the impact of features such as bathrooms and yr_built on house prices. These findings contribute to a comprehensive understanding of factors driving house prices and offer actionable insights for real estate analysis and decision-making.

## Conclusion
In conclusion, the analysis of the King County House Sales dataset has provided valuable insights into the factors influencing home prices and market trends. Through the application of data analytics and predictive modeling techniques, we have identified key variables such as the number of bathrooms, square footage of living space, and other features that significantly impact property values. The development of regression models, both simple and multiple, has allowed for the quantification of these relationships and the evaluation of their predictive performance. Despite initial challenges with limited explanatory power in simple linear regression, the adoption of multiple regression has yielded more robust models with higher R-squared values, indicating a better fit to the data. Overall, this project aims to support decision-making processes for real estate agencies in King County, Washington, by providing actionable insights into how various home modifications and features affect property values. By leveraging these insights, stakeholders can make informed decisions to maximize returns on investment and better serve homeowners in understanding the dynamics of their local real estate market.

### Solutions offered by our analysis

**Current Market Trends and Best-Performing Features**

Our analysis reveals that certain types of homes are currently selling better in the market based on their price, with features such as square footage of living space, number of bathrooms, and other amenities playing significant roles in distinguishing top-performing properties. By identifying these factors, real estate agencies can better tailor their offerings to meet market demands and optimize their sales strategies.

**Popular Features and Preferences Across Time**

Through our analysis, we've identified housing features and attributes that have consistently proven popular and successful over time. Understanding current trends in homebuyers' preferences, as well as their preferences according to property ratings and reviews, can provide valuable guidance for property developers and real estate agents seeking to meet customer needs effectively.

**Home Renovations and Sale Price**

Our analysis also sheds light on how various home renovations, such as adding floors or bedrooms, can impact the sale price of a home. By quantifying the predicted rise in selling price after specific renovations, homeowners can make informed decisions about potential investments in their properties to maximize returns.

**Seasonal Trends & Optimal Time to Sell** 

By examining seasonal patterns in home sales and prices, our analysis helps to identify the optimal time to sell a home for the highest possible price. Understanding these trends allows sellers to time their listings strategically and capitalize on periods of peak demand in the market.
