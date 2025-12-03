# ML System Design Interview Questions

This folder contains interview questions focused on designing and deploying machine learning systems at scale.

## Topics Covered

1. **ML Pipeline Design**
2. **Model Deployment**
3. **Scalability and Performance**
4. **Monitoring and Maintenance**
5. **Real-world Scenarios**

---

## Questions

### 1. How would you design an ML system for a recommendation engine?
**Answer:** Key components:
- **Data Collection**: User interactions, item features, contextual data
- **Feature Engineering**: User embeddings, item embeddings, collaborative signals
- **Model Selection**: Collaborative filtering, matrix factorization, deep learning (NCF, Wide & Deep)
- **Serving**: Candidate generation → ranking → re-ranking → filtering
- **Infrastructure**: Feature store, model serving (low latency), A/B testing
- **Metrics**: CTR, conversion, user engagement, diversity

### 2. Explain the difference between batch and real-time inference.
**Answer:** 
- **Batch Inference**: Process large datasets periodically (hourly/daily). Lower cost, higher throughput, acceptable for non-time-sensitive predictions.
- **Real-time Inference**: Process individual requests with low latency (<100ms). Higher cost, requires optimized serving infrastructure.
Choose based on: Latency requirements, cost constraints, data freshness needs.

### 3. How do you handle model versioning and rollback?
**Answer:** Best practices:
- **Model Registry**: Central repository for model versions (MLflow, SageMaker)
- **Metadata Tracking**: Training data, hyperparameters, metrics, dependencies
- **Containerization**: Docker for reproducible environments
- **Gradual Rollout**: Canary deployments, shadow mode testing
- **Rollback Plan**: Quick switch to previous stable version
- **A/B Testing**: Compare new vs. old model on live traffic

### 4. What is feature store and why is it important?
**Answer:** A feature store is a centralized repository for ML features:
- **Consistency**: Same features for training and serving
- **Reusability**: Share features across teams and models
- **Point-in-time correctness**: Prevent data leakage
- **Low-latency serving**: Optimized for real-time access
Examples: Feast, Tecton, AWS SageMaker Feature Store.

### 5. How would you design a fraud detection system?
**Answer:** Components:
- **Data**: Transaction history, user behavior, device fingerprints
- **Features**: Transaction amount, frequency, location, time patterns, network features
- **Model**: Ensemble (XGBoost + Neural Network), handle class imbalance (SMOTE, class weights)
- **Serving**: Real-time scoring with <50ms latency
- **Challenges**: Concept drift, adversarial attacks, false positive costs
- **Monitoring**: Alert on distribution shifts, feedback loop from manual reviews

### 6. Explain model monitoring and drift detection.
**Answer:** Types of drift:
- **Data Drift**: Input distribution changes
- **Concept Drift**: Relationship between input and target changes
- **Prediction Drift**: Model output distribution changes
Monitoring approaches:
- Statistical tests (KS test, PSI)
- Model performance metrics
- Feature distribution dashboards
- Automated retraining triggers

### 7. How do you handle imbalanced datasets in production?
**Answer:** Strategies:
- **Sampling**: Oversampling (SMOTE), undersampling, combination
- **Class Weights**: Adjust loss function weights
- **Algorithm Selection**: Tree-based methods often handle imbalance better
- **Metrics**: Use precision, recall, F1, AUC-PR instead of accuracy
- **Threshold Tuning**: Optimize decision threshold for business needs
- **Ensemble**: Combine models trained on different sampling strategies

### 8. Design a search ranking system.
**Answer:** Architecture:
- **Query Understanding**: Tokenization, spell correction, intent classification
- **Candidate Retrieval**: Inverted index (Elasticsearch), approximate nearest neighbors
- **Ranking Model**: Learning to rank (LambdaMART, BERT-based rankers)
- **Features**: Query-document relevance, user personalization, freshness, popularity
- **Serving**: Multi-stage ranking for efficiency
- **Evaluation**: NDCG, MRR, online A/B tests

### 9. How do you ensure reproducibility in ML pipelines?
**Answer:** Key practices:
- **Version Control**: Code, data, configurations (DVC for data)
- **Dependency Management**: Lock file, containerization
- **Random Seeds**: Set seeds for all random operations
- **Experiment Tracking**: Log parameters, metrics, artifacts (MLflow, W&B)
- **Pipeline Orchestration**: Airflow, Kubeflow, DAG-based workflows
- **Documentation**: Clear README, architecture diagrams

### 10. How would you optimize model inference latency?
**Answer:** Techniques:
- **Model Optimization**: Quantization, pruning, knowledge distillation
- **Efficient Architectures**: MobileNet, EfficientNet, DistilBERT
- **Batching**: Group requests for throughput (but increases latency)
- **Caching**: Cache frequent predictions, feature caching
- **Hardware**: GPUs, TPUs, specialized inference chips
- **Framework**: ONNX Runtime, TensorRT, TFLite for optimized inference
- **Infrastructure**: Load balancing, autoscaling, edge deployment
