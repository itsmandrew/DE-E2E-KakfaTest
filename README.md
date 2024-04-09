# Realtime Data Streaming | Date Engineering Project

## Introduction

This project covered each stage from data ingestiong to processing and finally to storage, utilizing a tech stack that includes Apache Airflow for data orchestration, Python as the main programming language, 
Apache Kafka and Zookeeper used for streaming data and cluster management, Spark for data processing with its master and worker nodes, and lastly Cassandra for where the processed data will be stored.

## System Architecture
![System Architecture](https://github.com/itsmandrew/DE-E2E-KakfaTest/blob/main/architecture.png)

## Components Overview

### Data Source

- **Description**: Utilizes the `randomuser.me` API to generate and fetch random user data, simulating real-world data input.
- **Role**: Acts as the entry point for the data pipeline, providing raw data for processing.

### Apache Airflow

- **Description**: Manages the orchestration of the data pipeline, ensuring tasks are executed in sequence and data flows smoothly through the pipeline.
- **Role**: Responsible for initiating data fetches, storing data in PostgreSQL, and overseeing the data's movement into the Kafka stream.

### Apache Kafka & Zookeeper

- **Description**: Kafka handles the streaming of data, acting as a buffer and messaging system, while Zookeeper manages Kafka's cluster coordination.
- **Role**: Ensures efficient and reliable data transfer from the PostgreSQL database to the Spark processing engine.

### Apache Spark

- **Description**: Processes the data streamed by Kafka, performing analytical computations and data transformations.
- **Role**: The core processing unit of the pipeline, transforming raw data into actionable insights or processed data for storage.

### Cassandra

- **Description**: A highly scalable NoSQL database that stores the processed data, optimized for high-speed read and write operations.
- **Role**: Serves as the final storage destination for processed data, making it available for querying and analysis.

### Docker

- **Description**: Containerization platform used to encapsulate each component of the pipeline, ensuring consistent environments and easy scalability.
- **Role**: Simplifies the deployment and management of the pipeline components, making the setup portable and easier to replicate across different environments.


## Getting Started

To set up the pipeline, follow these steps:

### Prerequisites

- Docker
- Docker Compose

### Installation

1. Clone the project repository:

   ```bash
   git clone https://github.com/<your-username>/<your-repository>.git
   cd <your-repository>
   ```

2. Create a Python virtual environment
   ```bash
   python3.10 -m venv <env_name>
   ```
   Keep in mind. Airflow might not work Python versions 3.9 and below.

3. Build/launch the Docker containers
   ```bash
   docker compose up (-d)
   ```
   -d to run in detached mode

## Usage
Once the pipeline is up and running, you can access and interact with each component:

- **Airflow Web Interface**: Monitor and manage the workflow at http://localhost:8080
- **Kafka Control Center**: View streams and topics at http://localhost:9021
- **Cassandra**: Use cqlsh or a similar tool to query and interact with the stored data.

