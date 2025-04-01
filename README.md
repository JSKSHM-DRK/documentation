# Kafka with FastAPI - Comprehensive Documentation

## Overview
The **Kafka-Python with FastAPI** repository provides a structured implementation of Kafka producers and consumers within a FastAPI application. This project serves as a foundation for integrating real-time messaging and event-driven architecture using **Apache Kafka, Python, and FastAPI**.

## Table of Contents
- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Installation Guide](#installation-guide)
- [Configuration](#configuration)
- [Usage Instructions](#usage-instructions)
- [API Endpoints](#api-endpoints)
- [Features & Benefits](#features--benefits)
- [Troubleshooting & FAQs](#troubleshooting--faqs)
- [References & Additional Resources](#references--additional-resources)

---

## Introduction
Kafka is a **distributed event streaming platform** capable of handling high-throughput, real-time data streams. This project demonstrates how to use **Kafka-Python** to set up a Kafka producer and consumer with **FastAPI**, making it suitable for applications requiring **real-time communication and data processing**.

### Key Technologies Used:
- **Apache Kafka**
- **Python 3.10+**
- **FastAPI**
- **Docker & Docker Compose**
- **Kafka-Python**
- **uv (dependency management)**

---

## Prerequisites
Before setting up and running this project, ensure that you have the following installed:

- **Python 3.10 or higher** → [Download Here](https://www.python.org/downloads/)
- **Docker & Docker Compose** → [Get Docker](https://www.docker.com/get-started)
- **uv Package Manager** → Install via:
  ```
  pip install uv
  ```
---

## Installation Guide
### Step 1: Clone the Repository
- Run the following command in your terminal:
```
git clone https://github.com/sumituiet/kafka_python.git
```
- Navigate to the project directory:
```
cd kafka_python
```
### Step 2: Setup Kafka Using Docker
- Start Kafka and Zookeeper services using Docker Compose:
```
docker-compose up -d
```
This will initialize and run Kafka, Zookeeper, and related dependencies in the background.

### Step 3: Setup Python Virtual Environment & Install Dependencies
- Create a virtual environment:
```uv venv```

- Activate and install required packages:
``` uv install ```

This installs all dependencies defined in ```pyproject.toml. ```

### Step 4: Run FastAPI Application
- Start the FastAPI application with:
``` fastapi dev app.py ```
The API will be available at http://127.0.0.1:8000.

## Configuration
### Modify config.py to adjust Kafka connection settings such as:
- Kafka Broker URL
- Topic Names
- Consumer Group ID
Example Kafka settings in ```config.py:```
```
KAFKA_BROKER_URL = "localhost:9092"
KAFKA_TOPIC = "sample_topic"
CONSUMER_GROUP_ID = "sample_group"
```
---

## Usage Instructions
- Running the Kafka Producer
- The Kafka producer is responsible for sending messages to the Kafka topic.
```python producer.py ```
- Running the Kafka Consumer
The Kafka consumer listens for messages from the specified topic.
```python consumer.py```

---

## API Endpoints:
| **Method** | **Endpoint**   | **Description**                      |
|-----------|---------------|--------------------------------------|
| **GET**   | `/health`      | Check API health status            |
| **POST**  | `/produce`     | Publish a message to Kafka         |
| **GET**   | `/consume`     | Fetch messages from Kafka          |

---

## Features & Benefits
- **afka Integration with FastAPI** → Enables event-driven architecture and real-time message processing.
- **Scalability** → Kafka allows high throughput and fault tolerance.
- **Dockerized Deployment** → Easy setup and portability.
- **API-Driven Approach** → RESTful endpoints for seamless communication.
- **Interactive API Docs** → Explore, test, and debug APIs easily.

---

## Troubleshooting & FAQs
### Kafka Connection Issues
If the consumer or producer fails to connect, verify:
- Kafka and Zookeeper are running ```docker ps```
- Correct Kafka broker address in ```config.py```
- Network connectivity between producer and consumer

### Docker Issues
If services fail to start, try:
```docker-compose down && docker-compose up --build ```

### Dependency Issues
Reinstall dependencies: 
```uv install --force ```

---

## References & Additional Resources
- [Kafka Documentation](https://kafka.apache.org/documentation/)
- [FastAPI Documentation](https://fastapi.tiangolo.com/)
- [Kafka-Python Library](https://kafka-python.readthedocs.io/)













