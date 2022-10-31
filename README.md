# Hotel Performance Analysis

## Work Environment

**Tool** : Jupyter Notebook \
**Programming Language** : Python 3 \
**Visualization** : Matplotlib, Seaborn \
**Dataset** : [Hotel Booking Data]() 

## Objectives
A company must analyze its business performance periodically. In this project, I explored the business in the hospitality industry. The aim is to find out how the customers behave in making hotel bookings and their relationship to the cancellation rate of hotel bookings. The results of the insights that I find are presented in the form of visualization data to make it easier to understand and more persuasive.

## Data Preprocessing
1. **Data summary checking**. The dataset contains 119,390 unique customers with 29 features in various data type float64(4), int64(16), object(9). Each row represent customers' demographics, booking details, and previous booking records. There are missing values in 4 columns, and 1 misdefined data type.
<p align="center">
  <img width="243" alt="summary" src="https://user-images.githubusercontent.com/98371569/199071939-d938fac6-3c4d-4e5d-b2c5-bdf8ff04a103.PNG">
  <br style="font-size: 5px"> Figure 1. Data Summary </br>
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
