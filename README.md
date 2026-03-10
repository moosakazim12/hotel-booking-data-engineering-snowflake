# hotel-booking-data-engineering-snowflake
❄️ This project demonstrates an end-to-end data engineering pipeline built entirely within the Snowflake Data Cloud. It transforms raw, inconsistent hotel booking data into a clean, actionable analytics dashboard without the need for external ETL tools or Python.

📂 Dataset Description
The dataset used in this project consists of hotel booking records containing raw, unformatted information. It includes a mix of categorical, numerical, and date-based data that required significant cleaning to be useful for analysis.

Column,Description,Data Type (Raw)
BOOKING_ID,Unique identifier for each hotel reservation.,VARCHAR
HOTEL_ID,Unique identifier for the hotel property.,VARCHAR
HOTEL_CITY,The city where the hotel is located (required cleaning).,VARCHAR
CUSTOMER_ID,Unique identifier for the guest.,VARCHAR
CUSTOMER_NAME,Full name of the guest (included extra spaces).,VARCHAR
CUSTOMER_EMAIL,Email address (contained invalid formats and nulls).,VARCHAR
CHECK_IN_DATE,The date the guest was scheduled to arrive.,VARCHAR
CHECK_OUT_DATE,The date the guest was scheduled to depart.,VARCHAR
ROOM_TYPE,"Category of the room (Standard, Deluxe, Suite).",VARCHAR
NUMBER_OF_GUESTS,Total number of people included in the booking.,VARCHAR
TOTAL_AMOUNT,The price paid (contained negative values as errors).,VARCHAR
CURRENCY,"The currency used for the transaction (USD, INR, EUR).",VARCHAR
BOOKING_STATUS,"Status of the booking (Confirmed, Cancelled, No Show).",VARCHAR

🏗️ Architecture: Medallion Framework
The project follows the industry-standard Medallion Architecture to ensure data quality:

1) Bronze (Raw): Ingestion of raw CSV data from Snowflake Stages using custom File Formats. Data is kept in its original state to maintain a "source of truth."

2) Silver (Cleaned): Application of data quality rules using Snowflake SQL.

Standardized text formatting (Initcap/Trim).

Handled null values and invalid email formats.

Fixed data anomalies (e.g., negative revenue values and logical date errors where checkout preceded check-in).

3) Gold (Curated): Business-level aggregates optimized for reporting. Tables are structured to provide insights into monthly revenue trends, city performance, and booking status distribution.

🛠️ Tech Stack & Features
Platform: Snowflake

Language: Snowflake SQL

Data Loading: Internal Stages & COPY INTO commands.

Data Transformation: Complex SQL transformations, Case logic, and Aggregate functions.

📊 Analytics Dashboard (Snowsight):

Key Performance Indicators (Total Revenue, Total Bookings, Average Booking Value).

Monthly Booking & Revenue Trends.

Top 5 Revenue-Generating Cities.

Booking Analysis by Room Type and Status.

🚀 Key Insights
By utilizing a Snowflake-native approach, this project achieves a simplified architecture that reduces data movement and lowers cost-to-serve by keeping all processing within the cloud data warehouse.

👤 Author

Gulam Kazim Master’s in Computational Science Data Engineer | Data Analyst

LinkedIn: https://www.linkedin.com/in/gmmk-5bba5125b
