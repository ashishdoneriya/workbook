---
title: "What is the difference between Topic and Partition in Apache Kafka"
date: 2019-02-21T01:43:00+05:30
lastmod: 2019-02-21T01:43:00+05:30
tags:
  - kafka
categories: 
  - big data
url: /topic-vs-partition-in-kafka.html
---

Partitions in Kafka are like buckets within a topic used for better load balancing when you are dealing with large throughput where you can as many consumers as your partitions to process your data. For example if you are processing orders you can send all orders for iPad into one partition “0” and iPhones in another partition “1” of the same Orders Topic and you can have two services one processing iPhone order from partition “1” and iPad from partition “0” and also maintain ordering of messages per partition. If a consumer service goes down the another service will pickup messages from both partition until another service comes backup into same consumer group processing orders topic.
Whereas replication factor determines how many backups you want to create for your topic in the Kafka cluster for enabling HA for your data in times of cluster losing a node due to various reasons.


Source : [Quora](https://www.quora.com/Whats-the-difference-between-partition-number-and-replication-factor-in-Kafka)

More Information : [StackOverflow](https://stackoverflow.com/questions/38024514/understanding-kafka-topics-and-partitions)
