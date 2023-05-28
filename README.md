<h1 align = "center">Investigate Business Hotel using Data Visualization</h1>

<p align="center">
  <img src="https://ascentiumcapital.com/images/default-source/Blog/blog-header-hotel-reception-desk-with-bell.jpg?sfvrsn=311cdc25_0"/>
</p>

<h2> Project Overview </h2>
"It is crucial for a company to constantly analyze its business performance. On this project, we will analyze deeper into the business in the hotel industry. Our focus is to understand the behavior of our customers when making hotel reservations and its relationship to the cancellation rate of hotel bookings. The insights we discover will be presented in the form of data visualization to make it easier to understand and more persuasive."

<h3> Data Overview </h3>
This project will use a dataset that contain booking informations from resorts and hotels, such as number of guests, arrival time, reservation status, and so on. This dataset contains 119390 records, and 30 features.

<details>
  <summary>click here to see features description</summary>
  
  > Booking data
> * Hotel (H1 = Resort Hotel or H2 = City Hotel)
> * is_canceled = Value indicating if the booking was canceled (1) or not (0) 
> * adr = Average Daily Rate as defined by dividing the sum of all lodging transactions by the total number of staying nights
> * lead_time = Number of days that elapsed between the entering date of the booking into the PMS and the arrival date
> * arrival_date_year = Year of arrival date
> * arrival_date_month = Month of arrival date
> * arrival_date_week_number = Week number of year for arrival date
> * arrival_date_day_of_month = Day of arrival date
> * company = ID of the company/entity that made the booking or responsible for paying the booking.
> * agent = ID of the travel agency that made the booking
> * city = city of the hotel
> * deposit_type = Indication on if the customer made a deposit to guarantee the booking. 
> * days_in_waiting_list = Number of days the booking was in the waiting list before it was confirmed to the customer.
> * distribution_channel = Booking distribution channel.
> * required_car_parking_spaces = Number of car parking spaces required by the customer
> * reservation_status = Reservation last status.
> * reservation_status_date = Date at which the last status was set. This variable can be used in conjunction with the ReservationStatus
> * stays_in_weekend_nights = Number of weekend nights (Saturday or Sunday) the guest stayed or booked to stay at the hote
> * stays_in_week_nights = Number of week nights (Monday to Friday) the guest stayed or booked to stay at the hotel
> * total_of_special_requests = Number of special requests made by the customer (e.g. twin bed or high floor)
  
> Customer Data
> * is_repeated_guest = Value indicating if the booking name was from a repeated guest (1) or not (0)
> * adults = Number of adults
> * children = Number of children
> * babies = Number of babies
> * meal = Type of meal booked. 
> * customer_type = Type of booking, assuming one of four categories
> * market_segment = Market segment designation.
> * previous_cancellations = Number of previous bookings that were cancelled by the customer prior to the current booking
> * previous_bookings_not_canceled = Number of previous bookings not cancelled by the customer prior to the current booking

</details>

<h2>Data Cleansing</h2>

* Missing Value Handling

  There are several columns that contain missing value:
  
  ![image](https://github.com/lutfiahk/Investigate-Business-Hotel-using-Data-Visualization/assets/99700225/e4cd6bc2-84b8-48bb-b405-9baff157125b)

    There are several columns that have missing values, so we will handle the missing values as follows:
    * For the "children" column, we will fill the missing values with 0.
    * For the "city" column, we will fill the missing values with 'others'.
    * For the "agent" column, we will fill the missing values with 0, indicating that no travel agent made the booking.
    * For the "company" column, we will fill the missing values with 0, indicating that no company made the booking or is responsible for paying the booking.

* Correct the incorrect data

    There is incorrect data input in the 'meal' column. We will replace the 'undefined' data with 'No meal'.

* Drop incorrect data

<p align="center">
  <img src="https://github.com/lutfiahk/Investigate-Business-Hotel-using-Data-Visualization/assets/99700225/36c5c80b-d9dc-4248-831b-1bca1af963d9"/ width="300" height="200">
</p>
  
  
There are 180 rows of data that have no guest, so we will drop these records. And there is booking record that has negative adr value, and also the is booking record   that has an extremely high value of adr with canceled status. So we will drop these records too.

<h2>Data Analysis</h2>

<h3>Customer Characteristics</h3>

<p align = "center">
  <img src = "https://github.com/lutfiahk/Investigate-Business-Hotel-using-Data-Visualization/assets/99700225/2e10bf6a-267d-42fb-b40a-c09feb810214"/ width = "300">
</p>

<b>37.1%</b> of the 119,209 bookings have been canceled.

<p align = "center">
  <img src = "https://github.com/lutfiahk/Investigate-Business-Hotel-using-Data-Visualization/assets/99700225/49587f65-c8a5-4e5a-8b0a-4f7a18a64905"/ width = "300">
</p>

The majority of customers is a new customer, and the number of canceled booking from new customer is higher than from the repeated customer. But we need to check if the proportion is different or not by conducting z-proportion test. 

> Z-statistic: 28.91<br>
> p-value: 0.0<br>
> The difference in proportions between the two groups is statistically significant, canceled Booking of New Customer has the highest proportion: 0.38<br>

The z-proportion test revealed a significant difference between the new customer and repeated guest groups in terms of canceled bookings, with new customers having the highest proportion at 38% of total new customers.

<p align = "center">
  <img src = "https://github.com/lutfiahk/Investigate-Business-Hotel-using-Data-Visualization/assets/99700225/13c2c63c-0493-489f-94c6-a7dce12bf165"/ width = "300">
</p>

66.4% of bookings are for City Hotels, which are usually found in urban areas, providing convenient access to business districts, shopping centers, and transportation hubs. Resort hotels, on the other hand, are situated in scenic destinations like beaches or mountains, offering natural surroundings and recreational activities.

This makes sense because the majority of customers are not families, indicating that there may be more customers using hotels for business travel or reasons other than vacation purposes.

<p align = "center">
  <img src = "https://github.com/lutfiahk/Investigate-Business-Hotel-using-Data-Visualization/assets/99700225/0d9bd163-85b7-4517-8611-1d55c093f07e"/ width = "300">
</p>

<h3>Monthly Hotel Booking Analysis Based on Hotel Type</h3>

<p align = "center">
  <img src = "https://github.com/lutfiahk/Investigate-Business-Hotel-using-Data-Visualization/assets/99700225/f00734e1-64d8-4bd7-9673-1d9a9734ef6d"/ width = "500">
</p>

High booking numbers are around the months of July until October. During the year, city hotels are booked more frequently than resort hotels.

As we know, July to October is not the holiday season, and the majority of customers are not families. Therefore, it is likely that many customers are traveling for business purposes or reasons other than vacation. Moreover, city hotels are typically located in the center of the city where many offices and economic activities take place

<h3>Impact Analysis of Stay Duration on Hotel Bookings Cancellation Rates</h3>

<p align = "center">
  <img src = "https://github.com/lutfiahk/Investigate-Business-Hotel-using-Data-Visualization/assets/99700225/d3d34c38-a12d-48a8-9cec-cd38f2d3206c"/ width = "500">
</p>

Basically, the cancellation rate of the city hotel is higher than the resort hotel. It is known that the longer the stay duration of customers, the higher the cancellation rate at the city hotel. The cancellation rate of the resort hotel tends to be consistent, ranging from 27% to 45%.

<b>We need to highlight the cancellation rate of the city hotel. The cancellation rate for bookings with a stay duration of more than 2 weeks is over 50%, which is a high number.</b>

<h3>Impact Analysis of Lead Time on Hotel Bookings Cancellation Rate</h3>

<p align = "center">
  <img src = "https://github.com/lutfiahk/Investigate-Business-Hotel-using-Data-Visualization/assets/99700225/56daa173-7485-430b-b995-0903ed321db8"/ width = "500">
</p>

The cancellation rate of the city hotel for each lead time is higher than that of the resort hotels. As we know, the lead time of more than 9 months is particularly high, especially for the city hotel that reach above 70%.

Therefore, the company needs to develop a strategy to decrease the cancellation rate by considering offering special packages or deals specifically for bookings with high lead time. This can provide added value to customers and encourage them to proceed with their bookings.

<h2>Conclusion</h2>

* The majority of customers are non-family customers, who book city hotels which are mainly located in the center of the city. The majority of the customer tends to be on non-vacancy purpose. The company needs to make strategies or marketing that refer to the needs and preferences of these customers.

* Above 90% of the customers are new customers. Having a high number of new customers is a positive indication of the company's ability to attract new business, but the company needs to be focuses on building customer loyalty. 

    Therefore, the company should implement strategies that prioritize customer retention, such as loyalty programs, personalized experiences, and excellent customer service, to ensure a strong foundation of loyal customers and sustained business growth.

* For the city hotel, the longer the stay duration, the higher the cancellation rate tends to be. Therefore, the company needs to implement promotions to decrease the cancellation rate, such as offering discounts for customers who stay for more than 2 weeks.

* As we know the longer the lead time, the cancellation rate tends to be higher, the company needs to develop a strategy to decrease the cancellation rate by considering offering special packages or deals specifically for bookings with high lead time.  This can make customers change their minds and encourage them to proceed with their booking.
