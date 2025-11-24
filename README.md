📊 Task 7 — Basic Sales Summary Using SQLite

A Data Analyst Internship Project

  


---

📌 Project Overview

This repository contains the solution for Task 7: Basic Sales Summary Using SQL, as described in the internship task PDF.

Objective:

Use a small SQLite database to calculate:

Total quantity sold

Total revenue

Summary per product

Visualize results using a bar chart


No Python was used — everything was done directly inside DB Browser for SQLite.


---

📁 Database

A new SQLite database file was created:

sales_data.db

Table Used: sales

Column Name	Type

product	TEXT
quantity	INTEGER
price	REAL
order_date	TEXT



---

🧩 Steps Performed

✔ 1. Created the SQLite database

Using DB Browser for SQLite → New Database → sales_data.db

✔ 2. Created the sales table

CREATE TABLE sales (
  id INTEGER PRIMARY KEY AUTOINCREMENT,
  product TEXT NOT NULL,
  quantity INTEGER NOT NULL,
  price REAL NOT NULL,
  order_date TEXT
);

✔ 3. Inserted sample sales records

INSERT INTO sales (product, quantity, price, order_date) VALUES
('Coffee', 10, 15.0, '2023-01-05'),
('Tea', 8, 12.0, '2023-01-06'),
('Juice', 5, 10.0, '2023-01-07'),
('Coffee', 7, 15.0, '2023-02-10'),
('Tea', 12, 12.0, '2023-02-11'),
('Coffee', 6, 15.0, '2023-03-03'),
('Juice', 10, 10.0, '2023-03-15');

✔ 4. Ran SQL queries to get the sales summary

Main query:

SELECT
  product,
  SUM(quantity) AS total_quantity,
  SUM(quantity * price) AS revenue
FROM sales
GROUP BY product
ORDER BY revenue DESC;

This query calculates total quantity and revenue per product.

✔ 5. Exported results

Exported the query results as sales_summary.csv


✔ 6. Created Bar Chart

Using the Plot tab inside DB Browser

X-axis → product

Y-axis → revenue

Chart type: Bar


Saved the chart as sales_chart.png.


---

📊 Output Summary (Example)

Product	Total Quantity	Revenue

Coffee	23	345
Tea	20	240
Juice	15	150
