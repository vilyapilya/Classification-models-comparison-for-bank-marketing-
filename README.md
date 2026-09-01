# Classification-models-comparison-for-bank-marketing-

[Link to the Notebook ](https://github.com/vilyapilya/Classification-models-comparison-for-bank-marketing-/blob/main/prompt_III.ipynb)

# Classification Models Comparison for Bank Marketing

## Project Overview
The goal of this project is to compare classification algorithms for identifying the customers who are more likely to subscribe to a term deposit. A successful predictive model can help the bank target marketing campaigns more effectively and reduce resources spent on unsuccessful customer contacts.


## Dataset

The dataset contains customer information, previous campaign results, contact information, and social and economic indicators.

The target variable is:

- `y = yes` — the customer subscribed to a term deposit
- `y = no` — the customer did not subscribe

The `duration` feature was excluded from modeling because call duration is only known after the call has already taken place and therefore would not be appropriate for a realistic predictive model.

## Data Preparation

Categorical variables were transformed using One-Hot Encoding, while numerical features were preserved and scaled where appropriate.

The data was divided into training and testing sets using a stratified split to preserve the distribution of the target variable. 

## Models

The following classification models were compared:

- Logistic Regression
- K-Nearest Neighbors (KNN)
- Decision Tree
- Support Vector Machine (SVM)

The models were first evaluated using their default parameters. Hyperparameter tuning was then performed using `GridSearchCV` with cross-validation. 

## Evaluation Metric

Because the target classes are imbalanced, accuracy alone can be misleading. F1 score was selected as the primary evaluation metric because it balances precision and recall and provides a better measure of the model's ability to identify customers who are likely to subscribe. 

## Results

The tuned Logistic Regression model provided the best overall balance between predictive performance, generalization, and training time. KNN showed signs of overfitting, while Logistic Regression, Decision Tree, and SVM demonstrated a better balance between training and testing performance. 

SVM had the longest training time among the best-performing models. 

## Key Findings

Logistic Regression was selected as the preferred model because it combines good predictive performance with interpretability.

Analysis of the Logistic Regression coefficients showed several important relationships:

- The 3-month Euribor rate was strongly associated with subscription behavior. Customers who subscribed tended to be contacted during periods with lower Euribor rates.
- Consumer Price Index was also associated with subscription probability.
- Employment Variation Rate was strongly associated with customers who did not subscribe.
- Higher numbers of employed people were associated with a lower probability of subscription.
- Failure in a previous marketing campaign was associated with a higher likelihood of rejecting the current offer.
- Telephone campaigns were also associated with the negative class.

These relationships represent associations identified by the model and should not necessarily be interpreted as causal effects.

## Business Recommendation

The bank could use the Logistic Regression model to prioritize customers who have a higher predicted probability of subscribing to a term deposit. This could help reduce unnecessary customer contacts and improve the efficiency of future marketing campaigns.

## Technologies Used

- Python
- pandas
- NumPy
- scikit-learn
- matplotlib
- seaborn
- Jupyter Notebook

