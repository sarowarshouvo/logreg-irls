# logreg-irls
This project presents the implementation, analysis, and evaluation of logistic regression using the Iteratively Reweighted Least Squares (IRLS) algorithm to investigate how regularization enhances convergence, numerical stability, and generalization across varying data conditions. The study begins by generating a balanced, linearly separable synthetic dataset consisting of two Gaussian clusters representing binary classes (
𝑦
∈
{
0
,
1
}
y∈{0,1}). This baseline configuration provides an ideal foundation for validating IRLS behavior under perfect separability before introducing data irregularities such as noise, outliers, and imbalance.

The IRLS algorithm, derived from the maximum-likelihood estimation framework for logistic regression, iteratively updates model parameters through a weighted least-squares approximation of the log-likelihood. Both unregularized (
𝜆
=
0
λ=0) and ridge-regularized (
𝜆
>
0
λ>0) versions were implemented in R, ensuring numerical stability through probability clipping, Hessian conditioning, and careful handling of the intercept term. Regularization was incorporated via an ℓ₂ penalty to constrain coefficient magnitudes, preventing divergence and improving interpretability.

The project further examines IRLS performance under increasingly complex conditions. When outliers were introduced to break linear separability, the unregularized model produced unstable, inflated coefficients, while the ridge-regularized model maintained smooth decision boundaries and bounded norms. Additional experiments varied sample size, class balance, and feature dimension (m) to evaluate how regularization scales with data complexity. Across all settings, ridge IRLS consistently converged within 8–12 iterations, with small, stable coefficient norms (
∥
𝛽
∥
2
≈
1.7
–
2.6
∥β∥
2
	​

≈1.7–2.6), while unregularized models frequently diverged or reached iteration limits.

An 80–20 train–test evaluation confirmed that ridge regularization preserved predictive accuracy (88.9–100%) while preventing coefficient explosion and ensuring numerical conditioning. Even in high-dimensional and imbalanced datasets, the ridge model achieved comparable or superior performance with improved stability. Overall, this project demonstrates that ℓ₂ regularization is crucial for achieving robust logistic regression models. It strengthens convergence, reduces sensitivity to outliers, and enhances generalization across diverse datasets, confirming its essential role in modern predictive analytics.
