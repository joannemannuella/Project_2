![Hero](Images/machine-learning.jpg)[^1]

---
# **Business Problem**

 >*"Americans reported 271,823 cases of credit card fraud in 2019. This is an increase of 72.4 percent from 2018, when there were 157,715 cases of credit card fraud reported."*[^2]

 >*"Losses from fraud involving cards used for payment worldwide reached $27.85 billion in 2018. They are projected to rise to $35.67 billion in five years and $40.63 billion in 10 years."*[^3]

### **Problem Statement** :

Manual filtering process can be lenghty and costly process, it will required time and human resources, when business these day wouldn't have enough resources to do so.


### **Goals** :

To eliminate process of manual filtering process and increase efficiency by developing machine learning to predict the fraudulent transaction with high accuracy. To help businesses to focus on other areas so business can achieve other goals.

---

# **Requirements**

![Install requirements](Images/installing%20library.PNG)

[^a] Install the required library

![Install requirements](Images/import%20library.PNG)

[^b] Import the required library

---

# **About the Dataset**

![Kaggle Dataset Screenshot](Images/Kaggle%20Dataset.PNG)

[^4] ***Please download the dataset from Kaggl to run code, link in footnote***

"This is a simulated credit card transaction dataset containing legitimate and fraud transactions from the duration 1st Jan 2019 - 31st Dec 2020. It covers credit cards of 1000 customers doing transactions with a pool of 800 merchants.

### **Source of Simulation** :

This was generated using Sparkov Data Generation | Github tool created by Brandon Harris. This simulation was run for the duration - 1 Jan 2019 to 31 Dec 2020. The files were combined and converted into a standard format." [^5]

---

# **Anaylsis & Clean the Dataset**
### ****Garbage in Garbage out, your analysis is as good as your data****
![Cleaning Data](Images/Non-Null.PNG)

[^6] Checking for missing data, identifying datatype. crucial that the analysis has no missing data

![Deepdive dataset](Images/deep%20dive%20dataframe.png)

[^7] Deep dive via loop function through dataset

![Correlating Data](Images/heatmap.png)

[^8] Using a heatmap shows correlation between columns. The columns that didn't correlate is dropped along with "Unnamed: 0" presenting negative vaules. 

![Dropping Data](Images/dropping%20columns.PNG)

[^9] Removing unnecessary column from data

![Convert D.O.B to Age (intager)](Images/DOB%20conversion.PNG)

[^10]
Coding to convert D.O.B to Age (intager)

---

# **Cleaned Dataset**
![Identify amount of fruad vs no-fruadulant data, Imbalanced Dataset](Images/data%20percentage.PNG)

[^11] Approx 0.5% of fruad transaction in dataset

![Cleaned Dataset](Images/Cleaned%20dataset.PNG)

[^12] Dataset to use for training machine model

---

# **Encoding Dataset**
![Encoding Dataset](Images/encode%20prep.png)

[^13] Encode cleaned dataset

![Output of Encoded Dataset](Images/encoded%20output.PNG)

[^14] Output of Encode cleaned dataset

---

# **Spliting dataset**
![Spliting dataset](Images/Spliting%20dataset.PNG)

[^15] Using a fraction of cleaned dataset

---

# **Normalize Dataset**
![Normalize Dataset](Images/Normalize%20split%20dataset.PNG)

[^16] Normalize to train machine model

---
# **First Machine Model: Logistic Regression Imbalanced Dataset**
![Logistic Regrssion](Images/Logistic%20Regression%20Imbalanced.PNG)

[^17] Imbalanced Dataset through Logistic Regression Machine Model. 100% Non-frudulant prediction, 42% frudulant prediction. Average total 99% accurate machine model, biased to non-frudulant transaction prediction

---
# **Second Machine Model: KNeighboursClassifier Imbalanced Dataset**
![KNeighboursClassifier](Images/KneighbourClassfier%20Imbal%3Banced.PNG)

[^18] Imbalanced Dataset through KNeighboursClassifier Machine Model. 99% Non-frudulant prediction, 0% frudulant prediction. Average total 99% accurate machine model, biased to non-frudulant transaction prediction

---
# **Third Machine Model: LGBClassifier Imbalanced Dataset**
![LGBClassifier](Images/LGBMClassifier.PNG)

[^19] Imbalanced Dataset through LGBClassifier Machine Model. 99% Non-frudulant prediction, 43% frudulant prediction. Average total 99% accurate machine model, biased to non-frudulant transaction prediction

---
# **Balance is Key!!**
![Balance Dataset](Images/Balancing%20dataset.PNG)

[^20] Apply Random under-sampling to balance biased dataset

![Output of Balance Dataset](Images/balanced%20output.PNG)

[^21] Output of balanced Dataset

---
# **Preparing for Machine Learning**
![Standarize and normalize balanced datset](Images/Balanced%20dataset%20prep.PNG)

[^22] Spliting and normalize balanced dataset

---
# **First Machine Learning Regression, Balanced Dataset**
![Balanced dataset through Learning Regression](Images/Logistic%20regression%20balanced.PNG)

[^23] Balanced Dataset through Logistic Regression Machine Model. 75% Non-frudulant prediction, 64% frudulant prediction. Average total 69% accurate machine model of fradulant transaction

# **Second Machine LGBMClassifier, Balanced Dataset**
![Balanced dataset through LGBClassifier](Images/LGBMClassifier%20balanced%20dataset.PNG)

[^24] Balanced Dataset through LBGClassifier Machine Model. 79% Non-frudulant prediction, 68% frudulant prediction. Average total 74% accurate machine model of fradulant transaction

 ---
# **To conclude** 

**This Machine** is able to predict fradulant credit card transaction to 74% accuracy, it has been trained with good data only. Meaning bad data has been removed via human logic and column correlation analysis.

At first the data was left unbalanced and fitted to three different machine learning models, all three indicated biased prediction to the majority of the data being non-fradulant, as expected.

The machine needed to be trained with balanced data. Using the previous supervised machine learning - Logistics regression. This popular model predicts binary event occuring i.e. fradulant, non-fradulant. It is used for predicting the categorical dependent variable using a given set of independent variables. Achieving a total average of 69% accuracy predicting fradulant transactions.

The second machine learning model LGBM Classifier out performed Logistical regression by 5% fianilsing at 74% total average. "Light GBM is a gradient boosting framework that uses tree based learning algorithm. It grows tree vertically while other algorithm grows trees horizontally meaning that Light GBM grows tree leaf-wise while other algorithm grows level-wise. Leaf-wise algorithm can reduce more loss than a level-wise algorithm.

**WHY USE LGB?**

It is ‘Light’ because of its high speed. It can handle large data, requires low memory to run and focuses on accuracy of results. Also supports GPU learning and thus data scientists/ Kagglers are widely using LGBM for data science application development.

TIPS & TRICKS

The algorithm easily overfits and thus, should not be used with small (< 10K rows) datasets.
Deal with overfitting using these parameters:
Small Maximum Depth
Large Minimum Data in a Leaf
Small Feature and Bagging Fraction
Improve the training speed
Small Bagging Fraction
Early Stopping Round
Use small learning_rate with large num_iterations for better accuracy
Ideally, the value of num_leaves should be less than or equal to 2^(max_depth). Value more than this will result in overfitting
If you have a big enough dataset, use this algorithm at least once. It’s accuracy has challenged other boosting algorithms"[^25]

![Logic Regression vs LGBClassifier](Images/LGBM%20v%20Logic.PNG)

[^26] Mljar.com has tested many machine learning models against one another. We focused on Binary classificaiton between LGBM Classification vs Linear logistic regression model. LGBM classification is better 16:3 against Logistic regression. 

[^1]: machine-learning https://intotomorrow.com/how-machine-learning-can-help-credit-card-fraud-detection/

[^2]: Credit Card Frauds Top the List of US Identity Theft Crimes with 270,000 Reports in 2019 https://www.precisesecurity.com/articles/credit-card-frauds-top-the-list-of-us-identity-theft-crimes-with-270000-reports-in-2019/

[^3]: Payment Card Fraud Losses Reach $27.85 Billion - Annual Fraud Statistics Released by The Nilson Report https://www.prnewswire.com/news-releases/payment-card-fraud-losses-reach-27-85-billion-300963232.html

[^4]: Download dataset via link https://www.kaggle.com/datasets/kartik2112/fraud-detection

[^5]: Credit Card Transactions Fraud Detection Dataset  https://www.kaggle.com/datasets/kartik2112/fraud-detection

[^6]: Check and identify dataset, ***Own Code***

[^7]: Loop through dataset for deep dive, ***Own Code***

[^8]: Heatmap for coorrelation, ***Own Code***

[^a]: Install the required library, ***Own Code***

[^b]: Import the required library, ***Own Code***

[^9]: Removing Garbage Data, ***Own Code***

[^10]: Coding to convert D.O.B to Age,  3.3 Converting dob to age, https://github.com/sharmasapna/credit-card-fraud-detection/blob/main/credit-card-fraud-detection.ipynb

[^11]: Imbalanced Dataset. Approx 0.5% of fruad transaction in dataset, ***Own Code***

[^12]:  Dataset to use for training machine model, ***Own Code***

[^13]: Encode cleaned dataset, ***Own Code***

[^14]: Output of Encode cleaned dataset, ***Own Code***

[^15]: Using a fraction of cleaned dataset, ***Own Code**

[^16]: Normalize to train machine model, ***Own Code***

[^17]: Imbalanced Dataset through Logistic Regression Machine Model. 100% Non-frudulant prediction, 42% frudulant prediction. Average total 99% accurate machine model. ***Own Code***

[^18]: Imbalanced Dataset through KNeighboursClassifier Machine Model. 99% Non-frudulant prediction, 0% frudulant prediction. Average total 99% accurate machine model, biased to non-frudulant transaction prediction ***Own Code***

[^19]: Imbalanced Dataset through LGBClassifier Machine Model. 99% Non-frudulant prediction, 43% frudulant prediction. Average total 99% accurate machine model, biased to non-frudulant transaction prediction. ***Own Code***

[^20]: Apply Random under-sampling to balance biased dataset, ***Own Code***

[^21]: Output of balanced Dataset, ***Own Code***

[^22]: Spliting and normalize balanced dataset, ***Own Code***

[^23]: Balanced Dataset through Logistic Regression Machine Model. 75% Non-frudulant prediction, 64% frudulant prediction. Average total 69% accurate machine model of fradulant transaction, ***Own Code***

[^24]: Balanced Dataset through LBGClassifier Machine Model. 79% Non-frudulant prediction, 68% frudulant prediction. Average total 74% accurate machine model of fradulant transaction, ***Own Code***

[^25]: Light Gradient Boosting Method, https://www.kaggle.com/code/krithi07/logistic-to-lightgbm-for-beginners/notebook

[^26]: Lightgbm vs Linear, https://mljar.com/machine-learning/lightgbm-vs-linear/