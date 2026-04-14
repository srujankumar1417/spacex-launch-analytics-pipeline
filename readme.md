# 🚀 SpaceX Launch Analytics Pipeline

A local data engineering project that builds an end-to-end **Bronze → Silver → Gold** pipeline using SpaceX API data. The project ingests raw launch data, transforms it into clean analytical datasets, and publishes business-ready summary tables using **Python, Pandas, DuckDB, and Jupyter Notebooks**.

---

## 📌 Project Overview

This project demonstrates a modern medallion architecture on a local machine using real-world SpaceX launch data. It covers:

* API data ingestion
* Raw data storage (Bronze)
* Data cleaning & transformation (Silver)
* Analytical marts (Gold)
* SQL-based reporting in notebooks

The final outputs help answer questions such as:

* How many launches happened each year?
* Which rockets were used most frequently?
* What are the mission success trends?
* Which launchpads are most active?

---

## 🏗️ Architecture

```text
SpaceX API / JSON Sources
        ↓
Bronze Layer (Raw JSON)
        ↓
Silver Layer (Clean Parquet Tables)
        ↓
Gold Layer (Analytics Tables)
        ↓
Jupyter Notebook Reports
```

---

## 🛠️ Tech Stack

| Tool             | Purpose                   |
| ---------------- | ------------------------- |
| Python           | Pipeline scripting        |
| Pandas           | Data transformation       |
| DuckDB           | SQL analytics engine      |
| Jupyter Notebook | Development & reporting   |
| JSON             | Raw Bronze storage        |
| Parquet          | Silver analytical storage |

---

## 📂 Project Structure

```text
SPACEX_pipeline/
└── DATA/
    ├── BRONZE/
    │   ├── DATA_FETCHING.ipynb
    │   ├── launches.json
    │   ├── launchpads.json
    │   └── rockets.json
    ├── SILVER/
    │   ├── launches.parquet
    │   ├── launchpads.parquet
    │   ├── rockets.parquet
    │   └── TRANFORMATION.ipynb
    └── GOLD/
        └── GOLD_LAYER.ipynb
```

---

## 🥉 Bronze Layer

Raw API data is stored exactly as received from the source.

### Files

* `launches.json`
* `rockets.json`
* `launchpads.json`

### Notebook

* `DATA_FETCHING.ipynb`

### Key Tasks

* Fetch data from API / source files
* Validate response structure
* Preserve source truth for reprocessing

---

## 🥈 Silver Layer

The Silver layer converts raw JSON into structured datasets.

### Outputs

* `launches.parquet`
* `rockets.parquet`
* `launchpads.parquet`

### Notebook

* `TRANFORMATION.ipynb`

### Key Tasks

* Flatten nested fields
* Rename columns to snake_case
* Cast dates and numeric types
* Remove duplicates
* Apply quality checks
* Prepare relational datasets

---

## 🥇 Gold Layer

The Gold layer contains business-ready reporting tables built with DuckDB SQL.

### Notebook

* `GOLD_LAYER.ipynb`

### Example Analytical Tables

#### `gold_launch_summary_by_year`

* launch_year
* total_launches
* successful_launches
* failed_launches
* upcoming_launches
* success_rate_pct

#### `gold_rocket_usage`

* rocket_name
* rocket_type
* total_launches
* successful_launches
* success_rate_pct
* avg_launches_per_year

#### `gold_launchpad_activity`

* launchpad_name
* region
* total_launches
* successful_launches
* launchpad_success_rate_pct

---

## 📈 Sample Insights

* Falcon 9 is the most frequently used rocket.
* Launch volume increased significantly in recent years.
* Success rates improved over time.
* Certain launchpads handle the majority of missions.

---

## ▶️ How to Run

1. Open `DATA_FETCHING.ipynb` and run ingestion cells.
2. Open `TRANFORMATION.ipynb` and generate Silver parquet files.
3. Open `GOLD_LAYER.ipynb` and execute Gold SQL queries.
4. Review final tables and insights.

---

## 🎯 Skills Demonstrated

* Data ingestion from APIs / raw files
* ETL pipeline design
* Medallion architecture
* Data cleaning & validation
* SQL analytics with DuckDB
* Parquet-based storage
* Notebook reporting
* Business KPI modeling

---

## 🚀 Future Improvements

* Add automated scheduling with Airflow / cron
* Incremental loading for new launches
* Build Streamlit dashboard
* Add unit tests for transformations
* Containerize with Docker
* Deploy to cloud storage / warehouse

---

## 📄 Resume Summary

Built a local data engineering pipeline using Python, Pandas, DuckDB, and Jupyter to ingest SpaceX launch data into Bronze, transform validated Silver datasets, and publish Gold analytics marts for launch trends, rocket usage, and mission performance.
