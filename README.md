# 📰 News Headline Classification
 
Classify news headlines into predefined subject categories using Machine Learning.  
This project uses **TF-IDF** for feature extraction and **Logistic Regression** for classification, with a complete pipeline from text preprocessing to prediction submission.
 
---
 
## 📌 Table of Contents
- [Overview](#overview)
- [Dataset](#dataset)
- [Approach](#approach)
- [Installation](#installation)
- [Usage](#usage)
- [Results](#results)
- [Future Improvements](#future-improvements)
 
---
 
## 📖 Overview
This project aims to predict the **subject category** of a news headline based on its text.  
It uses a simple yet effective ML pipeline that can be extended to more advanced models like **BERT** or **RoBERTa**.
 
---
 
## 📂 Dataset
- **train.csv** → Contains headlines and their corresponding subject labels.
- **test.csv** → Contains headlines without labels (for prediction).
- **sample_submission.csv** → Example of the expected submission format.

### **Columns in the dataset**
- **ID** → Unique identifier for each sentence.  
- **Text** → The sentence from the essay.  
- **Subject** → The subject category (target label).
 
 
**Example row from `train.csv`:**
| id  | text                          | label   |
|-----|--------------------------------|---------|
| 1   | US stocks rise as inflation... | business|
 
---
 
## ⚙️ Approach
1. **Text Preprocessing**
   - Lowercasing
   - Removing punctuation & special characters
   - Tokenization
 
2. **Feature Extraction**
   - TF-IDF vectorization of headlines
 
3. **Model Training**
   - Logistic Regression with hyperparameter tuning
   - Tried different algorithms:  
     - Logistic Regression  
     - Multinomial Naive Bayes  
     - Random Forest  
     - Support Vector Machines  
   - Selected the best-performing model based on cross-validation.
 
4. **Evaluation**
   - Macro F1-score on validation set
   - **Evaluation Metric:**  
`Score = 100 × f1_score(actual, predicted, average='macro')`
 
5. **Prediction**
   - Generate predictions for `test.csv`
   - Save results in submission format
 
---
 
## Results

| Model  | Macro F1 Score   |
|-----|--------------------------------|
| Logistic Regression   | 0.87 |
| TF-IDF + Naive Bayes   | 0.85 |

---

## 🔮 Future Improvements
 
1. Implement transformer-based models (BERT, RoBERTa)
 
2. Use word embeddings (Word2Vec, GloVe, FastText)
 
3. Experiment with ensemble methods
 
4. Perform more advanced preprocessing (stopword removal, lemmatization

---
 
## 💻 Installation
Clone the repository and install dependencies:
 
```bash
git clone https://github.com/yourusername/news-headline-classification.git
cd news-headline-classification
pip install -r requirements.txt
