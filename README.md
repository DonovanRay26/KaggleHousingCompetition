**KNN Regressor for Kaggle House Prices - Advanced Regression Techniques Competition**

*Overview*

This project applies a custom-built *K-Nearest Neighbors (KNN) regression model* to predict housing prices using the Kaggle House Prices:
Advanced Regression Techniques dataset. This dataset contains 79 features including both numerical and categorical data.
All code for this model is included in the KNN.ipynb notebook in the root directory. 

*Approach*

The development process for this model focused on thorough data pre-processing, feature selection and engineering, and dimensionality
reduction.

* Pre-processing pipeline
  * Numerical features were imputed with median values and scaled using StandardScaler in order to normalize the impact of all features as some features had larger ranges than others.
  * Categorical features were imputed with most frequent values and were then one-hot encoded to ensure compatibility with KNN.
* Feature Selection and Engineering
  * After pre-processing, a Spearman correlation coefficient analysis was performed to determine each features monotonic relationship with the target feature.
  * Features with an absolute correlation below 0.075 were removed from the training and test data in order to reduce noise and improve overall performance. 
* Dimensionality Reduction with Principal Component Analysis
  * Principal component analysis was applied to the model in order to mitigate the curse of dimensionality with the datasets wide and diverse range of features.
  * The number of components was tuned during validation. 
* Model Tuning
  * Multiple distance metrics were tested, including Euclidean, Manhattan, Mahalanobis, Minkowski, Chebyshev, and Correlation with uniform and non-uniformed weighting.
  * Optimal hyperparameters and model configurations were found to be:
    * k = 2
    * Chebyshev distance metric
    * Uniform weighting
    * 5 PCA components

*Results*

This model configuration and tuning resulted in an R-squared score of 0.89, indicating strong predictive power. This is due 
the utilization of the Chebyshev distance metric, which significantly improved model performance (as compared to other metrics) through
prioritizing dominant feature differences, the application of principal component analysis in order to avoid the curse of dimensionality, and feature
selection through a Spearman correlation coefficient analysis. 