# Portfolio
General Portfolio


Levi's Project
  1) Browse project overviews.
 I browsed the SAS projects and chose the following:
https://www.sas.com/en_us/customers/levi-strauss.html
  2) Pick a project for which you think at least three different Analytics models might have been combined to create the solution.


 Levi Strauss & Co. crafts better customer experiences through big data and analytics
For one of the world’s most recognizable apparel brands, getting it right for the consumer has been the No. 1 priority for over 160 years. The company that invented blue jeans is always innovating. And Levi Strauss & Co. is on a journey with SAS® to build an analytically driven, decision-ready culture that helps it connect to the people who love its apparel. Learn how in the video above.
   Challenge
Analyze millions of consumer demand signals to create a supply chain geared to the preferences of individual customers.
Keep Levi’s products in stock for retailers and wholesalers.
   Solution
By using SAS® Analytics, Levi Strauss & Co. can optimize plans and predict opportunities through merchandise planning, allocation and inventory management.
Through smarter demand plans and a supply chain geared to the preferences of
 
   Stay globally connected, yet regionally aware, by creating demand forecasts down to each style, color and size.
   millions of customers, consumers around the world can find the merchandise they want.
Levi Strauss & Co. can make data-driven decisions, leading to increased growth and a genuine competitive advantage.
 3) Think carefully and critically about what models might be used to create the solution, how they would be combined, what specific data might be needed to use the models, how it might be collected, and how often it might need to be refreshed and the models re-run.
The challenge is stated in three distinct delineations:
1) Analyze millions of consumer demand signals to create a supply chain geared to the
preferences of individual customers.
2) Keep Levi’s products in stock for retailers and wholesalers.
3) Stay globally connected, yet regionally aware, by creating demand forecasts down to
each style, color and size.
Additional challenge considerations:
- Analyzing a large dataset/s of millions.
- Estimating customer interest in new styles.
- Estimating lost sales when stock runs out.
- Estimating overspent capital on unsold overstock. - Majority of products sourced from China.
The above three delineations will use three or more models.
1) Analyze millions of consumer demand signals to create a supply chain geared to the
preferences of individual customers. Given:
- From a large dataset, select and optimize for indicators of customer wants and
use these indicators to predict stock needs for each product SKU.
- We are not taking into consideration shipping costs or other cost factors.
- Daily retail sales reports including style, size, colors, and retail address.
- Daily online sales records for style, size, colors, and shipping address. Use:
- PCA

- Regression.
- Linear probability model.
To:
- PCA to reduce the factor considerations, to possibly find correlations for
predictive modeling later.
- Regression to forecast demand based on consumer preferences.
- Linear probability model to create a probabilistic model of demand.
2) Keep Levi’s products in stock for retailers and wholesalers. Given:
- Millions of data points.
- Product sales numbers.
- We are not taking into consideration shipping costs or other cost factors. - We assume products move one way in the supply chain from wholesalers
downstream to retailers. (There may be a possibility that products move laterally
between retailers.) Use:
- So, what strategy would isolate key selectors from a large group? Possibly ANOVA.
- Queuing model.
- Optimization model.
- A network optimization model. To:
- We can use ANOVA to compare the weight/importance of factors by comparing
the means of various samples. For a large data set this may be impractical to
analyze two data sets at a time.
- Queuing model to simulate movement of stock at points in the supply chain. This
might be thought of as a version of the airport queuing in-out problem. There is a time aspect to this where we want to know how long it takes to move in and out of each queue point based on an exponential probability distribution of time between events in a Poisson process.
- Optimization model to determine the number of and how the products will be distributed to stores globally.
- A network optimization model to determine product flow in the supply chain.
3) Stay globally connected, yet regionally aware, by creating demand forecasts down to each style, color and size.
Given:
- Sales records.
- Product sales correlations.
- Online sales records.
- Online sales delivery addresses.
- Seasonal effect on clothing types.

Use:
- Regression trees (CART)
- Optimization model.
- Linked constraints.
- A network optimization model.
- For a dynamic demand model, we might use an ARIMA model, an autoregression
(uses previous sales/inventory to estimate demand) that includes a moving average of daily sales.
To:
- Regression trees (CART) to fork decisions based on regression demand
optimizations for each averaged customer avatar, for each style, color, and size. - Optimization model to determine the number of and how the products will be
distributed to stores globally.
- A network optimization model to optimized distribution of the product.
- A dynamic demand model such as ARIMA to incorporate moving daily sales
averages to estimate demand.
What THREE models might have been used to create the SAS solution to this problem?
1) Regression and linear probability models to forecast demand.
2) Regression trees (CART) to fork decisions based on regression demand optimizations. 3) Queuing model to simulate movement of stock at points in the supply chain. This might
be thought of as a version of the airport queuing in-out problem. There is a time aspect to this where we want to know how long it takes to move in and out of each queue point based on an exponential probability distribution of time between events in a Poisson process. We want to keep items continually in stock without delay.
4) This is also an example of a network optimization model.
5) Optimization model to determine the number of and how the products will be
distributed to stores globally.
4) Write a short report describing you answers to (3).
How would these models be combined?
Use optimizations and probabilistics to hone and influence the tree, queue, and network models.
What specific data might be needed to use the models? - Sales data.
- Customer locations.
- Inventory numbers.
- Dates of sales.
- Customer indicators of interest on websites.

- - -
How that data -
- - - -
Logistics inventory product tracking. Seasonal predictors.
Social media trend data.
might be collected?
Sales receipts from stores.
Inventory tracking by region.
Website sales.
Website stats on customer indicators of interest. Social media data mining.
How often the data might need to be refreshed and the models re-run? - Daily for in store data.
- Daily for website data.
- Daily for distribution of inventory from warehouses to individual stores. The
localized regression and linear probability demand models are the base sink
nodes that aggregate up the chain to wholesale demand.
- Weekly for large inventory movements between continents from production
source to wholesale points at each continent.
For the network model:
To forecast demand and to stay ahead of the logistics lead times, we should create a customer avatar of each geographic specific representation of the average customer around a geographical network sink that includes a linear probabilistic optimization of products bought. This would give us an idea of projected demand near demand sink locations. We could incorporate online customer input by using their delivery addresses. To forecast demand at each node there could be three defining steps: 1) Define the decision variables. 2) Create the decision structure as a logistic regression or decision tree. 3) Optimize the solution with a regression model.
For each sink node create a probability variable of demand that will indicate probability # of products consumed. This dependent variable for each product would be binary (0 or 1) as to purchased or not. We could incorporate the outcome of the PCA result correlation found earlier. Then, use that lambda variable to affect the lambda in the cumulative distribution function 1 − 𝑒!"# , or probability density function 𝜆𝑒!"#, to find the time between outgoing products at the next upstream source node, then use that lambda pair next upstream source node, and so on, to build a demand model amongst the network nodes. Some nodes will have multiple inputs that affect the lambdas. The base of this chain is the predicted demand at the retail nodes (and online sales).
From a macro perspective, this problem is a neural network. From a more micro view the problem has similarities to a queuing problem or transportation problem. This is demand dependent where the sinks are dynamic and based on constantly updating consumption optimization models which can have a probabilistic demand at the base nodes. We optimize using linear regression / ARIMA of consumer data to inform CART decision tree that incorporates a logistic regression for after each decision split to order more or not (i.e. if stock for an item is below a certain number as a decision point, then run a regression to find the optimum order amount/s). If the regression of the optimum order amount meets a certain number, the sink lamba is adjusted to lower the sink threshold number that triggers the upstream source to fill that given void. All of this is dependent on the downstream numbers of consumer preferences which shape the regression optimization models at the lowest nodes, and would also incorporate online shopping preferences localized by shipping addresses.
An example of an objective demand function to optimize:
∑ Linear model demand variables + ∑ ARIMA variables + ∑ PCA correlated variables + ∑ probability density function
Here’s a graphic supply chain example with China as the #1 source node distributing to wholesalers on various continents who then distribute to retailers. Local to the SF Bay area, the shipment arrives in the Port of Oakland and distributes from there:
This is a general flow-balance equation for each sink and source node:
𝑃𝑟𝑜𝑑𝑢𝑐𝑡𝑠 𝑖𝑛𝑡𝑜 𝑠𝑖𝑛𝑘 𝑛𝑜𝑑𝑒
𝑃𝑟𝑜𝑑𝑢𝑐𝑡𝑠 𝑜𝑢𝑡 𝑜𝑓 ⎛ 𝑑𝑒𝑡𝑒𝑟𝑚𝑖𝑛𝑒𝑑 𝑏𝑦 ⎞ 𝑁𝑒𝑡 𝑠𝑢𝑝𝑝𝑙𝑦 @ 𝑠𝑜𝑢𝑟𝑐𝑒 𝑛𝑜𝑑𝑒 K − ⎜ 𝑟𝑒𝑔𝑟𝑒𝑠𝑠𝑖𝑜𝑛 𝑎𝑛𝑑 𝑝𝑟𝑜𝑏𝑎𝑏𝑖𝑙𝑖𝑡𝑦 ⎟ = @ 𝑎𝑡 𝑛𝑜𝑑𝑒 K
𝑜𝑝𝑡𝑖𝑚𝑖𝑧𝑎𝑡𝑖𝑜𝑛 𝑓𝑜𝑟 𝑐𝑜𝑛𝑠𝑢𝑚𝑝𝑡𝑖𝑜𝑛 ⎝ 𝑎𝑛𝑑 𝑝𝑟𝑜𝑗𝑒𝑐𝑡𝑒𝑑 𝑑𝑒𝑚𝑎𝑛𝑑 ⎠
𝐶𝑜𝑛𝑠𝑡𝑟𝑎𝑖𝑛𝑡𝑠: a 𝐴𝑐𝑡𝑢𝑎𝑙 𝑜𝑟 𝑃𝑟𝑜𝑗𝑒𝑐𝑡𝑒𝑑 𝑛𝑒𝑡 𝑠𝑢𝑝𝑝𝑙𝑦 ≤ 0: 𝐴𝑑𝑗𝑢𝑠𝑡 𝑠𝑜𝑢𝑟𝑐𝑒 𝑛𝑜𝑑𝑒 𝜆 𝑡𝑜 𝑖𝑛𝑐𝑟𝑒𝑎𝑠𝑒 𝑠𝑢𝑝𝑝𝑙𝑦 f 𝐴𝑐𝑡𝑢𝑎𝑙 𝑜𝑟 𝑃𝑟𝑜𝑗𝑒𝑐𝑡𝑒𝑑 𝑛𝑒𝑡 𝑠𝑢𝑝𝑝𝑙𝑦 > 0: 𝐴𝑑𝑗𝑢𝑠𝑡 𝑠𝑜𝑢𝑟𝑐𝑒 𝑛𝑜𝑑𝑒 𝜆 𝑡𝑜 𝑚𝑎𝑖𝑛𝑡𝑎𝑖𝑛 𝑐𝑢𝑟𝑟𝑒𝑛𝑡 𝑠𝑢𝑝𝑝𝑙𝑦
Here’s an example general network flow model of product to the SF Bay Area stores: Factory
       Retailers
   Distributors
   Warehouse
    17 ? variable units
18
3 300 Units
2 300 Units 1
SF HQ
           150 Units
                  150 Units
         2-way communications to sync optimizations
      2-way communications to sync optimizations
 
  Retailer level
   Distributor level
   Warehouse level
  Factory level
   SF HQ level
  PCA
  Regression / ARIMA
Regression / ARIMA
  Regression / ARIMA
 Incorporates all models for cross channel communication
  Regression / ARIMA for demand forecast
   CART
 CART
       Linear probability model
    Logistic regression
  Logistic regression
        ANOVA


![](https://github.com/contrevaloir/Portfolio/blob/main/images/LevisSupplyMap.png)

[](https://github.com/contrevaloir/Portfolio/blob/main/images/Screen%20Shot%202021-11-30%20at%205.46.55%20PM.png)

[](https://github.com/contrevaloir/Portfolio/blob/main/images/Screen%20Shot%202021-12-18%20at%2011.11.07%20PM.png)

[](https://github.com/contrevaloir/Portfolio/blob/main/images/Screen%20Shot%202021-12-18%20at%2011.11.33%20PM.png)
