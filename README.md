# Classification model (RandomForestClassifier)

## Target
### Churn: Whether the customer churned or not (Yes or No)

### Description about the features/columns
#### Two numerical columns:
1. **MonthlyCharges**: The amount charged to the customer monthly
2. **TotalCharges**: The total amount charged to the customer

#### Eighteen categorical columns:
##### Feature name : Description
1. CustomerID : Customer ID unique for each customer
2. gender : Whether the customer is a male or a female
3. SeniorCitizen: Whether the customer is a senior citizen or not (1, 0)
4. Partner: Whether the customer has a partner or not (Yes, No)
5. Dependents: Whether the customer has dependents or not (Yes, No)
6. Tenure: Number of months the customer has stayed with the company
7. PhoneService: Whether the customer has a phone service or not (Yes, No)
8. MultipleLines: Whether the customer has multiple lines or not (Yes, No, No phone service)
9. InternetService: Customer’s internet service provider (DSL, Fiber optic, No)
10. OnlineSecurity: Whether the customer has online security or not (Yes, No, No internet service)
11. OnlineBackup: Whether the customer has an online backup or not (Yes, No, No internet service)
12. DeviceProtection: Whether the customer has device protection or not (Yes, No, No internet service)
13. TechSupport: Whether the customer has tech support or not (Yes, No, No internet service)
14. StreamingTV: Whether the customer has streaming TV or not (Yes, No, No internet service)
15. StreamingMovies: Whether the customer has streaming movies or not (Yes, No, No internet service)
16. Contract: The contract term of the customer (Month-to-month, One year, Two years)
17. PaperlessBilling: Whether the customer has paperless billing or not (Yes, No)
18. PaymentMethod: The customer’s payment method (Electronic check, Mailed check, Bank transfer (automatic), Credit card (automatic))



## Phase 1 (Explorotary Data Analysis)
### Getting to know the dataset better
1) Shape
2) Null Values summary
3) Column datatypes
aswell as a small amount of cleaning and preprocessing

### Why did customers churn(main question)?
FILE_TAG: (EDA_1)
This is where we try to visualize the features, and how they are related with our target.
we also try to draw patters/trends from these features, aswell as concluding some basic theory on our main question 
Aswell as providing possible solution to what we conclude is part of the problem

FILE_TAG: (EDA_2)
Here we take several groups of people
1. People who left and stayed in first 6 months
2. Loyal Customers
We mainly apply the same metrics we applied in EDA_1 file, where we also compare different features with out target

## Phase 2 (Training the model)
FILE_TAG: (Final_Train_Model)
1) Feature extraction (Recursive Feature Elimination (RFE) and SelectKBest)
2) Sampling Techniques (SMOTE/RandomOverSampler)
3) Data Splitting and training
4) Model Evaluation (confusion_matrix, ROC_AUC_Curve)

### Phase 2 Confusion matrix
Our evaluation was **Recall** based (Lower **False Negative**)

[What is a confusion matrix?] : https://medium.com/analytics-vidhya/what-is-a-confusion-matrix-d1c0f8feda5

Recall = out of the total actually who churned , how many did the model actually manage to predict correctly

Precision = out of the total which the **model** predicted will leave , how many actually churned

If recall increases , precision decreases, and vice versa

### Why focus on lowering **False negatives** ?
In our situation, we decided that lowering false negative values is more important than lowering false positive


Positive prediction (0) =  no churn

Negative prediction (1) = churn

**False Negative** = predicted positve , while actual value was negative.

In simpler terms , a positive prediction means that the model  predicited that a certain customer did not churn, but he actually did.

this is bad in a business situation.

**False Positive** = predicted negative , while actualy value was positive

In simpler terms , a negative prediction means that the model  predicited that a certain customer  churned, but he actually did not

this is digestable  in a business situation and not as bad as the situation above

A higher recall mean lower false negatives. Recall was our main evaluation metric , while also taking into consideration a considerable
f1 score(harmonic mean of precision and recall).

#### Threshold optimization (OPTIONAL)
You can even increase recall more by applying a high threshold to the predicted probabilities.
This inturn will increase recall significantly , but a decreases precision aswell.
Overall lower f1-score , but high precision


## Phase 3 (Model Deployment) 
** Under Construction **

