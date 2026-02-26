# 🎬 Sentiment Analysis on IMDb Movie Reviews using NLP

## 📌 Overview

This project performs **sentiment analysis** on the IMDb Movie Reviews dataset to classify reviews as **positive** or **negative** using Natural Language Processing (NLP) techniques. The project demonstrates end-to-end NLP workflow including preprocessing, feature engineering, model building, evaluation, and business insights.

---

## 🗂️ Dataset

- **Source:** IMDb Movie Reviews Dataset (`IMDB_Dataset.csv`)
- **Size:** 50,000 reviews
- **Classes:** Positive / Negative (balanced — 25,000 each)

- Columns:
  - review → Text review
  - sentiment → Target label (positive/negative)

---

## 🔄 Project Workflow

### 1. Data Understanding
- Loaded and explored the dataset
- Checked shape, data types, missing values, and class distribution
- Visualized sentiment distribution using a bar chart

### 2. Data Cleaning & Preprocessing
The following steps were applied to clean and normalize the raw text:
- Converted text to **lowercase**
- Removed **HTML tags** (using regex)
- Removed **punctuation**
- Removed **stopwords** (using NLTK)
- Applied **Lemmatization** to reduce words to their root form

### 3. Feature Engineering — TF-IDF
- Used **TF-IDF Vectorizer** with `max_features=5000` to convert text into numerical features
- TF-IDF was preferred over CountVectorizer because it down-weights common words and highlights meaningful sentiment-bearing words like *excellent*, *terrible*, *amazing*
- Output matrix shape: **(50,000 × 5,000)**

### 4. Label Encoding
- Encoded `positive` → `1`, `negative` → `0` using `LabelEncoder`

### 5. Train-Test Split
- Split: **80% training / 20% testing** (`random_state=42`)

### 6. Model Training & Evaluation

| Model | Accuracy |
|---|---|
| Logistic Regression | **88.67%** |
| Naive Bayes (MultinomialNB) | 85.20% |

- **Logistic Regression** outperformed Naive Bayes and is the recommended model
- Both models showed balanced precision and recall across both classes

- Evaluation metrics used:
    - Accuracy
    - Precision
    - Recall
    - F1-Score
    - Confusion Matrix

### 7. Visualizations
- **Confusion Matrix** — heatmap for Logistic Regression predictions
- **Word Clouds** — most frequent words in positive vs. negative reviews

---

## 💡 Business Insights

- The balanced dataset ensures the model is not biased toward either sentiment class
- Logistic Regression (88.67% accuracy) is suitable for production deployment
- The model can be used by movie/streaming platforms to **automatically classify user reviews**
- Negative reviews can be **flagged and routed** for deeper analysis to improve user experience
- Applicable beyond movies — can be extended to customer feedback, product reviews, and brand monitoring

---

## 🧰 Libraries Used

```
pandas | numpy | matplotlib | seaborn
nltk | scikit-learn | wordcloud | re | string
```

---

## 📁 File Structure

```
├── Task4_SentimentAnalysis_usingNLP.ipynb   # Main notebook
├── IMDB_Dataset.csv                          # Dataset (not included in repo)
└── README.md                                 # Project documentation
```

---

## ▶️ How to Run

1. Clone the repository
2. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn nltk scikit-learn wordcloud
   ```
3. Download NLTK resources (already included in the notebook):
   ```python
   nltk.download('stopwords')
   nltk.download('wordnet')
   ```
4. Place `IMDB_Dataset.csv` in the working directory
5. Open and run `Task4_SentimentAnalysis_usingNLP.ipynb`

---

## ✅ Conclusion

This project demonstrates a complete NLP pipeline — from raw text preprocessing to model evaluation. Logistic Regression with TF-IDF features achieved **88.67% accuracy**, making it a strong baseline for binary sentiment classification tasks. The approach is generalizable to other text classification problems such as product reviews, social media monitoring, and customer support analysis.

---

## 👩‍💻 Author

  Harshitha Salian
  
   *Aspiring Data Analyst*
  
  **LinkedIn**: https://linkedin.com/in/salianharshitha/
