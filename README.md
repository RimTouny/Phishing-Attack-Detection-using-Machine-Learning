# **Phishing Attack Detection using Machine Learning**
Advancing Cybersecurity with AI: This project fortifies phishing defense using cutting-edge models, trained on a diverse dataset of 737,000 URLs. It was the final project for the AI for Cybersecurity course in my Master's at uOttawa in 2023

- Required libraries: scikit-learn, pandas, matplotlib.
- Execute cells in a Jupyter Notebook environment.
- The uploaded code has been executed and tested successfully within the [Google Colab](https://colab.google/) environment.


## Binary-class classification problem
Task is to classify the email dataset into two classes: Spam / Not Spam.

### Independent Variables:
   +	57 Features related to word frequencies, character frequencies, and capital run lengths.
### Target variable:
   +	'Target' indicating the classification into two classes.


## **Key Tasks Undertaken**

1. **Data Loading and Exploration:**
    - Loaded CSV files into Pandas DataFrames.
    - Created a binary column based on an existing column.
    - Explored and visualized the distribution of labels using a pie chart.
    - Checked for and displayed duplicate rows in the DataFrames.
      
2. **Data Concatenation:**
    - Concatenated multiple DataFrames vertically into a single DataFrame.
    - Checked for and removed duplicate rows from the concatenated DataFrame.
      
3. **Data Balancing:
    - Balanced the dataset by randomly undersampling the majority class.
    - Displayed the class distribution in the balanced dataset using a pie chart.
      
4. **Feature Extraction:
    - Defined a function for extracting features from URLs.
    - Extracted various features such as domain, path, first directory length, presence of IP address, URL length, etc.
    - Calculated counts and frequencies of characters, entropy, URL decoding, and presence of unusual characters.
    - Checked for URL shortening, special characters, and suspicious top-level domains.
  

5. **Exploratory Data Analysis (EDA)**
   - Checked dataset information, including data types and non-null counts.
   - Explored unique values in the dataset.
   - Computed and displayed descriptive statistics for numerical features.
   - Visualized data distribution using boxplots, violin plots, histograms, and correlation matrices.

5. **Feature Engineering and Data Cleaning:**
   - Handling Null Values and Duplicate Rows
   - Handling Repeated Maximum Values
   - Investigated features with overwhelmingly repeated maximum values and took appropriate actions.
   - Oversampling with SMOTE:Used SMOTE (Synthetic Minority Over-sampling Technique) to balance the training data, especially for the minority class.

5. **Modeling:**
   - Model Training: Trained various classification models (Logistic Regression, SVM, Decision Tree, Random Forest, XGBoost, etc.) using LazyClassifier.

   - Performance Evaluation: Evaluated each model's performance using confusion matrices, F1 scores, classification reports, and other relevant metrics.

6. **Bias-Variance Analysis:**
   - Bias-Variance Decomposition: Implemented a function for bias-variance decomposition to analyze and quantify the bias and variance for each model.

7. **Stacking and Voting Classifiers:**
   - Stacking Classifiers: Implemented stacking classifiers using different base models and a meta-model (Logistic Regression).
   - Soft Voting: Applied soft voting to combine results from multiple models.
   
8. **Comparing and Selecting Models:**
   - Model Comparison: Analyzed and compared models based on key metrics such as True Positive (TP), True Negative (TN), and F1 score.
   - Model Selection: Selected the best-performing models based on the analysis.

9. **Ensemble Classifier:**
   - Soft Voting Ensemble: Created an ensemble classifier using soft voting with the best models for True Positive and True Negative.
   - Evaluation: Evaluated the performance of the ensemble classifier.

10. **Results Comparison:**
   - Displayed and compared the results of the champion model and the ensemble classifier.

