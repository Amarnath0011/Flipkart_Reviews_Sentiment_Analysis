# Flipkart Reviews Sentiment Analysis

An end-to-end **NLP and Machine Learning** project that classifies Flipkart product reviews into **positive, neutral, and negative** sentiment categories.

## Problem Statement

Customer reviews contain valuable information about product quality and customer satisfaction, but manually analyzing large volumes of reviews is time-consuming. This project uses NLP and machine learning to automatically classify review sentiment and generate customer-feedback insights.

## Dataset

The dataset contains **2,304 raw Flipkart reviews** with:

- `Product_name` — product name/details
- `Review` — customer review text
- `Rating` — customer rating from 1 to 5

After removing duplicate records, the analysis contains **2,181 unique reviews**.

### Sentiment Mapping

| Rating | Sentiment |
|---|---|
| 1–2 | Negative |
| 3 | Neutral |
| 4–5 | Positive |

## Tech Stack

- **Python**
- **Pandas / NumPy** — data processing
- **Matplotlib / Seaborn** — visualization
- **NLTK / spaCy** — NLP preprocessing
- **Scikit-learn** — machine learning and evaluation
- **XGBoost** — gradient boosting classifier
- **imbalanced-learn (SMOTE)** — class balancing
- **VADER** — rule-based sentiment scoring
- **Jupyter Notebook**

## Approach

```text
Raw Reviews
    ↓
Data Cleaning
    ↓
Rating → Sentiment
    ↓
Text Cleaning + Tokenization/Lemmatization
    ↓
TF-IDF Feature Extraction
    ↓
Train/Test Split
    ↓
Baseline Model Comparison
    ↓
SMOTE for Class Balancing
    ↓
Model Training
    ↓
Evaluation
    ↓
Business Insights
```

## Models Evaluated

- Logistic Regression
- Decision Tree
- Random Forest
- Multinomial Naive Bayes
- XGBoost

Models were evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC
- Classification Report
- Confusion Matrix

## Results

The original project evaluation reported the following XGBoost results after balancing the training data with SMOTE:

| Metric | XGBoost |
|---|---:|
| Test Accuracy | **92.67%** |
| Weighted F1-score | **93.14%** |
| ROC-AUC | **96.14%** |

> These metrics correspond to the original analysis notebook. Re-running the notebook with different library versions or preprocessing settings may produce slightly different values.

## Business Impact

The analysis can help product and customer-experience teams:

- reduce manual effort in classifying reviews,
- identify recurring negative feedback,
- monitor customer satisfaction trends,
- flag potentially poor-quality or defective products,
- prioritize reviews requiring attention,
- support data-driven product improvements.

## How to Run

### 1. Clone the repository

```bash
git clone <YOUR_REPOSITORY_URL>
cd Flipkart_Reviews_Sentiment_Analysis
```

### 2. Create a virtual environment

```bash
python -m venv .venv
source .venv/bin/activate
```

On Windows:

```powershell
.venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
python -m spacy download en_core_web_sm
```

### 4. Launch Jupyter

```bash
jupyter notebook
```

Open:

```text
Flipkart_Reviews_Sentiment_Analysis.ipynb
```

and run the notebook from top to bottom.

## Project Structure

```text
Flipkart_Reviews_Sentiment_Analysis/
├── Flipkart_Reviews_Sentiment_Analysis.ipynb
├── flipkart.csv
├── requirements.txt
├── .gitignore
└── README.md
```

## Future Improvements

- Hyperparameter tuning with GridSearchCV/RandomizedSearchCV
- Compare TF-IDF with word embeddings
- Add transformer-based sentiment models
- Build a Streamlit dashboard
- Add product-level sentiment aggregation
- Deploy the trained model as a REST API
