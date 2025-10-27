# churn-insights-telecom

##  Project Analysis – Telecom Churn Prediction

###  Objective

The goal of this project is to analyze telecom customer data to identify factors that influence customer churn (leaving the service) and to build predictive models that can forecast churn probability with high accuracy.

---

###  Dataset Overview

* **Source:** [Kaggle – Telco Customer Churn](https://www.kaggle.com/blastchar/telco-customer-churn)
* **Records:** ~7,000 customer entries
* **Features:** Customer demographics, account details, services subscribed, billing information, and churn status.

---

###  Data Cleaning & Preparation

* Converted `TotalCharges` to numeric and filled missing values with median.
* Encoded categorical variables using Label Encoding.
* Standardized numerical columns for consistent model performance.
* Removed duplicates and null values for data integrity.

---

###  Exploratory Data Analysis (EDA)

####  Churn Rate

* Around **26–30%** of customers have churned.
* Indicates a moderate customer retention challenge.

####  Key Insights from EDA

| Factor               | Observation                                             | Inference                                             |
| -------------------- | ------------------------------------------------------- | ----------------------------------------------------- |
| **Contract Type**    | Month-to-Month customers show the highest churn rates.  | Long-term contracts improve retention.                |
| **Tenure**           | Customers with <12 months tenure churn more frequently. | Early engagement is key to reducing churn.            |
| **Monthly Charges**  | Higher monthly charges correlate with higher churn.     | Cost-sensitive customers may leave for cheaper plans. |
| **Internet Service** | Fiber optic users have higher churn than DSL users.     | Review service quality and pricing.                   |
| **Senior Citizens**  | Slightly higher churn tendency.                         | May need tailored plans or better support.            |

####  Visual Insights

* **Heatmap:** Shows correlation between numeric features and churn.
* **Countplots:** Contract type, Internet service, and Payment method vs. churn.
* **Distribution Plots:** Monthly charges grouped by churn status.

---

###  Model Building & Evaluation

Trained multiple classification models to predict churn:

| Model               | Accuracy    | Key Notes                                              |
| ------------------- | ----------- | ------------------------------------------------------ |
| Logistic Regression | ~80%        | Strong baseline, interpretable results.                |
| Random Forest       | ~85%        | Better performance, handles feature variety well.      |
| Gradient Boosting   | ~86%        | Effective and consistent.                              |
| XGBoost             | **~88–90%** | Best performance, strong recall for churned customers. |

**Best Model:** `XGBoost` – Chosen for its high accuracy and balanced precision/recall.

**Top Predictive Features:**
`Contract`, `Tenure`, `MonthlyCharges`, `InternetService`, `OnlineSecurity`

---

### Business Insights & Recommendations

1. **Promote Annual Contracts:** Offer discounts for long-term commitments.
2. **Loyalty Programs:** Reward customers who stay longer (e.g., after 12 months).
3. **Optimize High-Charge Plans:** Provide lower-cost alternatives or custom bundles.
4. **Improve Fiber Optic Experience:** Investigate quality issues or customer complaints.
5. **Target At-Risk Customers:** Use churn predictions to send retention offers proactively.

---

### Conclusion

This project successfully identified the key drivers of customer churn and built predictive models achieving up to **90% accuracy**.
The analysis provides actionable insights that can help telecom companies improve **customer retention, satisfaction, and revenue stability**.
