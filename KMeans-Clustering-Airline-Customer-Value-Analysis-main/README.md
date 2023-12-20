# KMeans-Clustering-Airline-Customer-Value-Analysis
This repository is related to clustering airline customer analysis using the Kmeans Clustering method to create customer segmentation using the LRFMC model.

Programming Tools : Python in Jupyter Notebook

Dataset : Airline Customer (flight.csv)

## The dataset consists of several features, such as:

1. MEMBER_NO : ID Member
2. FFP_DATE : Frequent Flyer Program Join Date
3. FIRST_FLIGHT_DATE : Data of First Flight
4. GENDER : Gender of customer
5. FFP_TIER : Tier of frequent flyer program
6. WORK_CITY : City of Origin
7. WORK_PROVINCE : Province of Origin
8. WORK_COUNTRY  : Country of Origin
9. AGE : Age of Customer
10. LOAD_TIME : Date the data was collected
11. FLIGHT_COUNT : Number of customer flights
12. BP_SUM : Itinerary
13. SUM_YR_1 : Total credits/points in the first year
14. SUM_YR_2 : Total credits/points in the second year
15. SEG_KM_SUM : Total distance (km) of flights already taken
16. LAST_FLIGHT_DATE : Last flight date
17. LAST_TO_END  : Time distance of the last flight to the most recent flight order
18. AVG_INTERVAL : Average distance time
19. MAX_INTERVAL : Maximum distance time
20. EXCHANGE_COUNT : Number of exchanges
21. avg_discount : Average discount that customers get
22. Points_Sum : Number of points earned by the customers
23. Point_NotFlight : Points that are not used by customers

Modelling Method : Kmeans Clustering using LRFMC Model

## LRFMC Model

RFM is a model that is widely used in segmentation. This RFM model consists of Recency, Frequency and Monetary. Here for feature selection using the LRFMC model, is a development of the RFM model. Based on research from papers made by Saixin Wu (2022) and Yang Tao (2020) that LRFMC in this case are: 

1. **L** (Length): The length of time of customer membership from the first time registering until the observation period (the longer the customer becomes a member means the customer is "loyal" or the better).

2. **R** (Recency): The length of time between the customer's last flight until the observation period (the smaller means the customer has just taken a flight, therefore the smaller the better).

3. **F** (Frequency): The number of customer flights in the observation period (the bigger the better which means the customer often makes flights).

4. **M** (Monetary): Accumulated flight mileage during the observation period (the bigger the better, which means that the long distance means the flight fare is bigger, so the customer spends more money).

5. **C** (Discount Coefficient) : The average value of the discount factor used during the observation period (the smaller the better, which means that the less customers use discounts on their flights).

Therefore, in the case that this analysis will be carried out, it uses features including: 

- L : `LOAD_TIME` - `FFP_DATE` 

(The amount of time the customer has been a member = Last time observed - First date the customer registered) in the form of months

- R : `LAST_TO_END`
- F : `FLIGHT_COUNT`
- M : `SEG_KM_SUM`
- C : `avg_discount`

## Here are the results

It can be seen that each cluster is formed due to differences in the **LRFMC** model indicators. Based on the analysis and visualization above, it can be concluded that: 

- **Cluster 0 - (The Champions)**: 

Customers who have been members for a medium period of time and often make flights with long flight distances are seen in the low Recency, Frequency and high Monetary indicators.

- **Cluster 1 - (Recent Users - Potential Loyalists)** : 

Customers who have just become members and have just taken a flight with a fairly long flight distance can be seen in the low Recency, Frequency and Monetary indicators which are quite high.

- **Cluster 2 - (Need Attention)** : 

Customers who have not been members for a long time and rarely make flights and usually make flights with fast / close mileage as seen from the high Recency, Frequency, Monetary and low Discount (C).
- **Cluster 3 - (Hibernating)** : 

Customers who have been members for a medium period of time and rarely fly. Although they do fly but within a fast / close distance and make flights when there are discount vouchers. Seen in Recency, Discount (C) is high while Frequency and Monetary are the lowest.

- **Cluster 4 - (Loyal Customers)** :

Customers who have been members for a long time and make flights in the medium term with a fairly fast / close distance. It can be seen that Length is very high while Frequency, Monetary is quite low.

## Business Recommendation

- **Cluster 0 - (The Champions) and Cluster 4 - (Loyal Customers)** : 
    - Provide a "Thank You" every time a customer uses the airline and provide a "Customer Greeting" and provide a voucher/discount for the next flight.
    - Provide points/rewards for every airline booking that can be redeemed with discount vouchers or products affiliated with the airline.
    - Provide Merchandise and special services to customers for being loyal customers.
- **Cluster 1 - (Recent Users - Potential Loyalist)** : 
    - Build and maintain good relationships with customers
    - Provide discounts by inviting friends to use the airline
    - Provide a discount for the next flight
    - Provide points/rewards for each airline booking that can be redeemed with discount vouchers or affiliated products with the airline.
- **Cluster 2 - (Need Attention)** : 
    - Provide campaign flyers or information related to flight promos
    - Provide newsletters to customers regarding discounts and flight programs with the hope that customers will use the airline again.
- **Cluster 3 - (Hibernating)** : 
    - Provide campaign flyers or information related to flight promos
    - Provide special flight promos/programs with a specified time limit
