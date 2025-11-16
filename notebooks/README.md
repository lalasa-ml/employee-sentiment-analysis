
Employee Sentiment Analysis - Summary
------------------------------------
Total messages processed: 2191
Unique employees: 10

Top 3 Positive / Negative employees per month: see outputs/top_employees_by_month.xlsx
Employees flagged as flight risk (first window if any): see outputs/flight_risks.xlsx

Modeling:
- Sentiment labeling: TF-IDF + Logistic Regression trained on NLTK movie_reviews + twitter_samples.
- Predictive model: Linear Regression trained to predict monthly sentiment scores from engineered features.

All outputs:
- data/processed/labeled_messages.xlsx
- outputs/monthly_features_and_scores.xlsx
- outputs/top_employees_by_month.xlsx
- outputs/flight_risks.xlsx
- visualizations/*.png
- models/*.joblib

To reproduce:
1. Install packages from requirements.txt
2. Open notebooks/main.ipynb and run all cells in order.
