# Kafka Cluster with KRaft Mode and UI

This project sets up a 3-node Apache Kafka cluster using KRaft mode (without Zookeeper) along with Kafka UI for management.

## Features

- 3 Kafka brokers in KRaft mode (no Zookeeper needed)
- Kafka UI for cluster monitoring and management
- Persistent storage for each broker
- External ports exposed for each broker

## Quick Start

1. Ensure Docker and Docker Compose are installed
2. Clone this repository
3. Run: `docker-compose up -d`
4. Access Kafka UI at: `http://localhost:8080`

## Configuration

- Brokers: `kafka1`, `kafka2`, `kafka3`
- Internal communication port: 9092
- Controller port: 9094
- External ports: 
  - kafka1: 19090
  - kafka2: 19091 
  - kafka3: 19092
- All brokers share the same cluster ID

## Notes

- Data is persisted in Docker volumes
- KRaft mode is enabled (Kafka's built-in consensus protocol)
- No authentication configured (plaintext listeners only)
