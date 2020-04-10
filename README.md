# Sparkify

## 1. Project Summary
This project is to predict customer churn on a fictional music streaming service Sparkify.
The project utilizes Spark SQL and Spark Dataframes to manipulate a large dataset, Spark MLlib to build and tune machine learning models on IBM watson studio.
This is Capstone project for Udacity Data Science Nanodegree.
A detailed walk-through of the project can be found in [a separate article](https://medium.com/@kimjinhaha/predicting-customer-churn-leveraging-spark-and-ibm-watson-studio-fafede5d492f).

## 2. Project Components
Jupyter Notebook 'Sparkify.ipynb' includes the following steps.
### 2.1. Load and Clean Data set
Load the data set using Spark.
Clean invalid or missing data, such as records without userids or sessionids.

### 2.2. Exploratory Data Analysis
Data analysis and visualization to explore relationships between customer churn and other variables.

### 2.3. Feature Engineering
Based on the exploratory data analysis, the following features are generated:
- tenure: The number of days between the last visited day and registration day
- state: The name of state from the location variable
- browser: Browser information retrieved from userAgent
- os: Operating system information retrieved from userAgent
- device: Device information retrieved from userAgent
- num_songs: The number of songs the user listened to
- num_artists: The number of artists the user listened to
- avg_length: The average length of songs the user listened to
- Several boolean variables indicating page visits to 'Roll Avert', 'Submit Downgrade', 'Submit Upgrade', 'Thumbs Down', 'Add Friend', and 'Add to Playlist'

### 2.4. Modeling
#### 2.4.1. Train-Test split
The full data set is split into train and test data with 80:20 ratio
#### 2.4.2. Transform categorical variables into numeric variables
Since machine learning models normally require numerical input, StringIndexer and OneHotEconderEstimator are used to convert categorical variables into numeric variables.
#### 2.4.3. Scaling numeric variables
Numeric variables are scaled using StandardScaler.
#### 2.4.4. Building pipelines
Building three machine learning pipelines utilizing Logistic Regression, Random Forest Classifier, and Gradient Boosted Tree Classifier.
#### 2.4.5. Model evaluation
Since we have an imbalanced data set, with 22% churn rate, AUC (Area Under the Curve) is used in addition to the Accuracy for evaluation.
Gradient Boosted Tree Classifier show the best performance, showing 96% Accuracy and AUC of 0.99 with the default parameters.
#### 2.4.6. Hyper parameter tuning
For Gradient-boosted tree classifier, codes for hyper parameter tuning via cross-validation are included.

## 3. Technologies and tools
- Python 3.6
- Spark 2.4
- IBM Watson studio
- Detailed information about libraries can be found in the beginning of the notebook
