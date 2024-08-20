# **US Airplane Analysis FY 2019-2023**

## **Overview:**

The US domestic flight industry accounted for almost 3 million flights with over 3.3 billion passengers on board, reflecting its critical role in national transportation. With such a vast number of flights, the industry faces significant challenges, including managing delays, cancellations, and ensuring operational efficiency.

The purpose of this study was to analyze key operational metrics within this industry, focusing on flight performance, delay patterns, and cancellation trends. By examining these factors, the analysis aimed to uncover insights that could help improve operational efficiency, enhance passenger satisfaction, and reduce the frequency and impact of delays and cancellations.

## **Dataset:**

The data was taken from Kaggle. Link to the dataset: https://www.kaggle.com/datasets/patrickzel/flight-delay-and-cancellation-dataset-2019-2023/data?select=flights_sample_3m.csv

## **Tools Used:**

### **Jupyter Notebook & Pyspark:**

the dataset contained over 3 million rows and around 30 columns. To efficiently handle and process this large dataset, PySpark was utilized for data cleaning and preparation.

#### **Data Cleaning & Pre-Processing:**

* Null values in columns which counted delay in minutes due to respective reasons were replaced with 0, as it would mean no delay experienced.

* Arrival and departure time columns were converted to time format (hh:mm), which were earlier string type.

* Cancellation Code column were modified to explicitly represent the reason of cancellation.

* Null values in columns which recorded times like delay, taxi in/out etc were replaced with 0 for flights which were operated and were not cancelled. No changes were made to these columns for the flights cancelled, as it would not make sense.

* Null values in taxi in/out columns were replaced with average values at respective airports.

* Null values for elapsed times were replaced with average elapsed time for the respective flights by same airlines traversing on the same route.

* Arrival and departure delays were calculated as the difference between actual and expected times for the null values.

The resulting dataset was used for analysing different operational metrics on Power-BI.

### **Power BI:**

The cleaned dataset was loaded as csv into Power-BI.

#### **Power Query Editor:**

Power Query was utilied the break down the large single table of data into multiple tables. Joins were utilized to create relationship between the tables. Dates table was also created.

#### **Data Modeling:**

The large table of data was broken down into a Fact table and multiple Dim tables in order to create a STAR Schema. This structure makes it easier to navigate and understand data, supports efficient querying, and improves the speed of data retrieval by minimizing joins and optimizing data storage. 

#### **Dashboard Creation:**

Calculated columns and measures were created to represent differnt operational metrics.

Different visuals were utilized to view display the measures. Slicers were used to filter across different fields.

## **Insights:**

**1. Flight Performance Metrics:**

Detailed analysis of on-time performance, average delays, and punctuality across different airlines and routes. This would helps airlines and airport authorities identify bottlenecks, improve scheduling, and enhance overall operational efficiency.

**2. Cancellation Trends:**

Analysis of cancellation rates, reasons for cancellations, frequency across months, and their distribution across airlines and routes. Enables airlines mitigate factors leading to cancellations, plan contingency strategies, and minimize operational disruptions. Aid airlines to address the root causes of cancellations and delays, optimize flight schedules, and improve customer satisfaction.

**3. Seasonal and Temporal Trends:**

Identification of seasonal variations in flight delays and cancellations, and analysis of peak travel times. Aids in capacity planning, resource management, and optimizing staffing levels during peak periods.

**4. Airline Comparison:**

Comparative performance of different airlines in terms of delays, cancellations, and overall service quality. Assists passengers in making informed choices and allows airlines to benchmark their performance against competitors, driving service improvements.










