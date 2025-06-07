# Travel Recommendation Engine

An advanced data pipeline project that uses **PostgreSQL**, **Apache Airflow**, **Kafka**, and **Power BI** to analyze and recommend travel destinations based on user preferences and travel data.

---

## Overview

This project demonstrates a modern data pipeline architecture for ingesting, processing, and visualizing travel data. It includes:
- **Data Streaming**: Kafka producer simulating real-time travel data.
- **ETL Orchestration**: Apache Airflow orchestrating batch and streaming workflows.
- **Data Warehouse**: PostgreSQL with advanced SQL features like window functions, partitioning, and materialized views.
- **Visualization**: Power BI or Tableau dashboards showing travel insights and recommendations.

---

## Tools Used

- **PostgreSQL**: Advanced SQL with window functions, partitioning, and caching.
- **Apache Kafka**: Real-time data streaming simulation.
- **Apache Airflow**: Orchestration of ETL pipelines.
- **Docker Compose**: Containerized local environment for all services.
- **pgAdmin**: PostgreSQL administration and query management.
- **Power BI / Tableau**: Data visualization dashboards.

---

## Architecture
       +-----------------+
       |    Kafka        |
       |  (Producer)     |
       +--------+--------+
                |
                v
        +-------+-------+
        |    Airflow    |
        |  (ETL DAGs)   |
        +-------+-------+
                |
                v
        +-------+-------+
        |  PostgreSQL   |
        |(Data Warehouse)|
        +-------+-------+
                |
                v
        +-------+-------+
        | Power BI /   |
        | Tableau      |
        +---------------+

---

## Quickstart

More to come

---

## Project Structure
travel-recommendation-engine/
│
├── dags/ # Airflow DAGs
│
├── docker/ # Docker Compose files
│ └── docker-compose.yml
│
├── data/ # Sample travel data
│
├── sql/ # SQL scripts (schema, views)
│ └── create_schema.sql
│
├── notebooks/ # (Optional) Data exploration notebooks
│
├── requirements.txt # Python dependencies
│
├── README.md # Project overview
│
└── .gitignore # Ignored files and folders

