## Ensemble Models – A Classification Project Using XGBoost for the Hotel Industry

In the hotel industry, it is essential to estimate whether a customer will follow through with a reservation. In this case, we have a dataset containing information on customer behavior related to hotel reservations and whether those reservations were honored or canceled. This project will implement XGBoost, an ensemble algorithm to predict whether a customer will cancel their reservation and classify the reservation status based on observed behavior (labeled data).


## Content

1. Objective
2. Problem Context
3. Model Implementation
    a. Importing libraries
    b. Data reading and analysis
    c. Data splitting
    d. Base model
    e. XGBoost and the optimal number of estimators
    f. Training and results of the best model
    g. Feature analysis
    h. Conclusions
    i. Final comments and further steps


## Dataset Description and Dictionary

The dataset contains various attributes related to customers' reservation details. Below is a detailed data dictionary:

| **Attribute**                      | **Description**                                                                                                                            |
|------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------|
| **Booking_ID**                     | Unique identifier of each booking                                                                                                          |
| **No of adults**                   | Number of adults                                                                                                                           |
| **No of children**                 | Number of children                                                                                                                         |
| **noofweekend_nights**             | Number of weekend nights (Saturday or Sunday) the guest stayed or booked to stay at the hotel                                              |
| **noofweek_nights**                | Number of week nights (Monday to Friday) the guest stayed or booked to stay at the hotel                                                    |
| **typeofmeal_plan**                | Type of meal plan booked by the customer                                                                                                   |
| **requiredcarparking_space**       | Indicates if the customer requires a car parking space (0 - No, 1 - Yes)                                                                    |
| **roomtypereserved**               | Type of room reserved by the customer (ciphered/encoded by INN Hotels)                                                                      |
| **lead_time**                      | Number of days between the booking date and the arrival date                                                                                |
| **arrival_year**                   | Year of the arrival date                                                                                                                    |
| **arrival_month**                  | Month of the arrival date                                                                                                                   |
| **arrival_date**                   | Day of the month                                                                                                                            |
| **Market segment type**            | Market segment designation                                                                                                                  |
| **repeated_guest**                 | Indicates if the customer is a repeated guest (0 - No, 1 - Yes)                                                                             |
| **noofprevious_cancellations**     | Number of previous bookings canceled by the customer                                                                                        |
| **noofpreviousbookingsnot_canceled** | Number of previous bookings not canceled by the customer                                                                                   |
| **avgpriceper_room**               | Average price per day of the reservation; room prices are dynamic (in euros)                                                                |
| **noofspecial_requests**           | Total number of special requests made by the customer (e.g., high floor, specific room view, etc.)                                           |
| **booking_status**                 | Flag indicating if the booking was canceled or not                                                                                          |


## Acknowledgements

The dataset for this project was sourced from: https://www.kaggle.com/datasets/gauravduttakiit/reservation-cancellation-prediction


## Model Theory

This project implements a **Supervised Learning** model using the **XGBoost** algorithm to classify the target variable.

XGBoost (eXtreme Gradient Boosting) is an advanced machine learning algorithm that enhances prediction accuracy by combining multiple weaker models to form a robust and optimized ensemble. It builds decision trees as base models and applies regularization and optimization techniques during tree construction to reduce overfitting and improve generalization. 

Below are some key parameters of the XGBoost model:

- **max_depth**:  
   Controls the maximum depth of each decision tree. Limiting depth helps prevent overfitting by reducing model complexity.

- **n_estimators**:  
   Specifies the number of trees to be built in the ensemble. Each tree is added sequentially, contributing to the ensemble’s prediction. Increasing the number of estimators generally improves accuracy but also raises computational costs.


## Results

The model achieved an 81.99% accuracy, correctly classifying 4,491 data points out of 5,150 in the positive class.