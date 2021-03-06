---
layout: default
title: 5 Key Software Trends of 2017
permalink: /swtrends/
---

# 5 Key Software Trends of 2017
Note: In progress article..Happy reading!

![Image Placeholder](/assets/images/swtrends.png)


## 1. Data Innovation
All about Data. Its acquisition, storage and leverage

### Data Acquisition
* Fast Data/Data Streaming
* Event based Data Streaming using Flume/Kafka

### Data Storage and organization
* Distributed File Systems (Hadoop HDFS, S3, etc)
* Data lakes (Unstructured, Structured or Hybrid Storage)


### Data Insights and leverage
* Data Science - Machine learning, AI


## 2. Intelligent Apps
### Machine Learning
* classification and Clustering
* Linear and Logistic Regression
* Random Forest
* K means
* etc

### AI
* Supervised Learning - Articial Neural Networks
* Unsupervised Learning - Genetic Algos, Reinforcement Learning
* [AI Techniques](http://theory.stanford.edu/~amitp/GameProgramming/AITechniques.html)

## 3. Reactive architecture
* Scalability in 3 dimensions (Horizontal, Vertical and Partitioning)
* Non-Blocking architecture
* Stateless Architecture
* Elastic computing
* [Reactive Manifesto](http://www.reactivemanifesto.org/)


## 4. API Innovation

### API Semantics
* HATEOS (Hypermedia as the engine of Application State)
* RMM - Richardson Maturity Model
* HAL (Hypertext Application Language)
* JSON-LD (Linked Document)
* etc

### API Gateways
* Non functional Gateways
* Functional Gateways

### API Specification Methods
* Swagger
* RAML

## 5. Micro Services Architecture
*Independently deployable* small modular services with high functional cohesion and loosely coupled interaction with other micro-services through APIs(REST, g-rpc etc).

This architecture is an anti-monolith pattern and a successor to the SOA design pattern. As opposed to highly functional Enterprise service bus driven architecture of SOA, MS patterns favor a light weight messaging approach (dumb pipes connecting smart functional services).

Key ingredients of a simple MS Pattern includes:

1. Efficient API Gateway as an external interface
2. Service Discovery : e.g. Eureka (Part of Netflix OSS)
3. Independent Micro-Services - Services which provide a functional capability and own the associated data store. Ideally services should not share a database with another services
4. (Optional) A Light weight messaging system like Apache Kafka or a JMS system - No ESBs allowed. Any service composition are done by services themselves (Can be built as composite services) instead of orchestration. A Choreography based approach vs orchestration is preferred.
