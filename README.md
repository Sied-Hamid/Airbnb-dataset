# Airbnb Booking Cleaning Analysis
![insight](/Image/insight.png)
## Project Overview

This project analyzes booking revenue from an Airbnb dataset using **Excel and Power Query**. The objective is to clean messy booking data, transform it into an analysis-ready dataset, and build an interactive dashboard to explore **revenue performance by city and guest**.

The workflow demonstrates practical data analytics skills including **data cleaning, transformation, aggregation, and dashboard development**.

---

## Tools Used

* **Microsoft Excel**
* **Power Query (Data Cleaning & Transformation)**
* **Excel Charts & Slicers (Dashboard Visualization)**

---

## Dataset Description

The dataset contains booking-level information including:

* `booking_id` – unique booking identifier
* `user_id` – unique user identifier
* `guest_name` – customer name
* `email` – guest email
* `listing_id` – property ID
* `listing_city` – property location
* `checkin_date` – booking start date
* `checkout_date` – booking end date
* `revenue` – total booking revenue
* `is_cancelled` – booking cancellation status

---

## Data Cleaning Process (Power Query)

Several data quality issues were identified and resolved:

### 1. Header Standardization

The dataset headers were promoted using:

`Table.PromoteHeaders(verbo_data_Sheet, [PromoteAllScalars=true])`

This ensured the first row became the column headers.

---

### 2. Handling Missing Values

Data profiling was used to identify:

* **Null values in guest names**
* **Missing emails**
* **Incomplete booking records**

These were handled by filtering invalid rows or keeping only valid records required for analysis.

---

### 3. Text Standardization

Some fields contained inconsistent formatting such as:

* `los angeles`
* `LA`
* `nyc`
* `San Fran`

These were standardized to consistent values such as:

* **Los Angeles**
* **New York**
* **San Francisco**

This step ensured accurate aggregation during analysis.

---

### 4. Cancellation Status Transformation

A calculated column was created to convert numeric cancellation values into readable labels:

```
if [is_cancelled] = 1 then "Yes"
else if [is_cancelled] = 0 then "No"
```

This improves interpretability in the dashboard.

---

### 5. Duplicate and Data Validation Checks

Power Query column profiling was used to verify:

* **Unique booking IDs**
* **Valid email records**
* **Distinct guest names**

Example result:

* `user_id`: 1000 distinct / 1000 unique
* `guest_name`: 983 distinct / 966 unique

This confirms realistic repeat customers rather than data duplication errors.

Data Cleaning Process (Excel & Power Query)
--
![Data cleaning Process](/Image/Applied_steps.png)

## Cleaned Dataset
![Data Cleaning process](/Image/cleaned_dataset.png)

## Summary Dataset
![Data Cleaning process](/Image/summary_dataset.png)

---

## Data Analysis

The cleaned dataset was used to calculate key metrics including:

* **Revenue by City**
* **Revenue by Guest**

---

## Dashboard Features

An interactive Excel dashboard was created with:

### 1. Top Revenue by City

A bar chart displaying the **top 10 revenue-generating cities**.

### 2. Top Revenue by Guest

A horizontal bar chart identifying **guests generating the highest revenue**.

### 3. Interactive Slicers

Dashboard filters include:

* **Guest Name**
* **Listing City**

These slicers allow users to dynamically explore revenue performance.

---

## Key Insights

* Major revenue contribution comes from **New York, Los Angeles, and San Francisco**.
* A small group of repeat guests generates a **large portion of total revenue**.
* Data standardization significantly improves the accuracy of location-based analysis.

---

## Project Structure

```
Airbnb-Revenue-Analysis
│
├── data
|  └── raw_booking_data.xlsx  
|  └── Cleaned dataset
|
├── images
│    └── Applied_steps.png 
|    └── cleaned_dataset.png 
|    └── insight.png 
|    └── summary_dataset.png
|
├── .gitignore
|
└── README.md
```

---

## Skills Demonstrated

* Data Cleaning with **Power Query**
* Handling **null values and inconsistent data**
* Data Transformation
* Excel Dashboard Development
* Interactive Data Visualization
