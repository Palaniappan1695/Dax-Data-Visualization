📊 E-Commerce Sales Analysis

Power BI | DAX & Data Visualization

Turning sales data into meaningful business insights

📌 Project Overview

This project focuses on analyzing an E-Commerce Sales Dataset using Microsoft Power BI. Building on the data model created in the previous assignment, this project applies Data Analysis Expressions (DAX) to create calculated columns and measures.

The report aims to explore sales trends, profitability, category performance, geographic sales patterns, and actual sales compared with targets through interactive visualizations.

🎯 Project Objectives

Create calculated columns to derive useful attributes from order data.

Develop DAX measures for order count, average profit, and year-to-date sales.

Compare actual sales with targets across categories and months.

Analyze sales and profit patterns across sub-categories and locations.

Present the analysis through clear and well-formatted Power BI visuals.

🗂️ Dataset Description

The assignment uses three tables:

Dataset

Key Attributes

Purpose

List of Orders

Order ID, Order Date, Customer Name, City, State, Category, Amount, Profit

Order-level sales and geographic analysis

Order Details

Order ID, Category, Sub-Category, Quantity, Amount, Profit

Product category and profitability analysis

Sales Target

Category, Month of Order Date, Target

Target comparison by category and month

The data model and relationships are carried forward from Assignment 1 and should be validated before final analysis.

🧮 DAX Calculations

1. Calculated Columns

The assignment requires three calculated columns in the Order Details table.

Category Type — combines Category and Sub-Category.

Category Type =
'Order Details'[Category]
    & " - "
    & 'Order Details'[Sub-Category]

Revenue per Order — calculates Amount multiplied by Quantity, as specified in the assignment.

Revenue per Order =
'Order Details'[Amount]
    * 'Order Details'[Quantity]

Sales Category — classifies Amount as Above Average or Below Average.

Sales Category =
IF(
    'Order Details'[Amount]
        > AVERAGE('Order Details'[Amount]),
    "Above Average",
    "Below Average"
)

2. DAX Measures

Order Count

Order Count =
COUNT('Order Details'[Order ID])

Average Profit in Delhi

Average Profit in Delhi =
CALCULATE(
    AVERAGE('List of orders'[Profit]),
    'List of orders'[City] = "Delhi"
)

Year-to-Date (YTD) Sales

YTD Sales =
TOTALYTD(
    SUM('List of orders'[Amount]),
    'List of orders'[Order Date]
)

📈 Data Visualizations

The report is expected to include the following nine visualizations:

#

Visualization

Chart Type

Business Purpose

1

Sales Target Achievement by Category

Clustered Column Chart

Compare actual sales against targets

2

Max Profit Margin by Sub-Category

Donut Chart

Analyze maximum profit margin by sub-category

3

Monthly Sales Trend

Line Chart

Explore sales trends over time

4

Profit and Quantity by Sub-Category

Scatter Chart

Compare profit with quantity sold

5

Total Sales Amount and Target

Cards and Multi-row Card

Display sales, targets, and minimum target by segment

6

Sales Performance Matrix

Matrix

Compare actual sales and targets by category and month

7

Geographic Sales Analysis

Map

Visualize total sales by city

8

Sales Distribution by Sub-Category

Treemap

Compare sales contributions across sub-categories

9

Order Count Analysis by State

Funnel Chart

Compare order counts across states

🎓 Skills Demonstrated

DAX calculated columns and measures

Aggregations and filter context

Time-intelligence calculations

Sales and target performance analysis

Data visualization and visual storytelling

Dashboard formatting and data presentation

Business-oriented analytical thinking
