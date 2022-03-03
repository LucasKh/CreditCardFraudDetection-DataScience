# CreditCardFraudDetection-DataScience

The first step would be importing the needed libraries. 

![Screenshot (79)](https://user-images.githubusercontent.com/88887839/156548955-7151db2d-a120-4cb9-8b4d-c62676681829.png)

# Explanatory data Analysis (EDA)

![Screenshot (80)](https://user-images.githubusercontent.com/88887839/156549171-17a1646a-62a3-44f7-b16b-f340a4f1ec8d.png)
![Screenshot (82)](https://user-images.githubusercontent.com/88887839/156549187-791dc515-4208-4264-a8fd-91fa3fccc406.png)

The data set is being loaded successfully and then the head of the first 5 elements were displayed on the screen. Moreover, it appears that we have 28 variables from V1 to V28 plus the time in a separation from previous transactions and amounts. It’s good to mention that this dataset contains real bank transactions but they are being hidden and transformed and the result is due toPCA dimensionality reduction. This was used in order to protect sensitive information in this dataset. For example, hiding the identity of the individual who made the credit-card transaction, in addition to location. The class here is going to be a 0 if it’s a valid normal credit card transaction and then 1 is going to be a fraudulent transaction. This dataset is being downloaded as a csv file from kaggle.

![Screenshot (83)](https://user-images.githubusercontent.com/88887839/156552119-250c1bf1-371b-4a2c-b7a8-e7abc0d840cd.png)

* The number of rows here is 284807 and the number of columns is 31. Then, the missing values 
are checked and no missing values obtained.

![Screenshot (84)](https://user-images.githubusercontent.com/88887839/156552237-88ba8113-3608-462f-beda-c0e67834f738.png)

* In the above figure we checked the datatypes of our variables where 30 of our variables are 
float64 and 1 variable of type integer int64.

![Screenshot (85)](https://user-images.githubusercontent.com/88887839/156552424-2c2460aa-2b2c-43d0-9310-ffe903e7a0a2.png)

* After assigning 1 to the class of fraud cases and 0 for valid cases, the result was 492 cases 
considered as fraud cases and 284315 cases as valid cases.

![ScreenShot 107](https://user-images.githubusercontent.com/88887839/156553122-22d579ba-02b9-4e6b-b169-28164473dcdb.png)

* This is a Pie chart is plotted using the plotly library where values are being calculated by dividing the amount of fraud transactions over the total transaction and similarly the amount of valid transactions are calculated in the same way. 

## Histogram: 

![Screenshot (88)](https://user-images.githubusercontent.com/88887839/156553570-a3358ca0-ae93-41da-8bd9-68905f2002c8.png)

Plotting a histogram of each of parameter from V1 to V28. As we can see most of our V's are clustered right around 0 with some fairly large outliers or no outliers. 

## Correlation Matrix: 

![Screenshot (90)](https://user-images.githubusercontent.com/88887839/156553670-0bc45263-0ed8-465e-a67f-6a7ecbd09cf5.png)

The above figure is a correlation matrix with the heat map where there’s a lot of values close to zero so there are not strong relationships between the different V parameters the v1 though v28 most of them are fairly unrelated to the others. However, the class is the interesting part here where there are some variations in the relationships between the different parameters and the class here, so the lighter ones are going to be a positive correlation while the darker would be strong negative correlation. Moreover, there is not a strong correlation between amount and whether its fraudulent or not or even time whether its fraudulent or not.

## Bargraph:

V3, V7, V10, V11, V12, V14, V16, and V17 have a strong correlation with target(class) 
compared to other features. And down below is the figure that illustrates the correlation between 
these parameters and the class.

![Screenshot (91)](https://user-images.githubusercontent.com/88887839/156553801-f477f673-2bfb-4a76-ae82-9a4a22ad2308.png)

## Duplicate Entries 
Now, It’s good to check for duplicate entries and drop these entries where 1081 rows are 
duplicated and then dropped.

![Screenshot (92)](https://user-images.githubusercontent.com/88887839/156553975-50dff081-9776-4409-93e0-89ba70bf2c0f.png)

# Training and Testing:
Before splitting our dataset into training set and testing set its good to declare 2 variables that refers to independent and dependent variables. The test size of the testing set is 30% as the best practice while 70% would be for the testing set. Moreover, the training and testing set shape is presented below:


![Screenshot (94)](https://user-images.githubusercontent.com/88887839/156554240-e07c7b0b-0cad-4b02-855a-7f7a1b7ea2ef.png)

# Model Building:

Machine Learning and data science are interrelated fields it’s one of the many tools used in data science. Although there are many machine different algorithm, six different machine learning algorithms are used in this project namely Decision Tree, K-Nearest Neighbors (KNN), Logistic Regression, Support Vector Machine (SVM), Random Forest, and XGBoost. Due to the fact that the problem is considered as a classification problem, these models are a good fit for this problem.

* The fit() function is used to train the models on the dataset and the predictions made by the models are recorded using the predict() function.

* The first model would be the decision tree where the main criteria used is the entropy that allows to build the tree where the lowest entropy would encounter for the highest information gain and would be considered as the root of the tree. The rest of models are done in the samae way but an example of how its done is shown below: 

![Screenshot (96)](https://user-images.githubusercontent.com/88887839/156554617-314634d6-c7bb-4299-b9ca-2499fcb016e5.png)

# Evalution of all the models: 

![Screenshot (101)](https://user-images.githubusercontent.com/88887839/156555565-69efb377-c0cf-4690-8851-fb46e86dba28.png)

![Screenshot (102)](https://user-images.githubusercontent.com/88887839/156555573-a8e5837d-900d-4ca2-a7fb-b765ea69dbe5.png)

XGBOOST and random forests ranks the 2 best classifiers in this report.

## Confusion Matrix:
A confusion matrix will be showing the degree of success of each model when comparing the predicted values to the real values. Then confusion matrix is plotted as a correlation table at first but then in a form of a heat map. This visualization of all the classification models help to identify which model performed better than the other in prediction.
After evaluting the performance of all the models, the XGBOOST ranked the best classifier so its confusion matrix in the form of a heatmap would be as follows:


<img width="382" alt="Screenshot 108" src="https://user-images.githubusercontent.com/88887839/156557685-a9fd583d-b33a-4fb6-964f-1fd488848d63.png">

For more detailed explanation, the rest of the confusion matrix are presented in the report.

# Conclusion
This project consolidated the explanatory data analysis with the implementation of machine learning algorithm. The dataset was fully explored and visualized using different techniques of visualization either bar graph, correlation matrix, histograms and pie charts. This helped to make the data clearer and more understandable. Then, six classification models were implemented starting from decision trees to XGBOOST. All things considered, these models were evaluated using different evaluation metrics from F1-Score to accuracy, recall and precision. The results were satisfying where XGBOOST had the best accuracy of 99.995% followed by random forests. Finally, due to the fact that the data is real data, it can be noticed that more than 99% of transaction are valid and not fraud while the fraud cases accounts for 0.17%. This creates an imbalance between the classes and this imbalance issue will cause bias towards the non-fraud transaction accounting for higher accuracy. Thus, there are various techniques to deal with this imbalance such as oversampling or under sampling that can be discussed in the future.
