# Hotel Performance Analysis

## Work Environment

**Tool** : Jupyter Notebook \
**Programming Language** : Python 3 \
**Visualization** : Matplotlib, Seaborn \
**Dataset** : [Hotel Booking Data](https://github.com/dinachoir/hotel-performance/blob/main/hotel_bookings_data.csv) 

## Objectives
A company must analyze its business performance periodically. In this project, I explored the business in the hospitality industry. The aim is to find out how the customers behave in making hotel bookings and their relationship to the cancellation rate of hotel bookings. The results of the insights that I find are presented in the form of visualization data to make it easier to understand and more persuasive.

## Data Preprocessing
1. **Data summary checking**. The dataset contains 119,390 unique customers with 29 features in various data type float64(4), int64(16), object(9). Each row represent customers' demographics, booking details, and previous booking records. There are missing values in 4 columns, and 1 misdefined data type.
<p align="center">
  <img width="560" img width="243" alt="summary" src="https://user-images.githubusercontent.com/98371569/199071939-d938fac6-3c4d-4e5d-b2c5-bdf8ff04a103.PNG">
  <br style="font-size:5px"> Figure 1. Data Summary </br>
</p>

2. **Change data type** of `agent` into object. 

3. **Missing values handling**. There are missing values in `company` (94.3%), `agent` (13.68%), city (0.41%) and `children` (0.003%) columns. Drop `company` since the majority of the values are null. Fill missing values in `agent` with “No Agent”, missing values in `children` with 0 and missing values in `city` with Mode.

4. **Invalid values handling**. 
    * Replace “Undefined” values in `meal` with “No Meal”. 
    * Replace “Undefined” values in `market_segment` and `distribution_channel` with Mode. 
    * Replace value “53” in `arrival_date_week_number` with “52” because there are only 52 weeks in a year. 
    * Delete row data with negative values and 5,400 in `ADR` because it is possibly a data entry error.
    
5. **Exclude unnecessary data**. Exclude row data with 0 value in `adults`, because most of hotels in Indonesia won’t permit anybody younger than 18 to stay in a hotel room unaccompanied.

## Analysis
**1. Monthly Hotel Booking Analysis Based on Hotel** 

   * **The average monthly booking of City Hotel is volatile** compared to Resort Hotel, which is relatively steady in the range of 1,065 to 1,774. 
   * **City Hotel** bookings **increased during the early dry season (May – July)** as this is the best time to travel, which coincides with the school holiday period in June – July. 
   * Another **peak season for City Hotel** is from **Nov – Dec** due to the **year-end holiday**. The number of bookings is increasing significantly in November for the December stay plan. 
   * The **low season for both City and Resort Hotel** occurs from **January – March** and might be influenced by the weather and season in that period. The weather often rains heavily, so people may not be free to travel in unfavorable weather.
<p align="center">
  <img width="560" img width="243" alt="summary" src="https://user-images.githubusercontent.com/98371569/199870560-306bb2be-702f-44b5-aab4-139e6db7b76e.png">
  <br style="font-size:5px"> Figure 2. Average Monthly Booking </br>
</p>

  
  
**2. Impact Analysis of Stay Duration on Hotel Bookings Cancellation Rates** 

   * **City Hotel** rooms booked for **more than a week** have a higher chance of being **canceled**. 
   * In range stay duration of **7 days in City Hotel** bookings didn’t show a significant difference in cancellation rate, it’s around 41% on average.
   * Duration of stay 1 – 2 days in the **Resort Hotel** has the **lowest cancellation rate**, which is 20.8%. Meanwhile, the others are relatively constant at around 30%.
<p align="center">
  <img width="560" img width="243" alt="summary" src="https://user-images.githubusercontent.com/98371569/199871971-9394a44b-a45e-40a5-ada1-7304f1404403.png">
  <br style="font-size:5px"> Figure 3. Cancellation Rate by Stay Duration </br>
</p>


  
 
**3. Impact Analysis of Lead Time on on Hotel Bookings Cancellation Rates** 

   * **City and Resort Hotel** bookings with **longer lead times** have a higher chance of getting **canceled**. As the lead time increases, the customers have more time to change their plans and cancel the bookings. 
   * **Bookings with lead times of 0 – 19 days** have the **lowest cancellation rate** since it is **cheaper** to book a hotel room close to the arrival date. The customers may find this price a great deal, so they become **more committed** to their bookings. It aligns with the research by NerdWallet that room prices average 13% less when booked last minute (in 15 days) than booked 4 months in advance.
   * **City Hotel** bookings with lead time more than 4 months (or 160 days) are **more likely to be canceled**.
   * **The cancellation rate of City Hotel** is **higher** than Resort Hotel, possibly related to the average monthly bookings, which the City Hotel is **more in demand**.
<p align="center">
  <img width="560" img width="243" alt="summary" src="https://user-images.githubusercontent.com/98371569/199872394-8920f954-ebf5-469d-b63f-0fff593b65f3.png">
  <br style="font-size:5px"> Figure 3. Cancellation Rate by Lead Time </br>
</p>
