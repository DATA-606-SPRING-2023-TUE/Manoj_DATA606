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

