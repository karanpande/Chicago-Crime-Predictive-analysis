TEAM RAGING BULLS 


Team members

Karan Pande, Shweta Khairnar, Harpreet Kour, Kartik Rajput

➢	Abstract
We identify a predictive task, train and evaluate models to perform predictions if an arrest would be carried out for a crime.We do this by taking into consideration the area code , the beat were the crime has taken place and the type of crime into consideration. 


➢	Dataset 
The dataset chosen for this project consists of incidents of crime reported in the city of Chicago from 2001 to 2017. 

Source: https://data.cityofchicago.org/Public-Safety/Crimes-2001-to-present/ijzp-q8t2
Title: Crimes_-_2001_to_present


➢	DATA CLEANING
Below Data Cleaning have been done to make our analysis way easier and observatory:

a.	The dataset has been reduced to year '2007-2017' as it was too large with 6297578 observations.
b.	All useful variables have been converted to categorical variables.
c.	Removed Missing Values and Whitespaces.
d.	Variable Date in original dataset has been segregate into Day, Month and Weekday variables.
e.	Converted different format of ‘Non-Criminal’ category under Primary. Type variable into one.
f.	Duplicates observations have been removed.


➢	EXPLORATORY ANALYSIS 







➢	PREDICTIVE TASK 

We identified a predictive task based on the information available in the data set. 

⇒	Predicting whether an arrest will be made for a committed crime:  Our predictive task was to predict arrests for reported crimes.

To perform this prediction we used KNN- k nearest neighbors, which is a simple algorithm that stores all available cases and classifies new cases by a majority vote of its k neighbors. This algorithm segregates unlabeled data points into well-defined groups.

We took a random sample of 25000 observations to predict the arrest likelihood based on past arrests in our model. 

As our entire explanatory variable are categorical, we create dummies for the same. This feature is of paramount importance since the scale used for the values for each variable might be different. The best practice is to convert the value to 1 if the feature was present, 0 if absent and transform all the values to a common scale.

The KNN algorithm is applied to the training data set and the results are verified on the test data set.
For this, we would divide the data set into 2 portions in the ratio of 80: 20 for the training and test data set respectively. 

The explanatory variables were chosen based on the pre-processing done during the exploratory analysis. 7 variables were considered:
a) Month: In which the crime happened represented as a 12 feature vector 
b) Type of crime such as Narcotics, Battery etc. represented as a 34 feature vector, one for each crime type. This was represented as a feature vector with categorical labels (1 if present, 0 if absent). A total of 32 categories were identified. 
c) Location description: A short description of the street/location in which the crime happened. The location description was used as a categorical label and represented as a binary value (1 if the feature was present, 0 if absent). 
d) Beat: A beat is the smallest police geographic area in which crime happened.
e) Weekday: In which day of the week crime happened represented as a 7 feature vector.
f) District: Indicates the police district where the incident occurred.
g) Year: In which year(2007-2017) a crime occurred.

Month was chosen because our exploratory analysis indicates that it is a seasonal influence in crime rate. This is revealed in above Figure. Since it is correlated with the rate of crime, by transitivity it is also correlated with the arrest rate for the crime. If there is more crime in a month then correspondingly, there will be more arrests. Our analysis also indicated that the probability of an arrest is heavily influenced by crime type. 

Above Figure also reveals that there are high disparities in arrest rate with some of the crime categories. Since this is the case, it seems that crime type is a strong predictor of whether or not there will be an arrest. 

The location description was thought to influence arrest rate as well because it seems that it is more common for arrests to be made in some locations more often than others. For example, it may be more likely for an individual to be arrested for battery in the middle of a parking lot than in a more discrete location such as an alley way. This feature was added because of this qualitative assumption. We found that the score improved after adding this as a feature. 

Beat, Weekday, District, Year were taken under consideration as they influence the time and area of the crime.

All of the features were represented as binary vectors in order to allow equal representation and individual weights for each possible choice of each feature. Preprocessing was done on all of the categorical variables in order to map them to their corresponding binary feature vector representations.

Train a model:

knn () function needs to be used to train a model. The knn() function identifies the k-nearest neighbors using Euclidean distance where k is a user-specified number.

The value for k in our model is 111.

Knn() function returns a factor value of arrest labels for each observation in the test data.




➢	EVALUATION AND RESULTS 

The following section documents the evaluation results for the predictive tasks described in the previous section. Explanatory variables are defined and predictive models are built in an attempt to improve the  performance. The results are documented and analyzed. 

Pros of KNN: The algorithm is highly unbiased in nature and makes no prior assumption of the underlying data. Being simple and effective in nature, it is easy to implement and has gained good popularity.

For each predictive task, we split the data set into training and test set. We then trained the models and used them to predict the labels on the test set.

The total accuracy of the model is 82% 

This indicates that the arrest probability for the type of crime committed has a very strong influence in whether or not there will be an arrest. 

➢	CONCLUSION 

In this project, we used data mining techniques to perform predictive tasks on crime data. A predictive task wes implemented - predicting arrests for a given type of crime in a given location. Pre-processing of data prior to training the model helped us identify useful features for building the models. The models used the techniques we learnt in the course. The results from evaluation are discussed and documented. Though we observed repeated patterns in crime count over months with summer being the highest, it did not add value to the prediction of whether or not arrests will be made but did help influence the prediction in term of number of crimes in a beatday. The type of crime also played strong role in predicting arrests and crime frequencies in Chicago. These tasks can be further extended to include much more extensive patterns in predictive crime if information about the victims and the offenders are made available.







