# Bike-Sharing Service Analysis and Visualization
by Jongseob Shin

## 1. About Bike-Sharing Datasets
A bike-sharing service or bicycle-sharing system is a kind of public transportation system that users can pick up and drop off near the users' location when needed. Bike-sharing services are available in many big cities and more popular.
The Datasets are provided by the bike sharing service company and include information about individual rides made in a bike-sharing service covering the greater San Francisco Bay area, Los Angeles and Washington DC. Dataset has rides information in 2019.

### 1.1 The greater San Francisco Bay Area
In San Francisco Bay Area, the bike-sharing service is provided under the name of Bay Wheels, which name was changed from Ford GoBike at May 2019. The dataset contains approximately 2.5 million rides information in 2019. The source of data is lyft web site (https://www.lyft.com/bikes/bay-wheels/system-data) or you can download it from https://s3.amazonaws.com/baywheels-data/index.html

### 1.2 Los Angeles
Metro Bike Share System is available in Downtown LA, Central LA, and North Hollywood. Unlike the other two cities, the service began in 2017 and the number of bikes is also small. The dataset contains approximately 290,000 rides information in 2019 and it is available at https://bikeshare.metro.net/about/data/

### 1.3 Washington DC
In the Washington DC area, Capital Bikeshare service is available. The dataset contains approximately 3.4 million rides information and it can be download at https://www.capitalbikeshare.com/system-data

##### The zipped datasets are also available at https://github.com/js3414/Bike-Sharing.git

## 2. Dataset Structure
The datasets from three bike-share systems are different data structures.

### 2.1 Bay Wheels Datasets
There are approximately **2.5 million trips** in the dataset with **15 features**.

No|column|non-null|type|description
--|:-----|--------|:---|:----------
1|duration_sec|2,506,983|int64|duration of trip in seconds
2|start_time|2,506,983|object|start date and time
3|end_time|2,506,983|object|end date and time
4|start_station_id|2,426,249|float64|ID of start station
5|start_station_name|2,426,850|object|name of start station
6|start_station_latitude|2,506,983|float64|latitude of start station
7|start_station_longitude|2,506,983|float64|longitude of start station
8|end_station_id|2,424,081|float64|ID of end station
9|end_station_name|2,424,633|object|name of end station
10|end_station_latitude|2,506,983|float64|latitude of end station
11|end_station_longitude|2,506,983|float64|longigude of end station
12|bike_id|2,506,983|int64|ID of bike
13|user_type|2,506,983|object|Type of user, Subscriber (member) or Customer (temporary)
14|bike_share_for_all_trip|2,263,724|object|Yes or No.
15|rental_access_method|120,838|object|This feature found in June, July and November. The value is either app or clipper|

### 2.2 Metro Bike Share Datasets
There are approximately **290K trips* in the dataset with **15 features**.

No|column|non-null|type|description
--|:-----|--------|:---|:----------
1|trip_id|290,342|int64|ID of trip
2|duration|290,342|int64|length of trip in minutes
3|start_time|290,342|object|start date and time
4|end_time|290,342|object |end date and time
5|start_station|290,342|int64|start station ID
6|start_lat|285,505|float64|latitude of start station
7|start_lon|285,505|float64|longitude of start station
8|end_station|290,342|int64|end station ID
9|end_lat|279,757|float64|latitude of end station
10|end_lon|279,757|float64|longitude of end station
11|bike_id|290,342|object|ID of bike
12|plan_duration|290,342|int64|The number of days that the plan the passholder is using entitles them to ride; 0 is used for a single ride plan (Walk-up); 999 is used for testing purpose.
13|trip_route_category|290,342|object|Round Trip or One Way
14|passholder_type|290,342|object|The name of the passholder's plan
15|bike_type|290,342|object|The kind of bike used on the trip, including standard pedal-powered bikes, electric assist bikes, or smart bikes.

### 2.3 Capital Bikeshare Datasets
There are approximately **3.4 million trips** in the dataset with **9 features**.

No|column|non-null|type|description
--|:-----|--------|:---|:----------
1|Duration|3,398,417|int64|duration of trip in minute
2|Start date|3,398,417|object|start date and time
3|End date|3,398,417|object|end date and time
4|Start station number|3,398,417|int64|ID of start station 
5|Start station|3,398,417|object|start station location
6|End station number|3,398,417|int64|ID of end station
7|End station|3,398,417|object|end station location
8|Bike number|3,398,403|object|ID of bike
9|Member type|3,398,417|object|Indicates whether user was a "registered" member (Annual Member, 30-Day Member or Day Key Member) or a "casual" rider (Single Trip, 24-Hour Pass, 3-Day Pass or 5-Day Pass)

## 3. Questions

### 3.1 Demands
The number of rides means the demand for the bike share service. I have the following questions related to the demands.
- The relation between bike demand and time, day of the week, and user type
- What time is the most demands?
- What day of the week is the most demanding?
- What is the difference of pattern of demands by user type?

### 3.2 Trip Duration
I have the following questions for the trip duration.
- How long time do users use a bike?
- Are the trip duration on weekends and weekdays are similar?

### 3.3 Demands by User Types
There are two types of users: One is a subscriber or member and the other is a customer or casual user.
- What is the difference of demands between a subscriber and casual user?

## 4. Summary of Findings
#### The expectation at the begining of the analysis, the demands and trip duration pattern will be similar in each city. However, the actual data shows that the demands and trip duration are different from city to city. The reason why these patterns are different might be related with weather conditions and geographic features.

### 4.1 Demands Analysis Results
#### 1) Demands on Weekdays and On Weekends
- Generally, average demands on weekdays are higher than on weekends. 
- In San Francisco, average demands on weekdays are about **1.9 times higher than weekends**.
- In Los Angeles, the average demands are **21% more on weekdays**.
- In Washington DC, unlike the other two cities, **demands on Sat are similar to weekdays**.

#### 2) Demands by Months
- In San Francisco, December is the lowest demand month and the highest demand is in March.
- In Los Angeles, **demands from Nov and Dec are higher than Apr or May**. August is the highest demand, and February is the lowest.
- In Washington DC, the demands in Washington DC **increased as getting warmer and decrease as getting cold**.
***Further study and more data are needed to understand the demand pattern of the cities.***

#### 3) Demmands by Time
- The demand patterns by time of the three cities are similar. The pattern of bike demands is quite different between weekdays and weekends. 
- On **weekdays**, more demands on rush hours between **7 to 10 in the morning time** and **16 to 19 in the afternoon**.
- On **weekends**, the demands for bikes peaked in the **daytime between 12 to 16 in the afternoon**.

#### 4) Demands by Months and Day of the Week
- In San Francisco, the bike demands on weekdays are **higher** than on weekends **every month**.
- In **Los Angeles**, the demands on weekends are **similar to or higher than weekdays in Mar, Jun, Aug, and Sep**.
- In **Washington DC**, the demands on weekends are **similar to or higher than weekdays in Mar, Apr, Jun, Jul, Aug, and Sep**.

### 4.2 Trip Duration Analysis Results
#### 1) Trip Duration
- Bikes are used for travel of **short distances**:
- **75%** of total trips are less than or equal to **17 minutes**.
- **More than 90% of trips are less than 30 minutes.**
    
#### 2) Trip Duration on Weekdays and Weekends
- Overall, the average trip duration on weekends is longer than weekdays.
- For San Francisco:
    - The average trip durations on weekdays are between **11 and 14 minutes** regardless of months.
    - In the cold-weather season of Dec, Jan, and Feb, the average trip durations on weekends are about 14 to 16 minutes, which are lower than other months.
- For Los Angeles:
    - The average trip durations are longer than San Francisco and their values are mostly between **24 and 36 minutes**.
    - **On weekends**, the average trip durations are over **40 minutes from Jan to Aug**.
- For Washington DC:
    - The distribution of the average trip duration is between **12 and 19 minutes**.
    - On weekends, average trip durations are longer than weekdays like the other two cities from 17 to 27 minutes.
- The differences in the average trip duration of the cities require further study.

### 4.3 User Type Analysis Results
- The bike demands by user type are quite **different between San Francisco and the other two cities**. 
- In **San Francisco**, **the demands from subscribers drop on weekends** however, **the casual users' demands are steady** regardless of the day of the week.
- In **Los Angeles and Washington DC**, **casual users** use bike sharing services **more on weekends**. During the weekdays demands from casual users are steady and **increase on weekends**.

## 5. Further Study
Further studies are needed to find the following answers:
- Why demands patterns in the three cities are different, especially on weekends?
- Why the average trip duration in Los Angeles is longer than the other two cities?
