# MachineHack_Predicting_Used_Cars_Price
- Predicting the prices of a Used Cars using SciKit Learn Supervised ML techniques

![](https://i.imgur.com/IhmfRed.png)
---
![](https://i.imgur.com/FcZJgZP.jpg)
- 01 - Building a Regression model to predict the prices of used cars
  * [1.1 Introduction](#11-Introduction)
  * [1.2 Libraries Used]()
  * [1.3 Algorithm]()
  * [1.4 Data Set]()

 - 02 - Index
    * [2.1 Problem Statement]()
    * [2.2 Business Understanding]()
    * [2.3 Data Exploration]()
    * [2.4 Data Cleaning]()
    * [2.5 Data Visualization]()
    * [2.6 Model Building]()
    
- 03 - Model Evaluation
     * [Validating data on split training & testing data]()
     
- [04 - Conclusion]()


---

### 1.1 Introduction
- Driverless cars are getting closer to reality and at a faster pace than ever. But it is still a bit far fetched dream to have one in your garage. For the time being, there are still a lot of combustion and hybrid cars that roar around the road, for some it chills. Though the overall data on sales of automobiles shows a huge drop in sales in the last couple of years, cars are still a big attraction for many. Cars are more than just a utility for many. They are often the pride and status of the family. We all have different tastes when it comes to owning a car or at least when thinking of owning one.

### 1.2 Libraries Used
- Numpy (for Numerical Analysis)
- Pandas (for handling data files)
- Matplotlib (for visualizations inline & figure settings)
- Seaborn (for better relational visualizations)
- Scikit Learn (for model building & data pre-processing)

### 1.3 Algorithm
- Random Forest Regression

### 1.4 Data Set
- The [DataSet](https://www.machinehack.com/course/predicting-the-costs-of-used-cars-hackathon-by-imarticus/)
 is provided by MachineHack in a Hack-a-thon conducted by Imarticus Learning
 
 ---
 
 ### 2.1 Problem Statement
 - AIM: To predict the price of used cars based on the previous data obtained from scraping several sources
 
 ### 2.2 Business Understanding
- Companies can restrict the selling price of the used car being posted by the customer in their respective websites.
- Companies can provide a visualization to customers for a better understanding of their car selling price.
- Companies can have Fraud Customers who are posting cars for higher prices.
- Companies can expand their network based on the number of cars being sold the next year by prediction.
 
 ### 2.3 Data Exploration 
| Parameter | Description  |
| --- | --- |
|Name | The brand and model of the car |
|Location| The location in which the car is being sold or is available for purchase|
|Year| The year or edition of the model|
|Kilometers_Driven |The total kilometres are driven in the car by the previous owner(s) in KM|
|Fuel_Type |The type of fuel used by the car|
|Transmission |The type of transmission used by the car|
|Owner_Type| Whether the ownership is Firsthand, Second hand or other|
|Mileage| The standard mileage offered by the car company in kmpl or km/kg|
|Engine| The displacement volume of the engine in cc|
|Power |The maximum power of the engine in bhp|
|Seats| The number of seats in the car|
|New_Price| The price of a new car of the same model|
|Price |The price of the used car in INR Lakhs|

- Null Values availability in the Data provided
![](https://i.imgur.com/kzKOd8R.png)


### 2.4 Data Cleaning
- In our current project data cleaning plays a major role
- I have dropped the data rows that consist of null values
- After looking at the box plots, I have seen that too many outliers are restricting the plot structure so removed some of the data cells with higher value to avoid model underfitting.
- Example: Removing the top 75 outliers from Kilometers_Driven column.
![](https://i.imgur.com/CJjd4Fh.jpg)

### 2.5 Data Visualization
![](https://i.imgur.com/yeq5YcK.png)
- Some of the statistics obtained from the data visualizations are
- Frequency Distributions
![](https://i.imgur.com/ocbbn4V.png)
- Maruti, Hyundai & Honda tops the list as most selling used car companies.
- Ambassador & ISUZU makes least in the list

![](https://i.imgur.com/Y2iWZ9h.png)
- Mumbai & Hyderabad stands as the top location where used cars sold in most.
- Bangalore & Ahmedabad stands least in the list

![](https://i.imgur.com/ZmUPpQ2.png)
- 95% of selling cars are Petrol & Diesel Fueled.

![](https://i.imgur.com/s3xsqXP.png)
- 75% of cars are manual, and the remaining 25% are automatic gear cars.

![](https://i.imgur.com/Ec5WyoH.png)
- More than 75% of cars handled by a single owner (First-Hand)
- 15% of cars are second handed


### 2.6 Model Building

- Before building the model, convert the categorical data into numerical categories for machines to understand using the sci-kit learn preprocessing LabelEncoder pre-defined function.
- The Frequency distribution of each field data represents below.
![](https://i.imgur.com/iu8D1an.png)
- Before training the model, we have to check the correlation between the dependent & independent variables.
    * Negatively co-related values will underfit the data, so check the model fitting procedure by dropping highly -vely related fields of data to achieve better accuracies.
    ![](https://i.imgur.com/yrPy8Xl.png)
    * By altering the dropping values of our Data  we can conclude, by dropping Model Name  & Transmission fields gives our model the best fir & validation accuracy
    
- Fit the data using Random Forest Regressor & predict the values 

---

### 3.1 Validating data on split training & testing data
- Obtain the predicted values using model. Predict () function and store the values in a variable.
- As the function is a regression model, r2_score will helps us find the accuracy of our model. Our model will be much accurate when the r2_score is nearer to 1.0

![](https://i.imgur.com/ewi3s04.png)

---
### 4.1 Conclusion
- Random Forest Regressor gives best accurate model when compared with Linear & Decision Tree regressor.
- Data Cleaning played a major role in achieving better accuracy
- Visualizing Data helped us alot to identify the patterns of data
- Removing the outliers increased the model accuracy by 10%, which is a huge improvement
- Model is saved using Pickle library and can be used further on the other data that consists of 11 columns respectively.
- Successfully obtained a RandomForestRegression model with 92% of accuracy from the data given.


