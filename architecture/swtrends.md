---
layout: default
title: 5 Key Software Trends of 2017
permalink: /swtrends/
---

# 5 Key Software Trends of 2017
Note: This is the skeleton on Trends in software development for 2017. My approach is to incrementally build the content of this article over a period of time. Favoring Agile approach I am posting this before it is fully complete..Happy reading!

## 1. Data Innovation
All about Data. Its acquisition, storage and leverage

### Data Acquisition
* Big Data
* Fast Data - Most relevant for most organizations
* Hybrid or Lambda architecture

### Data Storage and organization
* Distributed File Systems (Hadoop HDFS, S3, etc)
* Data lakes (Unstructured, Structured or Hybrid Storage)
* Why not Data Oceans?

### Data Insights and leverage
* Machine learning
* Data Science
* AI


## 2. Artificial Intelligence
### Machine Learning
* classification and Clustering
* Linear and Logistic Regression
* Random Forest
* K means
* etc

### ANN
* Supervised Learning - Articial Neural Networks
* Unsupervised Learning - Genetic Algos, Reinforcement Learning

## 3. Reactive architecture
* Scalability in 3 dimensions (Horizontal, Vertical and Partitioning)
* Non-Blocking architecture
* Stateless Architecture
* Elastic computing

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
Independently deployable small modular services with high functional cohesion and loosely coupled interaction with other micro-services through APIs(REST, g-rpc etc).

This architecture is an anti-monolith pattern and a successor to the SOA design pattern. As opposed to highly functional Enterprise service bus driven architecture of SOA, MS patterns favor a light weight messaging approach (dumb pipes connecting smart functional services).

Key ingredients of a simple MS Pattern includes:

1. Efficient API Gateway as an external interface
2. Service Discovery : e.g. Eureka (Part of Netflix OSS)
3. Independent Micro-Services - Services which provide a functional capability and own the associated data store. Ideally services should not share a database with another services
4. (Optional) A Light weight messaging system like Apache Kafka or a JMS system - No ESBs allowed. Any service composition are done by services themselves (Can be built as composite services) instead of orchestration. A Choreography based approach vs orchestration is preferred.
