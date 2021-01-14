
## Topic: Credit Card Fraudulent Transaction detection (Imbalanced Data Handling)

### Introduction:
Nowadays, the problems related to financial fraud increase day by day around the world. In UK only, it is 190 billion pounds of lost money per annum. A variety of solutions to such kind of issue were implemented by vast number of banks recent years, however the fraudulence still affects a significant part of clients creating a strong erosion of confidence in banks and undermining their credibility. Money fraudulence continues to gain momentum which includes issues of plastic cards theft, breaking online-banking profiles, stealing personal information, account numbers and security codes. Thus, the actions to minimize money theft issues were undertaken but there is still an urgent need of more considerate work on finding better and stronger system to keep financial information private and difficult to hack. The implementation of AI into banking security system had already been started. Therefore, following Teradata’s success in determination of fraud schemes by their learning machines, it is important to review different AI tools for better and more accurate outcome in this regard.

## Sampling Techniques used:
The dataset was told to be extremely imbalance. There were only 0.172 % of the transactions were fraudulent. Before training our models, the imbalance in the dataset will have to be addressed as this will reduce the ability of the model to make predictions regarding the minority class. **Undersampling** and **Oversampling** techniques were used to balance out the dataset.
Random undersamping is a very simple undersampling technique whereby samples from the majority class are chosen randomly to match the number of the minority samples, therefore balancing out the data. The data was first split into cases of fraud and not fraud and the resample function from sklearn.utils module is used to randomly choose cases of not fraud as to match the number of samples of fraud. 
N-groups Ensemble involves first splitting the dataset into training and testing data and then to split the majority class into n ensembles to match the number of samples in the minority class. For example, after splitting into training and testing, there are 370 cases of fraud and 284315 cases of not fraud. Then we split the 284315 cases of not fraud in to ⌊284315/370⌋ ensembles and train the model with each ensemble and the fraud cases. 
K-means under sampling is similar to the ensemble technique however after splitting your data into n ensembles you find the centre point of each ensemble using the K-means algorithm, such that in the end you have n number of data points of the majority class to train on.
Synthetic Minority Oversampling Technique (SMOTE) and Adaptive Synthetic Sampling Approach (ADASYN) are two over sampling technique that work in a similar fashion to each other. SMOTE works by finding the k-nearest neighbour for the minority class and generates new synthetic data points on the vector connecting each neighbour. (Chawla, et al., 2002) The algorithm works by taking the feature space vector and its nearest neighbours and computes the distance between them. The difference is then multiplied a random number between (0,1) and is then added back to the features (Walimbe, 2017).
ADASYN works by using a weighted distribution for different minority class examples according to their level of difficulty in learning, where more synthetic data is generated for minority class examples that are harder to learn compared to those minority examples that are easier to learn thus the ADASYN approach improves learning with respect to the data distributions (He, et al., 2008).


## Content of the Notebook:
### I. Exploratory Data Analysis (EDA):
1. Correlation Analysis

2. Gaussian , Skewness and Kurtosis Analysis

3. Normalisation and Transformation

### II Imbalance Data Handling:
1. UnderSampling - Random Undersampling

2. UnderSampling - N-groups Undersampling

3. UnderSampling - K-Means Undersampling

4. OverSampling - SMOTE (Synthetic Minority Oversampling Technique)

5. OverSampling - ADASYN (Adaptive Synthetic Sampling Approach)

### III. Modeling:
Logistic Regression
