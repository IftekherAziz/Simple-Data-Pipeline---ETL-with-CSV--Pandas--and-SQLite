# 🎬 Simple Data Pipeline — ETL with CSV, Pandas, and SQLite

## 📘 Project Overview

This project was developed as part of the **Information Management and Systems Engineering** master’s course assignment.  
The main objective was to design and implement a simple yet complete **ETL (Extract, Transform, Load)** data pipeline using **Python**, **Pandas**, and **SQLite**.

The chosen dataset — **Netflix Movies and TV Shows** from Kaggle — is used to demonstrate how raw CSV data can be cleaned, transformed, and loaded into a relational database for analysis.  
Through this project, I gained hands-on experience with core **data engineering concepts**, **data transformation**, and **SQL querying**.

---

## ⚙️ Key Steps in the ETL Process

### 1️⃣ **Extract**

* The dataset (`netflix_titles.csv`) is imported from a CSV file using **Pandas**.
* This step represents the "Extract" stage of the ETL pipeline, where raw data is brought into the Python environment.

---

### 2️⃣ **Transform**

* Multiple data transformation steps were applied to clean and enhance the dataset:
  - Removing duplicates and missing values  
  - Dropping unnecessary columns (`rating`)  
  - Renaming columns for clarity (e.g., `listed_in → genre`)  
  - Adding new columns such as:
    - `content_length_type` — identifies if the title is a *Movie* or *TV Show*  
    - `semester_id = 'WS2025'` — a mandatory field for all records  
  - Filtering and aggregating data:
    - Number of titles added per year  
    - Movies with low ratings (<5.0)  
    - TV Shows with more than two seasons  

These transformations ensure that the dataset is consistent, structured, and ready for analysis.

---

### 3️⃣ **Load**

* The transformed dataset is stored in an **SQLite** database using Python’s built-in `sqlite3` module.
* Several SQL queries were executed to explore the data, including:
  - Verifying semester IDs  
  - Counting movies by release year  
  - Calculating average rating per genre  
  - Finding the latest release year for each content type  

This completes the final stage of the ETL process — loading data into a persistent, queryable database.

---

## 🧠 Data Analysis Examples

Once the dataset is loaded into the SQLite database, several SQL queries can be run for analysis.  
Examples include:

```sql
-- Verify dataset for WS2025 semester
SELECT show_id, title, type, release_year
FROM netflix_titles
WHERE semester_id = 'WS2025';

-- Average numeric rating per genre
SELECT genre, ROUND(AVG(rating_numeric), 2) AS avg_rating
FROM netflix_titles
GROUP BY genre
ORDER BY avg_rating DESC;

-- Latest release year per content type
SELECT type, MAX(release_year) AS latest_release_year
FROM netflix_titles
GROUP BY type;
````

These queries help validate the ETL pipeline and demonstrate how transformed data can be explored efficiently.

---

## 🛠️ Tools and Technologies

| Tool / Library                 | Purpose                                                   |
| ------------------------------ | --------------------------------------------------------- |
| **Python 3**                   | Programming language used for ETL scripting               |
| **Pandas**                     | Data extraction and transformation                        |
| **SQLite3**                    | Lightweight database engine for loading and querying data |
| **Jupyter Notebook / VS Code** | Development and visualization environment                 |

---

## 📂 Project Structure

```
ETL_Pipeline_Project/
│
├── data/
│   └── netflix_titles.csv                # Original dataset
│
├── notebooks/
│   └── etl_pipeline.ipynb                # Main Jupyter notebook (ETL process)
│
│
└── README.md                             # Project documentation
```

---

## 🚀 How to Run This Project Locally

### 1️⃣ **Clone or Download the Repository**

```bash
git clone https://github.com/<your-username>/ETL_Pipeline_Project.git
cd ETL_Pipeline_Project
```

---

### 2️⃣ **Set Up the Environment**

Install the required dependencies (Python ≥ 3.8):

```bash
pip install pandas
```

*(The `sqlite3` module is included with Python by default.)*

---

### 3️⃣ **Prepare the Dataset**

Ensure the CSV file `netflix_titles.csv` is placed in the `data/` directory.
You can download it directly from Kaggle:

🔗 [https://www.kaggle.com/datasets/shivamb/netflix-shows](https://www.kaggle.com/datasets/shivamb/netflix-shows)

---

### 4️⃣ **Run the ETL Notebook**

You can execute the entire ETL pipeline using **Jupyter Notebook**:

```bash
jupyter notebook notebooks/etl_pipeline.ipynb
```

or, to run as a Python script:

```bash
python notebooks/etl_pipeline.py
```

This will:

* Load the raw CSV file
* Perform all cleaning and transformation steps
* Save the results into `outputs/netflix_db.sqlite`

---

### 5️⃣ **Explore the Database**

After running the notebook, open the SQLite database file:

```bash
sqlite3 outputs/netflix_db.sqlite
```

Then run any SQL queries from the provided `queries.sql` file or explore it using a GUI tool such as **DB Browser for SQLite**.

---

## 🎯 Learning Outcomes

Through this project, I learned how to:

* Implement an **end-to-end ETL pipeline** using Python and Pandas
* Clean and transform data efficiently for database use
* Integrate Python with an **SQLite database**
* Write SQL queries for validation and analysis
* Combine scripting, data management, and analytical reasoning in a cohesive workflow

---

## 💡 Future Improvements

If extended, I would add:

* Automated data validation and error logging
* Visualization dashboards (e.g., in Power BI or Matplotlib)
* Incremental data updates instead of full reloads
* Unit tests to validate transformations automatically

---

## 🏁 Conclusion

This assignment provided a strong foundation in the **ETL process** — from extracting data and transforming it into meaningful form to loading it into a database for analysis.
It demonstrates how **Python, Pandas, and SQLite** work together to form a simple but powerful data engineering pipeline.
