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
    
