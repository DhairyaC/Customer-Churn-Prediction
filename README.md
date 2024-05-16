> Did you know that attracting a new customer costs five times as much as keeping an existing one?

## Overview
The core to succeed in this market lies in the customer itself. Customer churn is a critical metric because it is much less expensive to retain existing customers than it is to acquire new customers. As a result, by addressing churn, these businesses may not only preserve their market position, but also grow and thrive. More customers they have in their network, the lower the cost of initiation and the larger the profit. As a result, the company's key focus for success is reducing client attrition and implementing effective retention strategy.

## Goal
Customer churn is defined as when customers or subscribers discontinue doing business with a firm or service. Individualized customer retention is tough because most firms have a large number of customers and can't afford to devote much time to each of them. The costs would be too great, outweighing the additional revenue. However, if a corporation could forecast which customers are likely to leave ahead of time, it could focus customer retention efforts only on these "high risk" clients. The ultimate goal is to expand its coverage area and retrieve more customers loyalty.

## Objectives
1. Display the statistical values for each of the attributes, along with visualizations of the distributions for each attribute. Check if there are any attributes that might require special treatment? If so, what special treatment might they require?
2. Analyze and discuss the relationships between the data attributes, and between the data attributes and label. This involves computing the Pearson Correlation Coefficient (PCC) and generating scatter plots.
3. Select 20% of the data for testing and 20% for validation and use the remaining 60% of the data for training. Describe how we did that and verify that our test and validation portions of the data are representative of the entire dataset.
4. Train different classifiers and perform hyperparameter tuning to improve performance. Report training, validation and testing performance (classification accuracy, precision, recall and F1 score) and discuss the impact of the hyperparameters:
A. Multinomial Logistic Regression (softmax regression); hyperparameters I explored: C, solver, max number of iterations.
B. Support vector mach ines (using kernels); hyperparameters I explored: C, kernel, degree
of polynomial kernel, gamma.
5. Implemented Random Forest classifier (also analyzed feature importance); hyperparameters
I explored: the number of trees, max depth, the minimum number of samples required to split an internal node, the minimum number of samples required to be at a leaf node.
6. Combine the classifiers into an ensemble and try to outperform each individual classifier on the validation set. Once we find a good one, try it on the test set. Describe and discuss the findings.

## Techniques/Models
1. Techniques:
   - Data Validation and Cleansing (treating missing values, distribution graph, removing unwanted features).
   - Categorical Encoding.
   - Compute and visualize Pearson Correlation.
   - Feature Engineering.
   - Standardization.
   - Train Test split.
   - Performance Metric (Precision, Recall, F1 score, Confusion Matrix).
   - Grid Search CV and Randomized Search CV.
2. Models:
   - Multinomial Logistic Regression / Softmax Regression (hyperparameters tuned -> C, solver, max_iterations).
   - Support Vector Machine (hyperparameters tuned -> C, kernel, degree, gamma).
   - Random Forest Classifier (hyperparameters tuned -> No. of estimators, max_depth, min_samples_split, min_samples_leaf).
   - Ensemble Classifier (Soft Voting, Hard Voting, Stacking, Bagging).
  
## Findings
1. Random Forest outperforms the Logistic Regression and SVM Classifier models individually. One of the reason is that Random Forests can capture complex non-linear relationships in the data due to their ability to create decision boundaries based on splits in the feature space. If the underlying patterns in the data are non-linear, Random Forest can capture them effectively, whereas Logistic Regression assumes linear relationships and kernel SVM uses non-linear transformations which might not capture the complexity as well.
2. Another reason I can think of is that Random Forests are less prone to overfitting, especially when compared to complex models like kernel SVM, which can be sensitive to the choice of the kernel and its parameters. Logistic Regression, while generally robust, can also overfit if the feature space is highly dimensional and the number of samples is limited.
3. Upon looking at the classifier metrics of the ensemble model and the 3 classifiers, the ensemble model (using soft voting) outperfoms all the other 3 classifiers in terms of validation and test set accuracy which means ensemble model of the 3 classifiers is the best choice for this particular dataset.
4. Soft voting performs better than hard voting because it takes into account the confidence or probability estimates of each classifier, rather than just the final predicted class labels. This can lead to more accurate and robust ensemble predictions.
5. In summary, it is necessary to choose the most appropriate and perfect hyperparameters for the model else it may lead to drastic underfitting or overfitting of the data.
