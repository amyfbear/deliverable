# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png)Capstone :  Predicting Daily Sales w/ SARIMAX for Budget Customization¶

- Amy Ontiveros-Bear


## Problem Statement

I am a consultant hired by restaurant owners from a wine and pizzeria concept, since new management has taken over their costs have gone through the roof and now, they are 25K in the red on average each month. For them to recoup their loss I need to figure out how to properly structure their budgets. I will create a SARIMAX predictive sales model to base my customized budgets from. My metric will be RMSE to gauge my model's performance with because the output will be on the same scale as my data. A successful model will output predictive sales values within a $530 range. My model Selection metric will be AIC because of it's ideal use case of smaller data sets such as mine.

# Executive Summary

Data Procurement; I gathered the data from Touchbistro which is a cloud-based POS (Point of Sale) platform that the company uses. It was exported via 5 separate csv files, that were cleaned then concatenated.The data is from June 1st, 2018 – February 16th, 2020. Quarterly information was only obtained for Q3 & Q4 for 2018 and then all of 2019. Data preproecessing; data was read in as “objects” which then had to be cleaned and converted to their appropriate data types in order to be utilized in my SARIMAX model. SARIMAX models are dependent on a sorted date index with set period frequencies. 

EDA; I looked at the correlation heatmap of daily sales to get a better sense of what were the best predictors and to visualize any features  that should be dropped because they are too correlated. "Margin" and "Net Sales" had to be dropped with a positive correlation of 1 percent. Daily Gross Sales are not normally distributed and skewed with what looks like a mean around $4,000.00. 
Bill Count, Labor Cost, Margin and Net Sales all have similar distributions as Gross Sales which means they are probably highly correlated


While exploring quarterly trends I discovered that Daily Gross Sales were stagnant with a growth on average of 1.1 percent when comparing Year over Year Q3 VS Q4 of 2018 and 2019 data. The most interesting observation I noticed was Q1 to Q2 of 2019 the daily gross sales mean increased by $749.00. The quarterly features distributions for the most part tend to follow the same trend as as above, where they are similar to daily gross sales's and are left skewed. 

These features with similar distributions are also proved to be correlated by visualing the heatmap correaltion graph.Bill count, labor cost and voids tend to have more similar distributions on a quarterly range than on a whole data range. In order to model you must ensure stationarity before modeling. My data has a p-value 0.000280 which gives us evidence to reject the null hypothesis, meaning we accept that our time series is stationary.The ACF and PACF plots showed that the obervations are follow similar trends and are correlated. However ultimately I chose my parameters based on a manual gridsearch of my data. For my model prep I had to split the index manually at the row with 75% of my data for my train set and the other 25% for my test/validation set.Indexes had to be converted to Datetime index with a frequency of “d” in order to be fed into the model. 
My model's RMSE is off by a mean of around 530 which is way better than my baseline model.

---

### Data Sources

[Touchbistro](https://cloud.touchbistro.com/)

[Private Access to Company Data]


---

### Data Dictionary


|Feature|Type|Dataset|Description|
|---|---|---|---|
|Bill Count |int64|TouchBistro|number of bills.|
|Voids|float64|TouchBistro|items that are NOT made, there is no increase or decrease of revenue. |
|Gross Sales|float64|TouchBistro|total revenue made without the deduction of voids or discounts.|
|Discounts|float64|TouchBistro|items that ARE made and sold at reduced price.|
|Menu Item Cost| float64|TouchBistro|total cost of raw perishable goods ordered directly from vendors at wholesale prices.|
|Labor Cost|float64|TouchBistro|total labor cost.|

---

## Conclusion

In conclusion I was able to build a model up to my standards however it was an in-sample model. For this to be applied correctly I will have to go back and look at my out of sample model notebook and figure out how to improve it. As it is completly unusable with a RMSE of 1896 which is no good. I can still look at my Actual Costs vs Actual Sales and offer budget customizations as I did in the functions in my budget reccomendations section. When I do get my out of sample model working I can use the same function  to calcuate the custom budgets.


## Recommendations & Next Steps

Total Prime costs are on average 20% over the suggested budget.
The main culprit is BOH labor and food costs.
The chef needs to be under weekly budget reviews for his food and labor costs.
Cross train back of house staff to work different stations so there are not more staff than needed. 
The budgets in the mean time will be based on the Previous week’s sales till a proper out of sample model can be provided.

- Total prime less than 50%
- Food cost 20% MAX
- Labor cost BOH 15% MAX
- Labor cost FOH 12 % MAX

For the business they should look at different vendors and request price sheets to compare to current ones. Look into payment plans for vendor accounts to aid in recouping costs. Although BOH labor and food costs seem to be the main issues, if I could gain access to the P & L report it would be helpful to see where other areas could be improved upon. They might consider opening earlier than 3PM to capture the lunch crowd and launch a happy hour program along with a cocktail menu. If they paid for a liquor license, they should be using it. Beverage programs have a higher profit margin than food and with a properly implemented program it could increase sales up to 5-10 K a week. Look into third party delivery services such as seamless to add a new revenue streams. When I do get my out of sample working I can use the same functions above to calcuate the custom budgets. For the out of sample model Gather more data. Log transform data, I tried this on in sample data for modeling and it was not useful but might be for this model. Try out another model like an RNN that can be utilized on Time Series data.




## References

[Touchbistro](https://cloud.touchbistro.com/)

[towardsdatascience](https://towardsdatascience.com/time-series-forecasting-with-a-sarima-model-db051b7ae459)

[machine learning mastery](https://machinelearningmastery.com/grid-search-arima-hyperparameters-with-python/)
