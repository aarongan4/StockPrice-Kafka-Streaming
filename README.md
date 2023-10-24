# Tesla Stock Price Real-Time Data Streaming Project

Inspired by this [video]([https://www.youtube.com/watch?v=q8q3OFFfY6c&t=994s](https://www.youtube.com/watch?v=KerNf0NANMo)). Thanks to the creator!

## Table of Contents

- [Description](#description)
- [Prerequisites](#prerequisites)
- [Execution](#execution)

## Description

This project is a real-time data streaming process that ingests stock prices for tick $TSLA, transforms each new events as a json file and upoads each file to an AWS S3 bucket. It utilizes Python ingest the data, Apache Kakfa on an EC2 Amazon Linux instance for orchestration, and various other tools and services.

## Prerequisites

Before you get started, ensure you have the following prerequisites in place:

1. **Stock Price Data/Stock Market API**: You'll need some kind of stock price data whether from a Kaggle dataset or a third-party site.

2. **AWS Account**: Configure an AWS account and create a IAM User access key to access AWS on your local machine

## Execution

1. **Configure and Launch EC2 Instance - Amazon Linux:**

   - Log in to your AWS Management Console.
   - Launch a new EC2 instance using Amazon Linux.
   - Configure security groups to allow necessary traffic, such as SSH.

2. **Install Apache Kafka and Java Runtime on EC2:**
   - Connect to your EC2 instance using SSH.
   - Update the package list
   - Install Java
   - Install Apache Kafka
      - All commands can be found [here](https://github.com/aarongan4/StockPrice-Kafka-Streaming/blob/main/linux_commands.txt).

4. **Configure Kafka Zookeeper and Start Kafka Server:**

   - Edit Kafka server properties with your EC2 public IP.
   - Find and modify the advertised.listeners setting:
   - Save the changes and start the Kafka server:
  
5. **Create Kafka Topic, Producer, and Consumer:**

   - Create a new Kafka topic:
   - Create Kafka producer and consumer instances to test your setup.

6. **Create Python Scripts for Data Processing and Uploading:**

   - Develop Python scripts to read stock market data using Pandas or a relevant library. (See notebooks)
   - Create mock price data or connect to a real data source. 
   - Configure producer and consumer objects in your Python scripts for publishing and subscribing to Kafka topics.
   - If needed, set up connectivity to an S3 bucket to upload processed data.



