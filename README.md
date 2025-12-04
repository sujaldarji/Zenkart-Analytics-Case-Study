# Zenkart Customer Analytics

This project performs end-to-end customer analytics for Zenkart, a fast-growing D2C brand.  
The analysis covers data cleaning, customer segmentation, churn prediction, and sales forecasting to help identify key business issues and recommend data-driven actions.

---

## 🔍 Project Overview

This study explores Zenkart’s sales, customer, and product data to answer:

- How do different types of customers behave?
- Which customers are at risk of churn?
- How can delivery performance and customer experience be improved?
- What will sales look like in the next 10–12 weeks?

The project applies standard machine learning workflows using Python and Colab.

---

## 🧹 Data Cleaning & Preparation

- Missing values in **Income** and **DeliveryTime** were imputed using median.
- **Rating** was treated as behavioral missingness → a new feature `HasRated` was created.
- Outliers in **Price**, **CLV**, and **DeliveryTime** were capped using the IQR rule.
- Daily transactions were aggregated into **weekly sales** for forecasting.

---

## 🛍️ Customer Segmentation (K-Means)

Customers were aggregated at the customer level and described using:

- Recency  
- Frequency  
- Monetary value  
- AvgDeliveryTime  
- CLV  
- Age, Income, CityTier  

K-Means (k = 4) revealed four meaningful segments:

1. **Mid-Tier Loyal Customers**  
2. **Dormant / At-Risk Customers**  
3. **Premium High-Value Customers**  
4. **Price-Sensitive Slow-Delivery Customers**

---

## 🔁 Churn Prediction

- Logistic Regression used as baseline classifier.
- Data was highly imbalanced → initial recall for churn was only 12%.
- Using `class_weight='balanced'`, churn recall improved to **76%**, making the model far more useful for retention planning.

---

## 📈 Time Series Forecasting

- Weekly sales were forecasted using **Simple Exponential Smoothing (SES)**.
- Accuracy improved significantly after cleaning:
  - **Before cleaning:** 34.7% MAPE  
  - **After cleaning:** **16.5% MAPE**  

Cleaned data produced a more stable 12-week forecast for planning and inventory decisions.

---

## 📝 Repository Structure

notebook/
    └── Zenkart_Code.ipynb
presentation/
    └── Zenkart_Presentation.pptx
report/
    └── Zenkart_Report.docx
visuals/
    ├── cluster_feature_comparison.png
    ├── Confusion_matrix_balanced.png
    ├── Confusion_matrix.png
    ├── Elbow_Method.png
    ├── forecast_cleaned.png
    ├── forecast_raw.png
    ├── Outliers_Free.png
    ├── Outliers.png
    └── weekly_sales_plot.png
README.md


---

## 📂 Visualizations

All graphs used in the analysis (boxplots, cluster comparisons, confusion matrix, forecast plots) are stored in the `/visuals` folder.

---

## 📌 Key Outcomes

- Customer behavior clearly segmented into 4 actionable groups.
- Significant improvement in churn detection.
- Forecasting accuracy doubled after data cleaning.
- Data-driven recommendations delivered across marketing, retention, delivery operations, and inventory planning.

---

## ✔ Summary

This project demonstrates a complete applied ML pipeline — data cleaning, feature engineering, unsupervised learning, supervised learning, and forecasting — to help Zenkart make better business decisions.

