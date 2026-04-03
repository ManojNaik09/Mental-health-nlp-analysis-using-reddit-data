# 🧠 Understanding Mental Health Discourse on Reddit
### An NLP & Sentiment Analysis Study

![Python](https://img.shields.io/badge/Python-3.8+-blue?logo=python)
![NLP](https://img.shields.io/badge/NLP-NLTK%20%7C%20Scikit--learn-green)
![SDG](https://img.shields.io/badge/SDG-3%20Good%20Health%20%26%20Well--being-brightgreen)
![Course](https://img.shields.io/badge/Course-Text%20%26%20Web%20Analytics-orange)
![MBA](https://img.shields.io/badge/Program-MBA-purple)

> **Course:** Text and Web Analytics — MBA Program  
> **Student:** Megavath Sai Manoj Naik (Roll No: 24030302030)  
> **Institution:** Sri Sathya Sai Institute of Higher Learning, Brindavan Campus  
> **Guide:** Sri L K Prasad Rayaprolu, Dept. of Management & Commerce

---

## 📌 Overview

This project applies **Natural Language Processing (NLP)** and **Machine Learning** to automatically classify Reddit posts as *mental health concern* or *not a concern*. It is structured in two phases:

- **Phase 1:** Comprehensive NLP analysis on a validated Kaggle dataset (27,972 posts)
- **Phase 2:** Model stability testing on live Reddit data scraped via RSS (1,418 posts)

The study directly supports **UN Sustainable Development Goal 3 — Good Health and Well-being** by building tools that can detect mental health distress signals in online text.

---

## 🗂️ Project Structure

```
├── 24030302030_TWA_final_.ipynb   # Main Jupyter Notebook (Phase 1 + Phase 2)
├── README.md                      # This file
```

---

## 🔬 Methodology

### Phase 1 — Kaggle Dataset Analysis
| Step | Description |
|------|-------------|
| EDA | Label distribution, text length analysis, box plots |
| Preprocessing | Lowercasing, URL removal, tokenisation, stopword removal, lemmatisation |
| NLP | Word clouds, Bag-of-Words, Unigrams, Bigrams, TF-IDF |
| ML Models | Naive Bayes, Logistic Regression, LinearSVC |
| Evaluation | Accuracy, Precision, Recall, F1, ROC-AUC, Cross-validation |
| Tuning | GridSearchCV hyperparameter optimisation |
| Clustering | K-Means + t-SNE visualisation |
| Topic Modelling | LSA (Truncated SVD) + LDA |

### Phase 2 — Reddit Scraping & Model Stability
| Step | Description |
|------|-------------|
| Scraping | RSS via `feedparser` — 120+ subreddits, no API key required |
| Data Quality | HTML tag stripping, entity removal, label noise audit |
| Stability Testing | Phase 1 models applied to live data (transform only) |
| Drift Analysis | Jensen-Shannon Divergence on vocabulary shift |

---

## 📊 Key Results

### Phase 1 Model Performance
| Model | Accuracy | F1 Score |
|-------|----------|----------|
| Naive Bayes | 90.10% | 90.55% |
| Logistic Regression | **91.96%** | **91.79%** |
| LinearSVC | 91.21% | 91.04% |
| Majority Vote Ensemble | 92.06% | 92.00% |

### Phase 2 Stability (Live Reddit Data)
| Model | Phase 1 Acc | Phase 2 Acc | Delta |
|-------|-------------|-------------|-------|
| Naive Bayes | 90.10% | 81.10% | -9.00% ✅ Stable |
| Logistic Regression | 91.96% | 78.07% | -13.89% ⚠️ Monitor |
| LinearSVC | 91.21% | 77.57% | -13.63% ⚠️ Monitor |

> **Vocabulary Drift (JS Divergence): 0.37** — significant shift between Kaggle and live Reddit data, explaining the accuracy drop in Phase 2.

---

## 🛠️ Tech Stack

- **Language:** Python 3.8+
- **NLP:** NLTK, WordCloud, Gensim
- **ML:** Scikit-learn (Naive Bayes, Logistic Regression, LinearSVC, K-Means, TruncatedSVD, LDA)
- **Scraping:** feedparser (RSS)
- **Visualisation:** Matplotlib, Seaborn, pyLDAvis
- **Data:** Pandas, NumPy

---

## ⚙️ Installation & Usage

### 1. Clone the Repository
```bash
git clone https://github.com/ManojNaik09/mental-health-reddit-nlp.git
cd mental-health-reddit-nlp
```

### 2. Install Dependencies
```bash
pip install kagglehub nltk wordcloud pyLDAvis scikit-learn matplotlib seaborn pandas numpy gensim feedparser tqdm
```

### 3. Download NLTK Data
```python
import nltk
nltk.download('stopwords')
nltk.download('wordnet')
nltk.download('punkt')
```

### 4. Run the Notebook
```bash
jupyter notebook 24030302030_TWA_final_.ipynb
```

> **Note:** Phase 1 requires a Kaggle account to download the dataset via `kagglehub`. Set up your Kaggle API credentials before running.

---

## 📁 Dataset

- **Phase 1:** [Mental Health Corpus — Kaggle](https://www.kaggle.com/datasets/reihanenamdari/mental-health-corpus)
  - 27,972 labelled Reddit posts (50.5% Not Concern / 49.5% MH Concern)
- **Phase 2:** Live RSS-scraped Reddit data
  - 1,418 posts from 120+ subreddits (balanced: 709 per class)

---

## 🌍 SDG Alignment

| SDG | Relevance |
|-----|-----------|
| **SDG 3 — Good Health and Well-being** | Primary alignment — detecting mental health distress for early intervention |
| **SDG 10 — Reduced Inequalities** | Mental health disparities disproportionately affect marginalised communities |

---

## 🔮 Future Work

- Apply transformer-based models (Mental-BERT, RoBERTa) for contextual understanding
- Expand to multi-class classification (depression, anxiety, PTSD, stress)
- Use PRAW API for large-scale historical data collection (100k+ posts)
- Build a real-time mental health trend monitoring dashboard
- Incorporate temporal analysis to track language evolution

---


---

## 📄 License

This project was submitted as a course completion project for academic purposes at Sri Sathya Sai Institute of Higher Learning. All rights reserved.

---

<p align="center">Made with ❤️ for SDG 3 — Good Health and Well-being</p>
