# Kafka with KRaft Mode + Kafka UI

This project sets up a single-node Apache Kafka cluster using **KRaft mode** (no Zookeeper) and **Kafka UI** for management.

## Features

- Kafka broker running in KRaft mode
- Kafka UI for monitoring and topic management
- Ports exposed for external access

## Quick Start

1. Install Docker and Docker Compose
2. Clone this repo
3. Run: `docker-compose up -d`
4. Open Kafka UI at: [http://localhost:8088](http://localhost:8080)

## Services & Ports

| Service   | Port    | Description         |
|-----------|---------|---------------------|
| Kafka     | 9092    | Internal broker     |
|           | 9093    | Controller (KRaft)  |
|           | 9094    | External access     |
| Kafka UI  | 8088    | Web interface       |

## Example Commands

Create topic:
```bash
docker exec broker /opt/kafka/bin/kafka-topics.sh --create \
  --topic test-topic --bootstrap-server broker:9092 \
  --partitions 1 --replication-factor 1
