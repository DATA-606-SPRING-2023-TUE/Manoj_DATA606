# Cancellation prediction of Hotel booking

## Introduction
### In the hospitality industry, hotel cancellations are a significant challenge for hotel management as they can result in revenue losses and resource wastage. Hotel cancellation prediction is the process of using historical booking data to determine the probability of a future booking being canceled. This prediction can help hotel management optimize their revenue management strategies, allocate resources effectively, and make informed decisions about pricing and inventory management.
### There are several factors that can impact hotel cancellation rates, such as seasonality, room type, customer behavior, and external factors like weather or travel restrictions. By analyzing these variables, hotel managers can develop predictive models that provide accurate forecasts of cancellation rates.
## Aim of the Project
### The main aim of this project is to create a model that finds reservations that have a high chance of getting cancelled. This solves problems like room management and forecasting income for the hotel management. The final model can predict the reservations that could be canceled with a good accuracy. 
## Dataset
### No. of rows – 36,275
### No. of columns – 19
### Total number of values - 689,225
### This dataset has no null values, which is quite unusual for a dataset in the actual world. I requested this dataset from Microtel BWI; the absence of null values might be due to this dataset being given over by Wyndham's data management team.
## Features
 0.   Booking_ID                    - object 

 1.   no_of_adults                 - int64  
 
 2.   no_of_children               - int64  
 
 3.   no_of_weekend_nights         - int64  
 
 4.   no_of_week_nights            - int64  
 
 5.   type_of_meal_plan            - object 
 
 6.   required_car_parking_space   - int64  
 
 7.   room_type_reserved           - object 
 
 8.   lead_time                  - int64  
 
 9.   arrival_year               - int64  
 
 10.  arrival_month               -  int64 
 
 11.  arrival_date                -  int64  
 
 12.  market_segment_type         -  object 
 
 13.  repeated_guest              -  int64 
 
 14.  no_of_previous_cancellations - int64 
 
 15.  no_of_previous_bookings_not_canceled - int64 
 
 16.  avg_price_per_room           -  float64
 
 17.  no_of_special_requests       -   int64 
 
 18.  booking_status                -  object 

## Exploratory Data Analysis
### The variables "avg_price_per_room" and "leadcolumns" have highly distinctive values, making it difficult to perform data analysis. Sorting these values into clearly defined categories can make visualization easier and more effective. I’ve added three new columns for dataset.lead Timeslabs, lead time, total nights.
### There is an uptick in bookings during the summer months, while reservations decline during the winter.
![image](https://github.com/DATA-606-SPRING-2023-TUE/Manoj_DATA606/assets/91697298/b8de87e7-eead-4dda-bb5d-5ca29d99a159)
### Booking activity tends to be highest on weekends and lowest on weekdays. 
![image](https://github.com/DATA-606-SPRING-2023-TUE/Manoj_DATA606/assets/91697298/f6fce365-fcf1-47f4-ac1f-cf8f0cc444e9)
### The primary source of reservations for Microtel is online booking, followed by offline reservations.
![image](https://github.com/DATA-606-SPRING-2023-TUE/Manoj_DATA606/assets/91697298/beb0861b-d887-456b-bd12-7272c090c3b4)
### Online booking sites typically offer users a convenient cancellation policy, allowing them to cancel reservations with ease.
![image](https://github.com/DATA-606-SPRING-2023-TUE/Manoj_DATA606/assets/91697298/61908018-72c4-4995-ad90-2ab0f6ad4898)
### Most of the guest chose to stay for 3 nights.
![image](https://github.com/DATA-606-SPRING-2023-TUE/Manoj_DATA606/assets/91697298/1baf54a9-08c6-48b0-ad26-400d3a944986)
### Based on the data, it appears that guests who choose to reserve a parking spot are less likely to cancel their reservation compared to those who do not reserve a parking spot. 
![image](https://github.com/DATA-606-SPRING-2023-TUE/Manoj_DATA606/assets/91697298/86d5168c-b3e4-459e-84c8-b3f91da19239)
### Online bookings often include an option for guests to make special requests for their stay at the hotel. This suggests that the guest is committed to their stay and has specific needs or preferences. 
![image](https://github.com/DATA-606-SPRING-2023-TUE/Manoj_DATA606/assets/91697298/1ff1165f-da5d-4d6a-a8ca-5a0eac5cc7e4)

# Classification
## Logistic Regression
### This model has pipeline which pre-processes the data using standard scaler and one hot encoder. It then applies logistic regression classifier on the data and also has two levels of hyperparameter searching done using GridSearchCV. This model has an accuracy of 0.77. The accuracy might seem desirable but still can get better. The precision, recall and f1-score values are higher while predicting "Not_Canceled" but very low while predicting "Canceled". This model is incomplete and should not be used unless there is no other alternative.
![image](https://github.com/DATA-606-SPRING-2023-TUE/Manoj_DATA606/assets/91697298/1583a95b-4001-4f0d-976b-aae75930cb1e)
### AUC-ROC curve is a performance measurement for the classification problems at various threshold settings. A good model has AUC near 1, whihc means that the model can clearly predict values 0 and 1. In the above plot, we can see that the curve is not pefectly right angled, but a little bent in shape. The ROC-AUC score of the model came out to be 0.80 which is quite favourable for a classifier but not the perfect one.
![image](https://github.com/DATA-606-SPRING-2023-TUE/Manoj_DATA606/assets/91697298/c8cecb31-ad90-4c56-85c1-95765b759151)

## Decesion Tree
### This model has pipeline which pre-processes the data using standard scaler and one hot encoder. It then applies decision tree classifier on the data and also has two levels of hyperparameter searching done using GridSearchCV. This model has an accuracy of 88%. This model also has good precision recall and f-score values while prediciting both 'canceled' and 'not_canceled' values but its ability to correctly predict "not_canceled" values is higher than to predict "canceled" . This is better than the logistic regression conducted before in terms of accuracy, precision and recall values. The run time of this classifier is also pretty low compared to other models like Random forest and Grdient boosting classifiers. The "dt_results_2" is the final model with the best estimator.
![image](https://github.com/DATA-606-SPRING-2023-TUE/Manoj_DATA606/assets/91697298/8319d97f-9a68-4c4a-a8e9-dc837cdce1d6)
### This model also has better ROC-AOC score than the first model. Which means that the model is better equipped to identify and seperate the two classes. This model can be viable if the accuracy does not increase in the futher models.
![image](https://github.com/DATA-606-SPRING-2023-TUE/Manoj_DATA606/assets/91697298/d812401d-5166-45d1-85e7-6f45925a80fd)

## Random Forest
### This model has an accuracy of 90%. The precision, recall and f1 values of the model are pretty good as well. Though these values are greater while prediting "Not-canceled" just like all the other models, the values while predicting "Canceled" are good as well. This model has the highest accuracy of the three models that are analysed until now. This model is chosen after tuning the hyperparameter search with secondary grid search technique to create the best model. Considering that this model took same amount of time to run as the decision tree model, this model is dar supirior with higher accuracy.
![image](https://github.com/DATA-606-SPRING-2023-TUE/Manoj_DATA606/assets/91697298/80523bdb-4822-40a3-b33e-52b2a5a365b1)
### This model has better ROC curve as well. Compared to the previous model's ROC score of 0.93, this model has better ROC score with 0.95. This means that this model can differentiate well between the two classes. Hence this model is by far the better model of all.
![image](https://github.com/DATA-606-SPRING-2023-TUE/Manoj_DATA606/assets/91697298/f352a144-260e-490a-b715-7428523ef8c8)

## Gradient Boosting
### This model got an accuracy of 90%. This is a pretty good score for this model. The precision, recall and f1-score values are good as well. Compared to the current best model, Random forest, this model took around 15 minutes to run, for a dataset of this size, this model takes huge computational power to execute, which is not desirable unless it has a very high accuracy or precision values.
![image](https://github.com/DATA-606-SPRING-2023-TUE/Manoj_DATA606/assets/91697298/3eca1e80-fcf9-46f0-9b43-54cc17d3bd91)
### The ROC score of this model is 0.95 which is similar to that of random forest. Due to the computational effort to run this model and the similar accuracy wiht the less demanding random forest classifier, this model is not prefered for this usecase.
![image](https://github.com/DATA-606-SPRING-2023-TUE/Manoj_DATA606/assets/91697298/fcca66c9-be20-4473-af48-6a6ee03ea040)

# Conclusion
### In conclusion, hotel reservations can be canceled for various reasons regardless of the price. Based on the findings, it seems that guests who make special requests or book a parking spot are more committed to their stay and have a lower likelihood of canceling their reservation. Additionally, among the classification algorithms used, it was determined that the Random Forest algorithm was the most effective for this dataset.













