# Employee Sentiment Analysis

## Project Overview
This project analyzes an unlabeled dataset of employee email communications to assess employee sentiment and engagement. Using Natural Language Processing (NLP), Exploratory Data Analysis (EDA), and predictive modeling, the project derives actionable insights such as employee sentiment trends, rankings, and potential flight risks.

The analysis is performed entirely in Python using a Jupyter Notebook, following reproducible and well-documented steps.

---

## Dataset Description
The dataset consists of employee email data with the following columns:

- **subject**: Subject line of the email
- **body**: Main content of the email
- **date**: Date the email was sent
- **from**: Sender's email address (used as employee identifier)

The dataset is unlabeled, and sentiment labels are generated programmatically.

---

## Methodology

### 1. Sentiment Labeling
- Sentiment is derived using **TextBlob polarity scores**.
- The email **subject and body are combined** to capture full contextual meaning.
- Sentiment categories are defined as:
  - **Positive**: Polarity > 0.1
  - **Negative**: Polarity < -0.1
  - **Neutral**: Otherwise

Each email is augmented with a sentiment label and a numerical sentiment score:
- Positive: +1
- Negative: -1
- Neutral: 0

---

### 2. Exploratory Data Analysis (EDA)
EDA was conducted to understand sentiment distribution and trends:
- Overall sentiment distribution across all messages
- Monthly sentiment trends over time
- Identification of patterns in employee communication behavior

Visualizations are stored in the 'visualizations' folder.

---

### 3. Monthly Employee Sentiment Scoring
- Sentiment scores are aggregated **monthly for each employee**.
- Scores reset at the beginning of each new month.
- This provides a normalized view of employee sentiment over time.

---

### 4. Employee Ranking
For each month:
- **Top Three Positive Employees** are identified based on highest sentiment scores.
- **Top Three Negative Employees** are identified based on lowest sentiment scores.
- Ties are resolved alphabetically by employee email ID.

---

### 5. Flight Risk Identification
An employee is classified as a **flight risk** if:
- They send **4 or more negative emails within any rolling 30-day window**.

This rolling window approach ensures detection of sustained negative behavior regardless of calendar month boundaries.

---

### 6. Predictive Modeling
A **Linear Regression model** is developed using 'scikit-learn' to analyze sentiment trends.

#### Features used:
- Average message length per month
- Average word count per month

#### Target:
- Monthly sentiment score

#### Evaluation Metrics:
- R² Score
- Mean Squared Error (MSE)

The model provides insight into how communication patterns influence sentiment.

---

## Key Results Summary

### Top Positive & Negative Employees
- Monthly rankings identify consistently positive and negative communicators.
- These insights can inform recognition and engagement strategies.

### Flight Risk Employees
- A small subset of employees are flagged as flight risks based on sustained negative communication.
- Early identification enables proactive intervention.

### Model Insights
- Message length and word count show measurable correlation with sentiment trends.
- The regression model demonstrates reasonable explanatory power given the unlabeled nature of the data.



---

## Setup Instructions

1. Clone the repository
2. Install dependencies:
   pip install -r requirements.txt



