# **Prediction of Grocery Sales**
**Author:** Justice Mansfield-Beaulieu
![image credit:](https://cdn.apartmenttherapy.info/image/upload/v1561242428/stock/shutterstock_373602469.jpg)

## **Project Overview**
Data has been collected from the year 2013 by data scientist at BigMart, they were able to collect 1559 products over 10 stores in many different cities. With the features each product provideds we can use that to create a predictive model 
to predict the sales of each product from different locations.

### **Data Source**
Big Mart Sales Prediction - [datahack.analyticsvidhya.com](https://datahack.analyticsvidhya.com/contest/practice-problem-big-mart-sales-iii/)

### **Data Dictionary**
- **Item_Identifier:** Unique product ID
- **Item_Weight:** Weight of product
- **Item_Fat_Content:** Whether the product is low fat or regular
- **Item_Visibility:** The percentage of total display area of all products in store allocated to the particular product
- **Item_Type:** The category to which the product belongs
- **Item_MRP:** Maximum Retail Price (list price) of the product
- **Outlet_Identifier:** Unique store ID
- **Outlet_Establishment_Year:** The year in which store was established
- **Outlet_Size:** The size of the store in terms of ground area covered
- **Outlet_Location_Type:** The type of area in which the store is located
- **Outlet_Type:** Whether the outlet is a grocery store or some sort of supermarket
- **Item_Outlet_Sales:** Sales of the product in the particular store. This is the target variable to be predicted.

## **Models Evaluated & Results**

### Used the following models during machine learning
- Linear Regression Model
- Decision Tree Regressor Model
### Model Evaluation & Results

- Linear Regression Model (Testing Set):
  - MAE: 804.3063 
  - MSE: 1,194,455.9463 
  - RMSE: 1,092.9117 
  - R2: 0.5671

- Decision Tree Regressor Model (Testing Set):
  - MAE: 738.3173 
  - MSE: 1,118,185.9731 
  - RMSE: 1,057.4431 
  - R2: 0.5947


- The final Model picked was the Decision Tree Regressor Model with the based model
- The testing set on the model is at 59.5%
- The Mean Absolute Error is off by about ₹738.32
- The Mean Square Error was ₹1,118,185.97
- The Root Mean Square Error is ₹1,057.44

## Importances and Coefficients
- LinearRegression coefficients plot 
![LinearRegression coefficients plot:](http://localhost:8888/view/Images/Top-5-most-important-features.png)
    - Outlet Type Supermarket Type 3
        - Being sold in an Outlet type of Supermarket Type 3 increases Item Outlet Sales by ₹3,132.40
    - Outlet Type Supermarket Type 1
        - Being sold in an Outlet type of Supermarket Type 1 increases Item Outlet Sales by ₹1,873.91
    - Outlet Type Supermarket Type 2
        - Being sold in an Outlet type of Supermarket Type 2 increases Item Outlet Sales by ₹1,424.40
Looking at the top three coefficients this makes sense since Outlet Type Supermarket Type 3 had the most sales overage followed by Outlet Type Supermarket Type 1 and then Outlet Type Supermarket Type 2.

- Tree-Based Model feature importance
![Tree-Based Model feature importance plot:](http://localhost:8888/view/Images/Top-3-coefficients.png)
    - The top 5 most importance features to our Tree-based model are:
        - "Item_MRP" ( Maximun Retail Price (list price) of the product)
        - "Outlet_Type_Supermarket Type3" (Outlet Supermarket type 3)
        - "Item_Visibility" (The percentage of total display area of all products in a store allocated to the particular product)
        - "Outlet_Type_Supermarket Type1" (Outlet Supermarket type 1)
        - "Item_Weight" (Weight of product)

## Global Explanations

![Summary Plot Bar:](http://localhost:8888/view/Images/summary_plot_bar.png)
- Comparing our top 5 feature importance to our top 5 SHAP value there are some similarities and differences. Item_MRP is still both at number 1 for SHAP values and features importance.
    - Outlet_Type_Supermarket Type3 is placed at number 3 for SHAP values but placed at number 2 for feature importances. 
    - Outlet_Type_Supermarket Type1 is placed at number 2 for SHAP values but placed at number 4 for feature importances. 
    - Item_Visibility is placed number 5 for SHAP values but placed at number 3 for feature importances
    - Outlet_Size_Medium is new to our top 5 SHAP values that isn't shown in our feature importance.
    - Item_Weight wasn't shown in our top 5 SHAP values but shown in our top 5 feature importance.
    
![Summary Plot Dot:](http://localhost:8888/view/Images/summary_plot_dot.png)
- SHAP Summary Plot Interpretation:
    - Item_MRP
        - The blue values are on the negtive side and the red values are on the postive side.
            The greater the Item_MRP the greater the Item_Outlet_Sales.

    - Outlet_Type_Supermarket Type3
        - The red values are on the postive side and Outlet_Type_Grocery Store equals 1, showing it's not a Supermarket Type3.
            Then the model will increase the value for 'Item_Outlet_Sales'.
        - The blue dots are on the right showing negative, and Outlet_Type_Grocery Store equals 0, showing it is a Supermarket Type3.
            Then the model will decrease the value for 'Item_Outlet_Sales'.

    - Outlet_Type_Supermarket Type1
        - The red values are on the postive end and Outlet_Type_Supermarket Type1 equals 1, showing it is a Supermarket Type1.
            The model will increase the value for Item_Outlet_Sales.
        - The blue values are on the negative side and Outlet_Type_Supermarket Type1 equals 0, showing it is a not a Supermarket Type1.
            Then the model will reduce the value for 'Item_Outlet_Sales'.


## Self Recommendations
- After working on this data set there are is some work still be done on my part. These results won't be the end of my predictions, I plan to add more models and do more tuning on my models. 
- Adding on, I plan to dive deeper into my exploratory and explanatory data anaylsis to get graphs more tailored towards profits and prices and include more functions and overall clean up my code
