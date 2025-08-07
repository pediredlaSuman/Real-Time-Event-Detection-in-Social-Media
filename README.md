# 📡 Real-Time Event Detection in Social Media

A big data pipeline that simulates real-time social media stream analysis to detect breaking events using Apache Kafka, Hadoop HDFS, and Apache Mahout (LDA topic modeling). This system identifies trends such as natural disasters, concerts, emergencies, and technology launches by processing high-velocity, unstructured text data.

---

## 🔍 Overview

With the explosion of social media data, detecting real-world events in real-time has become both vital and challenging. This project demonstrates an end-to-end scalable pipeline capable of:

- Real-time data ingestion using **Apache Kafka**
- Distributed fault-tolerant storage with **Hadoop HDFS**
- **Latent Dirichlet Allocation (LDA)** topic modeling using **Apache Mahout**
- Visualizing social trends with **histograms, bar graphs, and line plots**

---

## 🛠️ Tech Stack

| Component         | Tool/Framework     | Description |
|------------------|--------------------|-------------|
| 🔄 Ingestion      | Apache Kafka        | Simulated real-time social media stream |
| 💾 Storage        | Hadoop HDFS         | Distributed, scalable data storage |
| 📊 Topic Modeling | Apache Mahout + LDA| Extracts themes from unstructured text |
| 🧪 Dataset        | Kaggle SI650        | 33,000+ short social media-style messages |
| 🖥️ Cluster        | Multi-node Hadoop   | Simulated parallel execution |

---

## 🗂️ System Architecture

![System Architecture](https://user-images.githubusercontent.com/placeholder/system-architecture.png) <!-- Replace with actual image if available -->

**Figure**: End-to-end pipeline from Kafka producer to Mahout-based topic extraction.

---

## 🔁 Workflow

1. **Kafka Producer**: Simulates live tweet/message stream using short social messages.
2. **Kafka Consumer**: Subscribes to topic and writes messages to HDFS.
3. **Storage Layer**: Organizes messages by `year/month/day` for batch analysis.
4. **Apache Mahout (LDA)**:
   - Preprocess text (tokenization, stopword removal, stemming)
   - Vectorize using TF-IDF
   - Train distributed LDA model
   - Extract topic-wise word distributions
5. **Trend Analysis**: Plot histogram, bar graph, and temporal line graph from LDA output.

---

## 📈 Results

| Metric                | Value                  |
|-----------------------|------------------------|
| Ingestion Rate        | 1,000 messages/min     |
| Kafka Throughput      | 50 KB/sec              |
| HDFS Storage Rate     | 0.5 MB/min             |
| LDA Coherence Score   | 0.61 (U-Mass metric)   |
| Detection Latency     | < 5 seconds            |

---

## 📊 Sample Topics Extracted

| Topic # | Top Keywords                 | Description                      |
|---------|------------------------------|----------------------------------|
| Topic 1 | earthquake, city, damage     | Natural disasters                |
| Topic 2 | concert, tonight, band       | Recreational events              |
| Topic 3 | fire, rescue, smoke          | Public safety incidents          |
| Topic 4 | technology, launch, features | Product/tech releases            |
| Topic 5 | holiday, celebration         | Cultural and social activities   |

---

### 📉 Visualizations

- **Histogram**: Topic frequency distribution
- **Bar Graph**: Top keywords per topic
- **Line Graph**: Topic trends over time

![Sample Graph](https://user-images.githubusercontent.com/placeholder/sample-graph.png) <!-- Replace with real image -->

---

## ⚙️ How to Run (Simulation Setup)

1. **Kafka Setup**
   ```bash
   bin/zookeeper-server-start.sh config/zookeeper.properties
   bin/kafka-server-start.sh config/server.properties
   bin/kafka-topics.sh --create --topic socialmedia --bootstrap-server localhost:9092 --partitions 1 --replication-factor 1
