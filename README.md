# 📊 Global Tech Sales Performance Dashboard

## 🎯 Project Overview
This project features a comprehensive Power BI dashboard designed to track and analyze sales performance across multiple regions and product categories from 2024 to 2026. The goal of this analysis is to identify top-performing products, understand category distribution, and visualize sales trends over time.

## 🛠️ Data Preparation & Cleaning
The raw data was sourced from two primary datasets:
* `customers.csv`: Contains customer demographic and scoring information.
* `orders.csv`: Contains transactional data, product details, and sales figures.

**Data Cleaning Highlights:**
* Handled missing data: All null values were successfully identified and filled during the Extract, Transform, Load (ETL) process in Power Query to ensure accurate aggregations and reporting.

## 🗄️ Data Model
The project utilizes a standard Star Schema data model. 
* A **One-to-Many (1:*) relationship** was established between the `customers` dimension table and the `orders` fact table using the `customer_id` key.

![Data Model](image_9f79f7.png)

## 📸 Dashboard Preview
![Sales Dashboard Overview](Screenshot%202026-06-29%20103945.png)
