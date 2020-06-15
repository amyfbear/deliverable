
# R2Net Deliverable
- Amy Ontiveros-Bear


## Analysis Guidelines: 

**Your deliverable should include the following:**

The script you developed to clean the CSV A copy of the cleaned CSV Your analytical answers organized in an Excel sheet with the data or data summary used and a brief description of how you found the answer

At minimum, your script should address the following:

Identify and clean typos, misspellings, and other standard human errors

Remove the time stamp from ORDERDATE column

Add a dollar sign to any money-related columns

Separate the Month and Year into two separate columns

Remove blank columns



## Analysis Answers:

**What is the population average quantity per order?**

- 34.09

This was taken by grabbing the mean of the "Quantity Ordered" Column.

**What is our top selling product?**

- Classic cars, Product Code: S18_3232
- This comprises 2.9% of our total sales & 1.8% of our total inventory ordered for 2003-2005
- Found by grouping by "Product Line" & "Product Code" then sorting the dataframe by the "Sales" column.

**What was our strongest sales period by volume? By value?**

- Overall Q4 is the strongest period by volume (38.5% of total orders) and by value (38.6% of total sales)
for 2004 & 2003 it is Q4 for 2005 it is Q1 because we do not have data for Q3 or Q4 for that year.

- By month and quarter it is November with 21.1%($2,118,885.67) of total sales and 21.1% of inventory during Q4.

Found by grouping by "Quarter ID" then sorting by "Sales", to find the volume I just sorted by "Quantity Ordered" instead of sales. To find the top month and quarter I just grouped by "Month" and "Quarter ID", sorted by "Sales" then sorted by "Quantity Ordered".

**What is our top selling region by volume? Is this the same as by value?**

- Top selling region is EMEA (Europe, Middle East & Africa) for 2003-2005, it is the same as by value
EMEA comprises 49.6% of our total sales & 49.7% of our total inventory ordered.


Found by grouping by "Territory" then sorting by "Sales", to find the volume I just sorted by "Quantity Ordered" instead of sales.

**Put together summary metrics and a brief description of your observations for each type of DEAL SIZE**

This should include, at minimum:

sample averages and a list of the top 5 clients for each category


### Large Deals

Deals are between 7,016.31 - 14,082.80 dollars comprise **12.98%** of total company sales and are mainly classic cars.

#### Euro Shopping Channel:

- Total Sales: $94,225.41

- .9% of total sales

- 7.2% of large deal's sales

#### Mini Gifts Distributors Ltd:

- Total Sales: $93,159.76

- .9% of total sales

- 7.2% of large deal's sales

#### The Sharp Gifts Warehouse:

- Total Sales: $53,442.10

- .5% of total sales

- 4.1% of large deal's sales

#### Danish Wholesale Imports:

- Total Sales: $53,442.10

- .4% of total sales

- 3.2% of large deal's sales 

#### Muscle Machine Inc:

- Total Sales: $53,442.10

- .4% of total sales

- 3.1% of large deal's sales   
    
### Medium Deals

Deals range from 3,002.4 - 6,996.42 dollars, make up **60.9%** of total deal sales and consist mainly of Classic cars and Vintage cars.


#### Euro Shopping Channel:

- Total Sales: $580,216.42

- 5.8% of total sales

- 9.5% of medium deal's sales
    
#### Mini Gifts Distributors Ltd:

- Total Sales: $408,562.74

- 4.1% of total sales

- 7.6% of medium deal's sales

#### Muscle Machine Inc:

- Total Sales: $128,034.90

- 1.2% of total sales

- 2.1% of medium deal's sales

#### Australian Collectors, Co.:

- Total Sales: $124,630.90

- 1.2% of total sales

- 2.0% of medium deal's sales 

#### La Rochelle Gifts:

- Total Sales: $122,367.40

- 1.2% of total sales

- 2.0% of medium deal's sales   

    
 ### Small Deals

Deals range from 482.13 - 2999.97 dollars, make up **26.3%** of total deal sales and consists mainly of Classic cars and Vintage cars.

**Euro Shopping Channel:

- Total Sales: $237,852.28

- 2.4% of total sales

- 90% of small deal's sales

**Mini Gifts Distributors Ltd:

- Total Sales: $153,135.56

- 1.5% of total sales

- 5.8% of small deal's sales

**Australian Collectors, Co.:

- Total Sales: $57,325.62

- .5% of total sales

- 2.2% of small deal's sales

**Rovelli Gifts.:

- Total Sales: $56,972.88

- .57% of total sales

- 2.2% of small deal's sales 

**Land of Toys Inc.:

- Total Sales: $57,325.62

- .53% of total sales

- 2.0% of small deal's sales 
    
    
I created masks the for all deal sizes then made new data frames with only those values. I then used .describe() to grab summary metrics for all new deal size data frames.

**Observations:

We have missed out on $56,959.39 overall due to the difference of MSRP to our actual sale price.


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
