# BinaryClassificationPM

This paper focuses on applying various Machine Learning and Explainable Artificial Intelligence (XAI) approaches, to determine the binary classification of the failures on the machines which is very crucial in enhancing the reduction of downtime in industries. This paper implements and compares three classification techniques: Logistic Regression, Gradient Tree Classifier, and Random Forest. During the pre-processing stage, automatic outlier detection and over-sampling analysis are performed, and the results are compared in the interest of assessing the best performance of the model. Among the used evaluation measures, the Random Forest model has the highest average accuracy of 99% after hyperparameter tuning using the grid search method. The measure of precision and recall are perfectly balanced with the highest F1 score of 99.33%. Moreover, adopting the Explainable AI tools like SHAP and LIME, improved the model interpretability to explain how the black box models predict the machine failures by providing the global and local explanations.

This project implemented a robust Predictive Maintenance system for industrial machines, achieving a 99.33% F1-score using a Random Forest model with advanced data preprocessing, outlier detection, and oversampling techniques like SMOTE-ENN. The development process involved comparing Logistic Regression, Gradient Boosting, and Random Forest, analyzing their performance after applying various data-balancing strategies and tuning hyperparameters.

Development Process
Dataset Selection and Challenges

The AI4I 2020 Predictive Maintenance Dataset was used, consisting of 10,000 records with 14 attributes like air temperature, torque, rotational speed, and tool wear.
Challenges included a class imbalance (96.61% no-failure vs. 3.39% failure) and outliers in features like rotational speed and process temperature.
Data Preprocessing

Outlier Detection: Four techniques were compared to handle outliers without losing critical minority class data:
Local Outlier Factor, Isolation Forest, One-Class SVM, and Elliptic Envelope.
Elliptic Envelope performed best, removing irrelevant outliers while maintaining minority class integrity, reducing data from 10,000 to 8,990 records.
Class Imbalance Handling: Four oversampling methods were implemented and evaluated:
SMOTE: Synthetic data generation for minority classes.
ADASYN: Focused on harder-to-learn samples.
SMOTE-Tomek: Combined oversampling with noise removal.
SMOTE-ENN: Enhanced boundary definition by oversampling and cleaning misclassified samples.
SMOTE-ENN delivered the most balanced and clean dataset, improving the overall model performance.
Model Development and Comparison

Three machine learning algorithms were implemented:
Logistic Regression (Baseline)
Gradient Boosting Classifier
Random Forest Classifier
The dataset was split 80/20 into training and testing sets, and Grid Search was used for hyperparameter tuning.
Model Performance after Hyperparameter Tuning:

Metric	Logistic Regression	Gradient Boosting	Random Forest
Training Accuracy	88.24%	99.72%	99.88%
Testing Accuracy	87.63%	99.24%	99.33%
Precision	87.00%	98.74%	99.02%
Recall	89.81%	99.82%	99.71%
F1-Score	88.38%	99.28%	99.33%
Random Forest consistently outperformed the other models with the highest testing accuracy (99.33%) and a balanced F1-score (99.33%), indicating superior precision and recall.
Gradient Boosting performed close but required more computational time. Logistic Regression struggled with imbalanced data despite oversampling.
Model Interpretability with XAI

SHAP (Shapley Additive Explanations): Provided global feature importance to identify which factors most influenced predictions, e.g., tool wear and rotational speed were critical predictors.
LIME (Local Interpretable Model-Agnostic Explanations): Delivered real-time, localized explanations, making predictions transparent and trustworthy for specific instances.
Key Outcomes and Comparison
Random Forest was the optimal model, achieving the highest accuracy and reliability after handling outliers and class imbalance using SMOTE-ENN.
Gradient Boosting came close but at a higher computational cost.
Explainable AI (XAI) improved model transparency, ensuring stakeholders could understand both global and local predictions.
Impact and Value
This project demonstrates a full-cycle machine learning pipeline—from data preprocessing, model comparison, and performance tuning to interpretability with XAI. The system reduces unplanned industrial downtime by accurately predicting machine failures and enhances trust in AI-driven decision-making through transparent explanations.
