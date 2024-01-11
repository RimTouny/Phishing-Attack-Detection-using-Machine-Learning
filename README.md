# **Phishing Attack Detection using Machine Learning**
Advancing Cybersecurity with AI: This project fortifies phishing defense using cutting-edge models, trained on a diverse dataset of 737,000 URLs. It was the final project for the AI for Cybersecurity course in my Master's at uOttawa in 2023.
![image](https://github.com/RimTouny/Phishing-Attack-Detection-using-Machine-Learning/assets/48333870/e1bbec1b-c00d-4e98-969f-82db3805a538)


- Required libraries: scikit-learn, pandas, matplotlib.
- Execute cells in a Jupyter Notebook environment.
- The uploaded code has been executed and tested successfully within the [Google Colab](https://colab.google/) environment.


## Binary-class classification problem
Task is to classify the likelihood of a URL: Phishing , Benign.

### Independent Variables:
 The independent variables in the provided dataset can be categorized into three groups:
   + Length and Count Features:These include measures related to the length and count of different components in a URL, such as domain length, URL length, count of digits, letters, path components, and various symbols.

   + Boolean Features:These features are binary indicators, representing the presence or absence of certain characteristics in a URL, such as whether it contains an IP address (ip), has redirection (redirection), uses IPv notation (ipv), is a shortened URL (short), is encoded (is_encoded), or has a suspicious top-level domain (sus).
     
   + Calculation-Based Features:These features involve calculated values based on the URL, including a malicious probability score (malicious_probability), entropy of characters (entropy), and a ratio of special characters and digits to the total characters in the URL (ratio).
     
### Target variable:
   +	'Label' indicating the classification into two classes: 1 (Phishing) / 0 (Benign)

## **Key Tasks Undertaken**

1. **Data Concatenation:**
    - Concatenated multiple DataFrames vertically into a single DataFrame.
      + [PhishStorm-URL dataset](https://research.aalto.fi/en/datasets/phishstorm-phishing-legitimate-url-dataset#:~:text=The%20dataset%20contains%2096%2C018%20URLs,%3A%20legitimate%20%2F%201%3Aphishing.): 96011 Data Size.
      + [ISCX-URL2016 dataset](https://www.unb.ca/cic/datasets/url-2016.html): Extracted only Phishing / Legitimate from165366 rows.
      + [Malicious URL dataset](https://www.kaggle.com/sid321axn/malicious-urls-dataset.): 651,191 Data Size

2. **Feature Extraction:**
    - Defined a function for extracting features from URLs.
    - Extracted various features such as domain, path, first directory length, presence of IP address, URL length, etc.
    - Calculated counts and frequencies of characters, entropy, URL decoding, and presence of unusual characters.
    - Checked for URL shortening, special characters, and suspicious top-level domains.
  
3. **Exploratory Data Analysis (EDA)**
   - Checked dataset information, including data types and non-null counts.
   - Explored unique values in the dataset.
   - Computed and displayed descriptive statistics for numerical features.
   - Visualized data distribution using boxplots, violin plots, histograms, and correlation matrices.
     ![merge_from_ofoct](https://github.com/RimTouny/Phishing-Attack-Detection-using-Machine-Learning/assets/48333870/8d073d3c-378a-478e-9cd5-da7beaa389ee)
     ![image](https://github.com/RimTouny/Phishing-Attack-Detection-using-Machine-Learning/assets/48333870/3e908238-3f1d-423c-b64a-380a58d02922)

4. **Feature Engineering and Data Cleaning:**
   - Handling Null Values and Duplicate Rows
   - Handling Repeated Maximum Values
   - Spilting Data: Train 80% , Test 20%
   - Oversampling with SMOTE:Used SMOTE (Synthetic Minority Over-sampling Technique) to balance the training data, especially for the minority class.
     ![cd107d3e-734f-42e5-8dcf-bb36ae821eeb](https://github.com/RimTouny/Phishing-Attack-Detection-using-Machine-Learning/assets/48333870/8c183957-7e30-4eb0-92a1-49194eacb8c3)

5. **Features Selection:**Developed a function to assess and identify features with overwhelmingly repeated maximum values.
   1. Evaluated the percentage of occurrences for the most frequent value in each feature.
   2. Removed features where the maximum value was repeated over 90% of the time.
   3. Applied a 90% repetition threshold to exclude less informative or near-constant features.
   4. Improved model efficiency and computational performance by reducing redundancy in the dataset.
     ![image](https://github.com/RimTouny/Phishing-Attack-Detection-using-Machine-Learning/assets/48333870/9a04e2bd-66e1-478c-97b3-9f548f4b84d9)

   
6. **Modeling:**
   - Model Training: Trained various classification models (Logistic Regression, SVM, Decision Tree, Random Forest, XGBoost, etc.) using LazyClassifier.

      ![image](https://github.com/RimTouny/Phishing-Attack-Detection-using-Machine-Learning/assets/48333870/f78fea05-d16f-4263-ae84-8257b240520b)

   - Bias-Variance Decomposition: Implemented a function for bias-variance decomposition to analyze and quantify the bias and variance for each model.

   - Performance Evaluation: Evaluated each model's performance using confusion matrices, F1 scores, classification reports, and other relevant metrics.
     ![merge_from_ofoct](https://github.com/RimTouny/Phishing-Attack-Detection-using-Machine-Learning/assets/48333870/9341a57f-79f0-4ccf-a81e-ebb76291a376)

     

7. **Stacking and Voting Classifiers:**
   - Selecting the two models with the highest true positive rates and the two with the highest true negative
rates.
   - Combining each pair of top models using a stacking classifier approach to create ensemble models.
   - Applying soft voting to the predictions from the two ensemble models.
   - Re-evaluating the final integrated model on the test set and comparing its performance to the highest traditional model.
   
   ![merge_from_ofoct (1)](https://github.com/RimTouny/Phishing-Attack-Detection-using-Machine-Learning/assets/48333870/e8bc9d84-eaa7-4db9-8214-a757d0cc7a41)
   
   ![image](https://github.com/RimTouny/Phishing-Attack-Detection-using-Machine-Learning/assets/48333870/0c87e55b-262d-41bd-a23f-976e2ffd51e2)
   

9. **Champion Model:**
    ![image](https://github.com/RimTouny/Phishing-Attack-Detection-using-Machine-Learning/assets/48333870/a42964ae-2160-47f4-b67f-f41952ea0f54)

   

