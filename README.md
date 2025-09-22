# 📊 Offer Ranking System for Customer Engagement  

**Hackathon:** *American Express Campus Challenge 2025 (Decison Science Track)*  
**Team:** *Brahma_Hackers*  

---

## 🚀 Problem Statement  
Customers often see multiple offers, but if those offers are not ranked effectively, engagement drops.  
Most models predict clicks independently, missing the bigger picture: *ranking the full list by relevance*.  

---

## 🔑 Our Strategy  
We built a **learning-to-rank system** that:  

1. **Captures Real Behavior**  
   - Smart sampling of non-clicked offers (no synthetic oversampling).  
   - Preserved authentic user interactions.  

2. **Extracts Powerful Signals**  
   - **Temporal**: activity by time-of-day and recency.  
   - **Behavioral**: fatigue, CTR history, impression gaps.  
   - **Semantic**: embeddings from product/service metadata.  
   - **Spending**: user-level spend patterns.  

3. **Optimizes for Relevance**  
   - Model: **LightGBM Ranker (LambdaRank objective)**  
   - Tuning: **Optuna hyperparameter search**  
   - Validation: Grouped folds to prevent leakage.  

---

## 🧩 Feature Types  

- **Temporal Features**  
  - Offer recency, age of offer, daily/hourly/weekly activity patterns and decaying weights.  

- **Behavioral Features**  
  - User CTR history, offer fatigue/delay, impression gaps and preferences.  

- **Semantic Features**  
  - TF-IDF embeddings on offer description, offer codes, and categories.  

- **Spending Features**  
  - Mean, standard deviation, and variability of user-level spending.  

---


## 📈 Results  

| Setup                           | MAP@7 |
|---------------------------------|-------|
| Baseline (naive ranker)         | 0.18  |
| + Feature Engineering           | 0.44  |
| + Smart Sampling + Tuning       | **0.53**  |

📌 **~3x improvement** in ranking quality compared to baseline.  

---

## 🛠 Tech Stack  
- **Python** (pandas, numpy, scikit-learn)  
- **LightGBM** (LambdaRank)  
- **Optuna** (Bayesian optimization)  
- **Jupyter** (experiments, visualization)  

---

## 💡 Key Insights  
- Ranking models align directly with business objectives.  
- Smart negative sampling preserves user behavior better than oversampling.  
- Careful feature design contributes more than just model complexity.  

---

## 🌍 Applications  
- **Finance** → credit offers, fraud detection alerts.  
- **E-commerce** → personalized recommendations.  
- **Marketing** → targeted campaigns & promotions.  

---

👥 *Developed by Team **Brahma_Hackers***  
