#  Topic Modeling on BBC News Articles

Uncover hidden themes and structures in news data using **Latent Dirichlet Allocation (LDA)** and **BERTopic**.  
This project applies unsupervised learning and natural language processing to cluster BBC news articles into meaningful topics like **sports**, **business**, **politics**, **technology**, and **entertainment**.

---

##  Dataset

**BBC News Dataset**  
Source: [Kaggle - BBC News Classification Dataset](https://www.kaggle.com/datasets/yufengdev/bbc-full-text-document-classification)  

- **Columns:**
  - `category`: News category (e.g., business, sport, tech, entertainment, politics)
  - `text`: Full news article text  

---

## Objective

To build an unsupervised topic modeling system that:
1. Discovers hidden topics across BBC news articles.
2. Evaluates topic coherence and perplexity.
3. Classifies new unseen articles into one of the discovered topics.
4. Provides interpretability via topic-word visualization.

---

## Technologies Used

- **Python 3.10+**
- **Scikit-learn** — LDA Model
- **BERTopic** — Transformer-based topic modeling
- **NLTK / re** — Text cleaning
- **Matplotlib / pyLDAvis** — Topic visualization
- **Gensim** — Coherence score computation
- **Google Colab** — Runtime environment

---

## Project Workflow

###  Step 1 — Text Preprocessing
Cleaned and prepared the text by:
- Lowercasing
- Removing punctuation and stopwords
- Tokenizing sentences
- Creating a `clean_text` column

### Step 2 — Feature Extraction
Used **CountVectorizer** to convert text into a document-term matrix.

##  Step 3 — LDA Topic Modeling

Trained multiple **LDA (Latent Dirichlet Allocation)** models to identify the optimal number of hidden topics within the BBC News dataset.

|    Topics (k) |    Perplexity ↓ |     Coherence ↑ |
|:-------------:|:---------------:|:---------------:|
| 3 | 1827.48 | 0.4410 |
| 4 | 1802.52 | 0.4757 |
| 5 | 1707.25 | 0.5310 |
| 6 | 1693.45 | 0.4913 |
| 7 | 1684.19 | 0.5233 |
| 8 | 1659.13 | 0.5373 |
| 9 | 1644.90 | 0.5296 |
| 10 | 1600.76 | 0.5465 |

✅ **Best Model:** Between **8–10 topics**  
➡️ These gave the highest coherence scores and most interpretable clusters.

---

## Example Discovered Topics

|   Topic |   Top Words |   Assigned Label |
|:-------:|:--------------------------------------------|:---------------:|
| 0 | user, mobile, technology, phone, service | **Tech** |
| 1 | film, award, best, year, music | **Entertainment** |
| 2 | market, economy, firm, company, price | **Business** |
| 3 | team, match, win, player, game | **Sport** |
| 4 | government, party, election, blair, labour | **Politics** |

---

## Step 4 — Text Classification Feature

After training, users can input any custom news text,  
and the model predicts the **most likely topic** with confidence scores for all topics.

## Step 5 — Visualization

Used pyLDAvis for interactive topic exploration.
It displays how topics differ, overlap, and what keywords dominate each cluster.

## Author

Jibran Mujtaba
Data Scientist | AI Enthusiast
