# Realtime Data Streaming | Date Engineering Project

## Introduction

This project covered each stage from data ingestiong to processing and finally to storage, utilizing a tech stack that includes Apache Airflow for data orchestration, Python as the main programming language, 
Apache Kafka and Zookeeper used for streaming data and cluster management, Spark for data processing with its master and worker nodes, and lastly Cassandra for where the processed data will be stored.

## System Architecture
(https://github.com/itsmandrew/DE-E2E-KakfaTest/blob/main/architecture.png)

The project is desgined with the following components:
- **Data Source**: We use `randomuser.me` API to generate random user data for our pipeline.
- **Apache Airflow**: Responsible for orchestrating the pipeline and storing fetched data in a PostgreSQL database.
- **Apache Kafka and Zookeeper**: Used for streaming data from PostgreSQL to the processing engine.
- **Apache Spark**: For data processing with its master and worker nodes.
- **Cassandra**: Where the processed data will be stored.
- **Docker**: How the entire project is setup.
