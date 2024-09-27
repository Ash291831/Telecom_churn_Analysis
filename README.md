Capstone Project: Telecom Churn

Business Problem Overview --
In the telecom industry, high customer churn (15-25% annually) poses significant challenges, especially as retaining existing customers is far more cost-effective than acquiring new ones. This project focuses on identifying and retaining high-value customers, particularly in the Indian and Southeast Asian markets where prepaid services are prevalent.

Understanding Churn
Churn Definition:

Postpaid: Clear churn identification when customers terminate services.
Prepaid: More complex, as customers may stop using services without notifying the operator, making it difficult to distinguish between churn and temporary inactivity.
Churn Types:

Revenue-Based Churn: Customers generating less than a specified revenue over a set period. Limitations include excluding users who receive calls without generating revenue.
Usage-Based Churn: Customers with no service usage (calls, internet, etc.) over a defined period. This method risks late intervention if not monitored closely.
High-Value Customers
In India and Southeast Asia, approximately 80% of revenue comes from the top 20% of customers. Therefore, reducing churn among these high-value customers is crucial for minimizing revenue loss. This project will define high-value customers based on specific metrics and focus on predicting churn within this segment.
Data preparation
The following data preparation steps are crucial for this problem:

 

1. Filter high-value customers

As mentioned above, you need to predict churn only for high-value customers. Define high-value customers as follows: Those who have recharged with an amount more than or equal to X, where X is the 70th percentile of the average recharge amount in the first two months (the good phase).

 

After filtering the high-value customers, you should get about 30k rows.

 

2. Tag churners and remove attributes of the churn phase

Now tag the churned customers (churn=1, else 0) based on the fourth month as follows: Those who have not made any calls (either incoming or outgoing) AND have not used mobile internet even once in the churn phase. The attributes you need to use to tag churners are:

total_ic_mou_9

total_og_mou_9

vol_2g_mb_9

vol_3g_mb_9


After tagging churners, remove all the attributes corresponding to the churn phase (all attributes having ‘ _9’, etc. in their names).


                                                 Modeling

Steps Taken:
Data Preprocessing: Ensured that the data was clean and prepared for modeling, including handling missing values and scaling numerical features.

Logistic Regression Model: This model was chosen to predict churn and to understand the influence of various features.

Feature Importance Analysis: After fitting the model, I examined the coefficients to identify significant predictors of churn. Visualizations, including plots and summary tables, were created to clearly convey the importance of these features.

Results
The logistic regression model revealed several key predictors of churn, which were visualized to illustrate their significance. This analysis highlighted factors such as service usage patterns, customer demographics, and payment behaviors as crucial indicators.
