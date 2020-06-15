# R2Net Deliverable
- Amy Ontiveros-Bear



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

- AMER comprises 38.4% of our total sales & 38.3% of our total inventory ordered.

- APAC 12% of our total sales & 12% of our total inventory ordered.


Found by grouping by "Territory" then sorting by "Sales", to find the volume I just sorted by "Quantity Ordered" instead of sales.

**Put together summary metrics and a brief description of your observations for each type of DEAL SIZE**

This should include, at minimum:

sample averages and a list of the top 5 clients for each category


## Deal Size Analysis:

### Large Deals

Deals are between $7,016.31 - $14,082.80, they comprise **12.98%** of total company sales and are mainly classic cars.

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

Deals range from $3,002.4 - $6,996.42, they make up **60.9%** of total deal sales and consist mainly of Classic cars and Vintage cars.


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

Deals range from $482.13 - $2,999.97, they make up **26.3%** of total deal sales and consists mainly of Classic cars and Vintage cars.

#### Euro Shopping Channel:

- Total Sales: $237,852.28

- 2.4% of total sales

- 90% of small deal's sales

#### Mini Gifts Distributors Ltd:

- Total Sales: $153,135.56

- 1.5% of total sales

- 5.8% of small deal's sales

#### Australian Collectors, Co.:

- Total Sales: $57,325.62

- .5% of total sales

- 2.2% of small deal's sales

#### Rovelli Gifts.:

- Total Sales: $56,972.88

- .57% of total sales

- 2.2% of small deal's sales 

#### Land of Toys Inc.:

- Total Sales: $57,325.62

- .53% of total sales

- 2.0% of small deal's sales 
    
    
I created masks the for all deal sizes then made new data frames with only those values. I then used .describe() to grab summary metrics for all new deal size data frames.


### Summary Statistics:
#### Large Deal Stats
 
![Large Deal stats](/images/Large_deals_summary_Statistics.png)

#### Medium Deal Stats

![Medium Deal stats](/images/Medium_deals_summary_statistics.png)

#### Small  Deal Stats

![Small Deal stats](/images/Small_deals_summary_statistics.png)


### Observations:

- We have missed out on $56,959.39 overall due to the difference of MSRP to our actual sale price.

- It is odd that we have not tapped into the Latin American market, or at least Mexico (since we are selling to Canada already we have the NAFTA advantage)
