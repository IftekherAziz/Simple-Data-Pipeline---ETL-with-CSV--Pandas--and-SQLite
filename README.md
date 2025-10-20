# Simple Data Pipeline - ETL with CSV, Pandas, and SQLite


## 📘 Project Overview

This project was developed as part of the **Information Management and Systems Engineering** master’s course assignment.
The main objective is to design and implement a basic **ETL (Extract, Transform, Load)** data pipeline using **Python**, **Pandas**, and **SQLite**.

Through this project, I learned how to extract raw data from a CSV file, transform it using Pandas functions, and load it into an SQLite database for storage and analysis. It provided hands-on experience with essential **data engineering concepts** and tools commonly used in real-world data workflows.

----

## ⚙️ Key Steps in the ETL Process

### 1. **Extract**

* The dataset is imported from a **CSV file** using the Pandas library.
* This step demonstrates how raw data can be brought into a Python environment for further processing.

### 2. **Transform**

* Various **data transformation techniques** are applied using Pandas.
* Common operations include:

  * Handling missing or duplicate values
  * Cleaning and formatting data
  * Renaming columns for consistency
  * Aggregating or filtering data
  * Creating new calculated variables

This step ensures the dataset is clean, structured, and ready for analysis.

### 3. **Load**

* The transformed dataset is loaded into an **SQLite database** using Python’s `sqlite3` module.
* This stage represents the final part of the ETL pipeline, where processed data is stored in a relational database for querying and long-term use.

---

## 🧠 Data Analysis

Once the data is successfully loaded into SQLite, several **SQL queries** are executed to:

* Retrieve and explore specific information from the database
* Perform aggregations (e.g., `GROUP BY`, `AVG`, `SUM`)
* Validate the transformations and check data integrity

These queries demonstrate how the transformed data can be effectively analyzed using SQL.

---

## 🛠️ Tools and Technologies

* **Python 3**
* **Pandas** – for data extraction and transformation
* **SQLite** – for database storage and SQL queries
* **Jupyter Notebook / VS Code / PyCharm** – for writing and running the code

---

## 🎯 Learning Outcomes

This assignment helped me to:

* Understand the **ETL process** and its importance in data management systems
* Gain practical experience in **data cleaning and transformation** using Pandas
* Learn how to integrate **Python** with **SQLite databases**
* Strengthen my ability to write and execute **SQL queries** for data analysis

---

## 📂 Project Structure

```
ETL_Pipeline_Project/
│
├── data/
│   └── netflix_titles.csv          # Input dataset
│
├── etl_pipeline.py              # Main Python script for ETL process
│
├── transformed_data.db          # SQLite database containing transformed data
│
├── queries.sql                  # SQL queries for data analysis
│
└── README.md                    # Project documentation
```

---

## 🚀 How to Run the Project

1. Clone or download this project folder.
2. Install the required libraries:

   ```bash
   pip install pandas sqlite3
   ```
3. Run the ETL Python script:

   ```bash
   python etl_pipeline.py
   ```
4. Open the SQLite database (`transformed_data.db`) using any SQLite viewer or run the provided SQL queries to explore the data.

---

## 💡 Conclusion

This assignment provided a practical understanding of how data flows through an ETL pipeline — from extraction and transformation to storage and querying.
By completing this project as part of the **Information Management and Systems Engineering** master’s program, I gained valuable experience in **data engineering, database management, and analytical thinking**, which are essential skills for managing modern information systems.

