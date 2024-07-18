Real-time Data Processing Pipeline

Overview

This project sets up a comprehensive real-time data processing pipeline utilizing several technologies including Kafka, Spark, Airflow, and Cassandra. The architecture is designed to handle data ingestion, processing, and storage efficiently and reliably.

Architecture and Components

The architecture consists of the following components:

               +--------------------+
               |     Zookeeper      |
               +--------------------+
                        |
                        v
               +--------------------+
               |      Kafka         |
               |      Broker        |
               +--------------------+
                        |
                        v
               +--------------------+       +-------------------+
               | Schema Registry    |<----->|     Control       |
               +--------------------+       |     Center        |
                        |                    +-------------------+
                        v
               +--------------------+
               |     Airflow        |
               |  (Scheduler & Web) |
               +--------------------+
                        |
                        v
               +--------------------+
               |      Spark         |
               |  (Master & Worker) |
               +--------------------+
                        |
                        v
               +--------------------+
               |     Cassandra      |
               +--------------------+

	•	Zookeeper: Manages and coordinates distributed systems, ensuring Kafka brokers are in sync.
	•	Kafka Broker: Acts as a publish-subscribe messaging system, enabling producers to send and consumers to receive data streams.
	•	Schema Registry: Manages Avro schemas for Kafka topics, ensuring data consistency.
	•	Control Center: Provides a web-based interface to monitor and manage Kafka clusters.
	•	Airflow: Orchestrates workflows, scheduling and monitoring tasks for ETL processes.
	•	Spark: Handles large-scale data processing and analytics, providing both batch and stream processing capabilities.
	•	Cassandra: A NoSQL database designed for high availability and handling large amounts of data.
	•	PostgreSQL: A relational database used by Airflow to store metadata and task results.

### Key Files

- **docker-compose.yml**: Service definitions and configurations.
- **requirements.txt**: Python dependencies.
- **kafka_stream.py**: Kafka stream processing script.
- **spark_stream.py**: Spark stream processing script.
- **entrypoint.sh**: Airflow initialization script.

## Technologies Used

- ![Kafka](https://kafka.apache.org/graphic-resources)
- ![Zookeeper](https://zookeeper.apache.org/images/logos/zk-small.png)
- ![Airflow](https://airflow.apache.org/docs/apache-airflow/stable/_images/pin_large.png)
- ![Spark](https://spark.apache.org/images/spark-logo-trademark.png)
- ![PostgreSQL](https://www.postgresql.org/media/img/about/press/elephant.png)
- ![Cassandra](https://cassandra.apache.org/_/img/ccm-logo.png)
- ![Docker](https://www.docker.com/wp-content/uploads/2022/03/Moby-logo.png)
- ![Flask](https://flask.palletsprojects.com/en/2.0.x/_images/flask-logo.png)
- ![SQLAlchemy](https://www.sqlalchemy.org/img/sqla_logo.png)
- ![Python](https://www.python.org/static/community_logos/python-logo.png)

## Setup Instructions

1. Clone the repository.
2. Ensure Docker is installed.
3. Run `docker-compose up --build` to start the services.
4. Access the Airflow web interface at `http://localhost:8080`.
5. Monitor Kafka and other services using Control Center at `http://localhost:9021`.










 
