# AirbnbPricePrediction
A project that compares price prediction for Airbnbs using Linear Regression and Random Forest Classifiers.

Question: Let’s say we want to build a model to predict booking prices on Airbnb. Between linear regression and random forest regression, which model would perform better and why?

# Solution
## Step 1: Data Collection
The dataset used for this project was [Airbnb Cleaned Europe Dataset]([https://www.kaggle.com/datasets/blastchar/telco-customer-churn](https://www.kaggle.com/datasets/dipeshkhemani/airbnb-cleaned-europe-dataset)) from Kaggle. It contained information about Airbnbs in Europe, the listing details and prices wich was relevant for the question. 
The overview of the data is shown below:
![Data Overview](/df_bnb.png)

## Step 2: Data Preparation
This phase includes preparing the data obtained for use by the machine learning model. It is implemented through the following steps.

### Data Preprocessing
This step involves checking the data for any missing values and replacing them in the case where the dataset is small or deleting the rows if the dataset is large. Since our dataset has 5000+ values, it would be easier to delete the rows with missing values. However, the data contained no missing values hence no need.
![Preprocessing Code Preview](/null_bnb.png)

### Exploratory Data Analysis
This is the step where the nature of the data is observed and analyzed so as to identify the best model for use and to perform feature selection and extraction. 
The first analysis is on the categorical features: room type, day and the city. 
![Room Type vs Price](/roomvsprice.png)
![Day vs Price](/dayvsprice.png)
![City vs Price](/cityvsprice.png)

Next there was boxplot plotting to show whether the data had any outliers.
![Boxplot - Price](/boxplot.png)

There was also observation of correlation between features and the price
![Correlation](/corr.png)

Finally, observation of correlation between the features.
![Correlation matrix](/corr2.png)

### Feature and Labels Selection
This stage involves selecting the columns that are relevant to the prediction and dropping the columns that are not relevant for the task at hand. After analysis, the following were used as features 'City',	'Day','Room Type','Person Capacity','Superhost','Cleanliness Rating','Guest Satisfaction','Bedrooms','City Center (km)','Metro Distance (km)','Normalised Attraction Index','Normalised Restraunt Index'.	

For the price label, it was observed to be skewed to the left and so the use of price_log to get a normalized distribution of the price.
![Price](/pricedist.png)
![Price log](/pricelog_dist.png)


### Label Encoding
Since come of the data values in the columns are categorical in nature, there is need for encoding them to a form that the model will be able to work with. This is done using label encoding. Some of the columns that needed encoding were 'City',	'Day','Room Type','Superhost'. 

### Splittling into Train and Test Sets
This is the final step in data preparation where we split the data into training tests and testing sets. The split ratio was 80:20.

## Step 3: Model Comparison
### Linear Regression
The model was trained and tested with an accuracy of 37% which was fairly good.
![linear Regression Model](/linearreg.png)

###Random Forest
The model was trained and tested with an accuracy of 81% which was fairly good.
![Random Forest Model](/rforest.png)

# Conclusion
From the above steps, for price predtiction, random forest classifier was more accurate and preferrable to the linear regression model. 




