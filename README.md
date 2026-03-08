# ✈️ Flight Recommendation System

Machine Learning term project that recommends airlines based on user reviews and service quality factors.

---

## 📌 Overview

Passengers often experience inconsistent airline service, and choosing the right airline can significantly affect overall travel satisfaction.

This project builds a **flight recommendation system** that predicts whether a user will recommend a specific airline based on previous review data and service attributes.

The system combines **collaborative filtering** and **content-based recommendation** techniques to improve recommendation quality.

---

## 📊 Dataset

Two airline review datasets were used.

| Dataset | Source | Samples |
|-------|-------|-------|
| Airline Review Dataset | Kaggle | 41,396 |
| Skytrax Airline Reviews | Skytrax | 8,100 |

### Key Features Used

- Seat Comfort  
- Staff Service  
- Food & Beverages  
- Inflight Entertainment  
- Value for Money  
- Cabin Class  
- Overall Rating  

---

## ⚙️ Methodology

The project implements **two recommendation approaches**.

---

### 1️⃣ Hybrid User-Based Collaborative Filtering

This model learns **individual user preference patterns** and recommends airlines based on similar users.

#### Main Steps

**User Preference Learning**

Each user’s preference for service factors is learned using **Ridge Regression**.

Example:

- Some users prioritize **seat comfort**
- Others prioritize **food or service**

---

**Test User Preference Estimation**

For new users, preferences are estimated using **a single rating input (1-shot learning)**.

---

**Neighbor Discovery**

Similar users are identified using **cosine similarity with shrinkage weighting** to prioritize reliable users.

---

**Recommendation Prediction**

Collaborative features are generated and fed into a **Logistic Regression classifier** to predict whether an airline will be recommended.

---

### 2️⃣ Content-Based Recommendation

This model recommends airlines based on **similarity of service attributes**.

#### Steps

1. Build airline feature profiles from review data  
2. Apply **Bayesian smoothing** to handle sparse ratings  
3. Compute **cosine similarity** between user preference and airline profiles  
4. Predict ratings using **regression calibration**

---

## 📈 Evaluation

The model was evaluated using the following metrics:

- Accuracy  
- Precision  
- Recall  
- F1 Score  

Evaluation was conducted using a **leave-one-out testing strategy**, where one rating from each user is used as the seed input.

---

## 🛠 Tech Stack

- Python  
- Pandas  
- NumPy  
- Scikit-learn  
- Collaborative Filtering  
- Content-Based Recommendation  
