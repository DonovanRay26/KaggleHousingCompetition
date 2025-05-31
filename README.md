**KNN Regressor for Kaggle House Prices - Advanced Regression Techniques Competition**

*Approach*

This model is featured in KNN.ipynb in the root directory of this project. The model utilizes a K-Nearest Neighbors
regressor to predict housing prices based on a dataset with 79 features including both numerical and categorical features.
In order to generate accurate predictions, this data needed to be preprocessed. The numerical features were imputed and scaled
to reduce noise and improve general quality, and the categorical features were imputed and one-hot encoded to allow them to be 
used with a regression model. This was done through a pipelined workflow. Next, in order to eliminate some of the noise associated
with the dataset, a Spearman Correlation Coefficient test was run on the features, and features with an absolute correlation of less
than 0.075 were excluded from training. Next, the model utilizes principal component analysis (PCA) to improve predictive power and reduce
noise. In testing, different distance metrics were used, various k values, various numbers of components, and testing was done with
weighted vs. unweighted distance metrics. 

*Results*

The results from testing showed that utilizing the Chebyshev distance metric, with k=2, five pca components, and without distance weighting
yielded an R-squared score of 0.89. This indicates that this model and specific configuration yields significant predictive power. This is likely
due to the Chebyshev distance metric's ability to place focus on large differences in distance, allowing it to focus on the most important features.
Utilizing PCA with this metric allowed the model to avoid the curse of dimensionality, and eliminating features with low correlation to the target
feature helped the model to reduce general noise. 