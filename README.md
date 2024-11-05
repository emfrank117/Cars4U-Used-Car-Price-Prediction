# **Used Cars Price Prediction**

-------------------
## **Context:**
-------------------

There is a huge demand for used cars in the Indian Market today. As sales of new cars have slowed down in the recent past, the pre-owned car market has continued to grow over the past few years and is now larger than the new car market. Cars4U is a budding tech start-up that aims to find footholes in this market.

In 2018-19, while new car sales were recorded at 3.6 million units, around 4 million second-hand cars were bought and sold. There is a slowdown in new car sales and that could mean that the demand is shifting towards the pre-owned market. In fact, some car owners replace their old vehicles with pre-owned cars instead of buying a new automobile.

Unlike new cars, where price and supply are fairly deterministic and managed by OEMs (Original Equipment Manufacturer / except for dealership level discounts which come into play only in the last stage of the customer journey), the used car market is a very different beast, with large uncertainties in both pricing and supply. Several factors, including mileage, brand, model, year, etc. can influence the actual worth of a car. From the perspective of a seller, it is not an easy task to set the correct price of a used car. Keeping this in mind, the pricing scheme of these used cars becomes important in order to grow in the market.

--------------------
## **Objective:**
--------------------

Come up with a pricing model that can effectively predict the price of used cars and can help the business in devising profitable strategies using differential pricing.

--------------------
## **Conclusions and Recommendations**
--------------------

**1. Comparison of various techniques and their relative performance based on chosen Metric (Measure of success):**
- How do different techniques perform? Which one is performing relatively better? Is there scope to improve the performance further?
  * Answer: Overall model performance across the board is realtively strong, minimal models yielded results that were below acceptable standards. While there was a consistenct lack of large scale improvement beyond the Least Squares model among the other Regularized Regression methods, the Tree Based models did show a higher performance and therefore produced the best model, Gradient Boosting Tuned.
  * While the performance is high, the best reccomendation to increase model performance is, as always, if possible increase dataset size. There were low respresenation in more niche Brands and Fuel_Types which were hard to generalize.  
  * Reducing the model complexity could be a direction to consider to address the overfitting, perhaps pooling vehicle Brands into more generalized groups.
  * And of course being more agressive with removing outliers would have assisted performance, especially the MAPE scores. With increased dataset size, removing these extreme values could be warrented.
 
**2. Refined insights:**
- What are the most meaningful insights relevant to the problem?
  * Answer:  The most meaningful insights were the relationships the data has within variables, and the value of the features determined by the models. Overwhelmingly the key component for pricing is the Power of the vehicle, the age of the vehicle, and the transmission type will increase the ability to predict the price of the vehicle.
  * The determination of which Locations are the highest and lowest of specific variables leads to actionable insights for the buying and selling of used cars for profit. Of the locations the Kolkata location would be the most ideal for purchasing vehicles at a lower price and Coimbatore for selling the vehicles.
  * The generalized statments that can be made about vehicle attributes and their relevance.
      * Higher power vehicles with lower age yield the highest price.
      * Diesel powered vehicles, which are more prevelant, have a higher power and are more expensive.
      * Manual transmissions lowers the price of the vehicle.
      * Lower mileage reported does not contribute to higher prices.
      * Increased Kilometers_Driven reduces the price.

**3. Proposal for the final solution design:**
- What model do you propose to be adopted? Why is this the best solution to adopt?
  * Answer: The model with the best overall performance across the metrics was the Tree Based, specifically the Gradient Boosting Tuned Regressor. The sequential addition of weak learners to the model while updating the weights from the residual errors of the Adaboost significantly increased the Rsquare value and removed a substantial amount of overfitting. And while MAPE values would have been more ideal lower, Gradient Boosting did not compromise MAPE while increasing the performance in other areas. XGBoost Regressor and Random Forest Tuned also had promising performance, and while the MAPE values were lower than others, the overfitting increased.  Therefore the Gradient Boosting had a solid performance across the metrics without compromising other areas and then after hyperparameter tuning the model performance exceeded all other tree based, making it the best model across the board.
  * I believe the use of this model would be useful to the Cars4U agency.  And the implementation of it's use can be benefical on two sides.  Determining if a vehicle is priced appropriately to buy and the price at which to sell. For maximum profit, this model could be used to determine which vehicles are priced below assumed value, and then with the employment of differential pricing a percentage higher at the resale.

### **Recommendations**

The buying and selling of used cars is complicated market that is highly affected by inventory and locality.  Dynamic and differential pricing is required to create profit stability.  There are a wide array of factors that are incorporated in creating a used car price, a crucial aspect for a profitable resale.  Creating a model to predict sales price is highly useful for both ends.  Determining if a vehicle is priced low enough to purchase for resale, and priced high enough for market trends that will result in a profit is the entire buisness model for success.  

The ability to buy low and sell high is not soley based on price, but it's also based on demand.  The bulk of inventory should be marketable cars for consistent proftits that allows for further investments made in either higher risk reward inventroy or simply increased variety of inventory.

While market trends evolve quickly, the continued collection of data such as this is absolutely cruicial in the used car industry.  While attending an auction, quick decison are required for the greatest gain.  Having extensive knowledge of the key features that dictate pricing is paramount to making concise decisions about buying used vehicles.  

Locality plays are large role in the inventory available.  Affluent and low income areas have different trends as do cities versus rural areas.  Tracking geographical location nuiances allows a company to tap into inventory that other areas value higher increasing profits.  Buying low and selling high does not have to indicate overpricing, it's the knowledge of local market trends that creates differential pricing systems for maximum profitability.

Simple exploratory data analysis shows that Kolkata has the lowest average priced vehicles with the lowest age and kilometers driven.  This is confirmed by the above average vehicle counts and the low sum of total price.  Vehicles in this location appear to be newer with lower mileage (kilometers driven) and priced lower than other areas like Coimbatore, where the average price for their newer, low mileage (kilometers driven) vehicles is 2.5 times that of Kolkata.

All models also indicated the importance of a vehicles engine power.  Higher power yields higher prices.  And this plays a role in other attributes of the vehicles, diesel vehicles are higher power, and it even shows in that vehicles with lower mileage (mileage reported) yield a higher price.  The cascading effect of understanding the feature relevance is the domain knowledge that is required for effecitive decision making.

Creating a system where pricing reflects the value of the vehicle based on the standards of used vehicle sales has the potential to increase profit stability in a fluctuating industry.  This benfits the buyer, the seller, and the overall used vehicle market.  With ever increasing amounts of sales records and a solid model like the one created from this dataset the prediciton of used vehicle prices can feel less unpredictable and create the foundation of a successful used vehicle company.
