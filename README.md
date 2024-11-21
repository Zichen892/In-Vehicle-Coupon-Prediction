# In-Vehicle-Coupon-Prediction

In the rapidly evolving world of automotive technology, personalized marketing strategies are becoming increasingly important. One such strategy involves offering in-vehicle coupons to enhance the customer experience and drive sales. However, accurately predicting which passengers or drivers are likely to redeem these coupons can be challenging due to the complex, dynamic nature of user behavior, vehicle conditions, and external factors such as time and location. This project aims to develop a predictive model that identifies the likelihood of in-vehicle coupon redemption based on historical data, user profiles, and contextual information. By leveraging machine learning techniques, the project explores how factors like trip details, demographics, and in-vehicle environment influence a customer's response to coupon offers.

### Goal
The goal of this project is to create an effective model that predicts in-vehicle coupon redemption, enabling businesses to:

Offer highly targeted coupons based on customer preferences and trip data, increasing conversion rates.
Optimize the timing and placement of in-vehicle promotions to maximize effectiveness.
Gain insights into key drivers of coupon engagement, providing data-driven recommendations for future marketing campaigns.
Would you like to focus on specific data sources, algorithms, or additional project details? Let me know if you'd like to refine any section.

#### Data 
in-vehicle coupon recommendation. (2020). UCI Machine Learning Repository. https://doi.org/10.24432/C5GS4P.

1. destination: No Urgent Place, Home, Work
2. passenger: Alone, Friend(s), Kid(s), Partner (who are the passengers in the car)
3. weather: Sunny, Rainy, Snowy
4. temperature:55, 80, 30
5. time: 2PM, 10AM, 6PM, 7AM, 10PM
6. coupon: Restaurant(<$20), Coffee House, Carry out & Take away, Bar, Restaurant(`$20 - $50`)

7. expiration: 1d, 2h (the coupon expires in 1 day or in 2 hours)
8. gender: Female, Male
9. age: 21, 46, 26, 31, 41, 50plus, 36, below21
10. maritalStatus: Unmarried partner, Single, Married partner, Divorced, Widowed
11. has_Children:1, 0
12. education: Some college - no degree, Bachelors degree, Associates degree, High School Graduate, Graduate degree (Masters or Doctorate), Some High School
13. occupation: Unemployed, Architecture & Engineering, Student,
Education&Training&Library, Healthcare Support,
Healthcare Practitioners & Technical, Sales & Related, Management,
Arts Design Entertainment Sports & Media, Computer & Mathematical,
Life Physical Social Science, Personal Care & Service,
Community & Social Services, Office & Administrative Support,
Construction & Extraction, Legal, Retired,
Installation Maintenance & Repair, Transportation & Material Moving,
Business & Financial, Protective Service,
Food Preparation & Serving Related, Production Occupations,
Building & Grounds Cleaning & Maintenance, Farming Fishing & Forestry
14. income: 37500 - 49999, 62500 - 74999, 12500 - 24999, 75000 - 87499,
50000 - 62499, 25000 - 37499, 100000 or More, 87500 - 99999, Less than 12500
15. Bar: never, less1, 1-3, gt8,  nan4-8 (feature meaning: how many times do you go to a bar every month?)
16. CoffeeHouse: never, less1, 4-8, 1-3, gt8,  nan (feature meaning: how many times do you go to a coffeehouse every month?)
17. CarryAway:n4-8, 1-3, gt8, less1, never (feature meaning: how many times do you get take-away food every month?)
18. RestaurantLessThan20: 4-8, 1-3, less1, gt8,  never (feature meaning: how many times do you go to a restaurant with an average expense per person of less than $20 every month?)
19. Restaurant20To50: 1-3, less1, never, gt8, 4-8, nan
(feature meaning: how many times do you go to a restaurant with average expense per person of `'$20 - $50`' every month?)
20. toCoupon_GEQ15min:0,1 (feature meaning: driving distance to the restaurant/bar for using the coupon is greater than 15 minutes)
21. toCoupon_GEQ25min:0, 1 (feature meaning: driving distance to the restaurant/bar for using the coupon is greater than 25 minutes)
22. direction_same:0, 1 (feature meaning: whether the restaurant/bar is in the same direction as your current destination)
23. direction_opp:1, 0 (feature meaning: whether the restaurant/bar is in the same direction as your current destination)
24. Y:1, 0 (whether the coupon is accepted)

## Results

- **Best Performace Model**: Random Forest (average AUC 0.8)
- **Best data structure**: One-hot Encoded data (111 features)
- **High Precision**: Random Forest with one-hot encoded and SVM with one-hot encoded data 
- **Time complexity**: SVM with cross validation, Neural Network
 

- **Recomendations**: Based on current condistions and reserach, our team will recomend **RandomForest** model with one-hot encoded data based on its AUC(0.83) and Recall(0.84)

- **Limitations**: The dataset for this project is complex with 21 features, but only 10,000 instances, and this will not fit for some models that requires more data for training, like neural nwtwork. Other limitations is that the survey data with 10, 000 instances cannot represent a city, so the model's AUC score doesn't mean the model is generalized or ready for market implementation. One-hot encoded data structure has better performace for all models, meaning with more deatailed fatures, the prediction would be more accurate. On the other hand, with wide range of data, the computation cost will increase tremendously if we have a large dataset in the future. Also, it could need to overfitting sometimes.  
