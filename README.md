# Fraud-Detection-and-Fraud-Prevention-using-AI

Fraud detection is a critical aspect of financial systems to prevent losses and ensure the integrity of transactions. This repository mainly focuses on detecting fraud using peer-to-peer (P2P) transaction data. The project utilizes the Neo4j graph database to analyze relationships and detect potentially fraudulent activities. <br>
Using Neo4j offers several advantages over traditional methods: <br>
- **Efficient Relationship Handling:** Neo4j excels at managing complex relationships, making it ideal for fraud detection where connections between entities are crucial.
- **Graph Algorithms:** Neo4j’s graph algorithms provide powerful tools for identifying patterns and anomalies in the data.
- **Scalability:** Neo4j can handle large datasets efficiently, making it suitable for real-world applications.
- **Real-time Analysis:** The ability to perform real-time analysis on graph data ensures timely detection of fraudulent activities. <br>

## Dataset

The dataset (`neo4j-p2p-data.dump`) used in this repo is collected from YouData.ai. It includes P2P transaction data with the following properties:<br>

- **Nodes:** 789,856
- **Relationships:** 1,776,743
- **Labels:** 4 (Card, Device, FlaggedUser, IP, User)
- **Relationship Types:** 5 (HAS_CC, HAS_IP, P2P, REFERRED, USED)
- **Property Keys:** 34 (e.g., cardDate, device, fraudRisk, etc.) <br>
The dataset's comprehensive nature and detailed properties make it an excellent resource for developing and testing fraud detection algorithms.

## Impact of Machine Learning in Fraud Detection

In real-world scenarios, identifying fraudulent user accounts in advance is challenging. Flags based on business rules like chargeback history or user reports are often insufficient. Community detection and recommendation approaches help identify additional fraud risk users. However, supervised machine learning enhances this by enabling proactive detection, providing measurable performance metrics, and automating fraud risk prediction. To classify fraud risk accounts effectively, graph features are engineered using GDS, including WCC community sizes, PageRank, and degree centrality.

In this repo, a Random Forest classifier is used due to its robustness to feature scaling and collinearity issues, and minimal tuning requirements. Random Forests are ensemble models that combine multiple decision trees to improve predictive accuracy and control overfitting. The model is trained with 500 estimators, a maximum depth of 5, and balanced class weights to handle class imbalance.

Investigating high-probability fraud predictions that were not previously labeled provides further insights. Visualizing these cases in Neo4j Bloom helps refine the model and improve understanding of fraud patterns.

## Neo4j Graph Database V/S Neo4j Graph Data Science

### Using Neo4j Graph Database:
- **Neo4j Desktop:** Install and use locally for free.
- **Neo4j Aura Free Tier:** Cloud service with limited resources for small projects.
- **Neo4j Sandbox:** Free cloud-hosted environment for learning and experimentation (limits nodes and relationships).

### Using Neo4j Graph Data Science (GDS):
- **Neo4j AuraDS:** Managed cloud service for GDS, charged based on hourly usage and dataset size.
  
Hence I've used Neo4j AuraDS for training models in Jupyter Notebook, but since it’s not free, I am using Neo4j Desktop for visualization and real-time analysis of the dataset.


