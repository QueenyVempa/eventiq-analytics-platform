# EventIQ: Real-Time Event Analytics Platform

A scalable, cloud-native data engineering platform that ingests, processes, and analyzes real-time event data using modern distributed systems.

## Overview

This project leverages the Ticketmaster API to build an end-to-end **event analytics pipeline** that collects, processes, and visualizes data about live events (concerts, sports, etc.) across cities.

The platform combines **real-time streaming** with **batch processing** to generate insights such as event trends, category distribution, and pricing opportunities.

## Architecture

```id="arch_event"
Ticketmaster API → Kafka → Spark Streaming → Data Lake (GCS)
                                          ↓
                                     Airflow
                                          ↓
                                        dbt
                                          ↓
                                   BigQuery (Warehouse)
                                          ↓
                                   Dashboard / Insights
```

## Workflow

1. Event data is fetched from Ticketmaster API
2. Data is streamed into Kafka topics
3. Spark Streaming processes and cleans the data
4. Processed data is stored in Google Cloud Storage
5. Airflow orchestrates batch workflows
6. dbt transforms raw data into analytical models
7. Data is loaded into BigQuery for querying
8. Dashboards provide insights on events and trends

## Tech Stack

* **Language:** Python
* **Streaming:** Apache Kafka
* **Processing:** Apache Spark (PySpark)
* **Orchestration:** Apache Airflow
* **Transformation:** dbt
* **Cloud:** Google Cloud Platform
* **Data Lake:** Google Cloud Storage
* **Data Warehouse:** BigQuery
* **Infrastructure:** Terraform
* **Containerization:** Docker

## Key Features

* Real-time event data ingestion and processing
* Hybrid pipeline (streaming + batch)
* Scalable cloud-based architecture
* Modular data transformation using dbt
* Automated workflow orchestration with Airflow
* Infrastructure as Code using Terraform
* Fully containerized deployment

## Use Cases

* Event trend analysis across cities
* Category-based insights (music, sports, etc.)
* Price comparison and deal identification
* Real-time event monitoring dashboards

## 🚀 Getting Started
### Setup infrastructure

```bash id="cmd_tf"
terraform init
terraform apply
```

### Run services

```bash id="cmd_docker"
docker-compose up --build
```

### Execute pipeline

* Start Kafka producers
* Run Spark streaming jobs
* Trigger Airflow DAGs

## Project Structure

```id="struct_event"
├── airflow/           # DAGs for orchestration
├── kafka/             # Event streaming setup
├── spark/             # Streaming jobs
├── dbt/               # Data transformation models
├── terraform/         # Cloud infrastructure
├── scripts/           # Data ingestion scripts
└── README.md
```

## Future Enhancements

* Incremental data ingestion
* Data quality checks (Great Expectations)
* Monitoring (Prometheus + Grafana)
* Multi-region cloud deployment
* Role-based access control

## Key Learnings

* Building scalable real-time data pipelines
* Integrating streaming and batch architectures
* Working with cloud-native data platforms
* Implementing Infrastructure as Code
* Designing analytical data models

## Support

If you found this project useful, consider giving it a star
