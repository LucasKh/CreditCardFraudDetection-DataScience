# CreditCardFraudDetection-DataScience

The first step would be importing the needed libraries. 

![Screenshot (79)](https://user-images.githubusercontent.com/88887839/156548955-7151db2d-a120-4cb9-8b4d-c62676681829.png)

# Explanatory data Analysis (EDA)

![Screenshot (80)](https://user-images.githubusercontent.com/88887839/156549171-17a1646a-62a3-44f7-b16b-f340a4f1ec8d.png)
![Screenshot (82)](https://user-images.githubusercontent.com/88887839/156549187-791dc515-4208-4264-a8fd-91fa3fccc406.png)
The data set is being loaded successfully and then the head of the first 5 elements were displayed on the screen. Moreover, it appears that we have 28 variables from V1 to V28 plus the time in a separation from previous transactions and amounts. It’s good to mention that this dataset contains real bank transactions but they are being hidden and transformed and the result is due toPCA dimensionality reduction. This was used in order to protect sensitive information in this dataset. For example, hiding the identity of the individual who made the credit-card transaction, in addition to location. The class here is going to be a 0 if it’s a valid normal credit card transaction and then 1 is going to be a fraudulent transaction. This dataset is being downloaded as a csv file from kaggle.

![Screenshot (83)](https://user-images.githubusercontent.com/88887839/156552119-250c1bf1-371b-4a2c-b7a8-e7abc0d840cd.png)

The number of rows here is 284807 and the number of columns is 31. Then, the missing values 
are checked and no missing values obtained.

![Screenshot (84)](https://user-images.githubusercontent.com/88887839/156552237-88ba8113-3608-462f-beda-c0e67834f738.png)

In the above figure we checked the datatypes of our variables where 30 of our variables are 
float64 and 1 variable of type integer int64.

![Screenshot (85)](https://user-images.githubusercontent.com/88887839/156552424-2c2460aa-2b2c-43d0-9310-ffe903e7a0a2.png)

After assigning 1 to the class of fraud cases and 0 for valid cases, the result was 492 cases 
considered as fraud cases and 284315 cases as valid cases.

![ScreenShot 107](https://user-images.githubusercontent.com/88887839/156553122-22d579ba-02b9-4e6b-b169-28164473dcdb.png)

This is a Pie chart is plotted using the plotly library where values are being calculated by 
dividing the amount of fraud transactions over the total transaction and similarly the amount of 
valid transactions are calculated in the same way. 

