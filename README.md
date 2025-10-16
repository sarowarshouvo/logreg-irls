# logreg-irls
# Implementation and Analysis of Logistic Regression using the IRLS Algorithm

This project implements and analyzes **logistic regression** using the **Iteratively Reweighted Least Squares (IRLS)** algorithm to explore how **ℓ₂ regularization (ridge penalty)** improves convergence, numerical stability, and generalization across different data conditions.

## 🔍 Overview
The study begins with a **balanced, linearly separable synthetic dataset** generated from two Gaussian clusters representing binary classes (`y ∈ {0,1}`). This setup establishes a clean baseline to validate IRLS behavior before introducing irregularities such as **noise, outliers, and imbalance**.

The **IRLS algorithm**, derived from maximum-likelihood estimation, iteratively updates model parameters through weighted least-squares approximations of the log-likelihood. Both **unregularized (λ = 0)** and **ridge-regularized (λ > 0)** versions were implemented in R, with attention to:
- Probability clipping for numerical stability  
- Proper intercept handling  
- Hessian conditioning and convergence monitoring  

## ⚙️ Experiments
The project examines model performance across:
- Clean vs. noisy data (with injected outliers)  
- Small vs. large datasets  
- Balanced vs. imbalanced class distributions  
- Higher feature dimensions (m > 2)  

Ridge regularization consistently produced **bounded coefficients**, **smooth decision boundaries**, and **stable convergence** (8–12 iterations), while unregularized models often diverged or required the maximum iteration limit.

## 📈 Results
- **Train–test split:** 80–20  
- **Accuracy:** 88.9% – 100%  
- Ridge IRLS achieved comparable or superior accuracy with smaller parameter norms (‖β‖₂ ≈ 1.7–2.6).  
- Regularization improved conditioning and generalization without sacrificing predictive performance.

## 🧠 Conclusion
**ℓ₂ regularization** is essential for robust logistic regression modeling. It stabilizes convergence, reduces sensitivity to outliers, and enhances interpretability across diverse datasets.

---

### 📂 Repository
**Name:** `logreg-irls`  
**Language:** R  
---
