# Chronus

## Overview

This project consists of running Apache Kafka with two topics (`immidiateNoRecur` and `futureTimeScheduled`) configured with partitions. Additionally, it involves setting up and running three Node.js services. The services are built using npm and utilize Postman collections to access their APIs and then by using those apis to manage jobs 

## Kafka Setup

1. **Installation**: Install Apache Kafka on your system. Refer to the [official Apache Kafka documentation](https://kafka.apache.org/documentation/) for installation instructions.
   
2. **Topic Creation**: Create two topics, `immidiateNoRecur` and `futureTimeScheduled`, with the desired number of partitions.

```bash
kafka-topics.sh --create --topic immidiateNoRecur --partitions 3 --replication-factor 1 --bootstrap-server localhost:9092
kafka-topics.sh --create --topic futureTimeScheduled --partitions 3 --replication-factor 1 --bootstrap-server localhost:9092

## Node server run
run 3 services i.e. Rest Api , kafka consumer for scheduled jobs , kafka consumer for immidiate jobs
1. npm i
2. npm run build
3. npm run start

please use postman dump for api reference
provided apis are 

1. api to register user
2. api to login user
3. api create job (bearer token is required in header)
4. get all jobs based on user (bearer token is required in header)
5. update the job based on job id (bearer token is required in header)
6. delete job based on job id  (bearer token is required in header)