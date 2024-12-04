---
author: Bryan Montalvan
pubDatetime: 2024-12-04
modDatetime:
title: What, Why, When, and Where Kafka?
featured: true
draft: false
tags:
  - Guide
  - Concept Introduction
description: How to add a new social icon to AstroPaper
---

The *mitochondria* of event streaming

## Table of contents

## Introduction

You might've heard of Kafka at some point in your tech journey. Whether you've seen it as a job posting requirement, mentioned by a classmate, or something you were told you'd have to learn for your job in a few months.

My mission during your read is to demystify this blackbox that Kafka may be. And we'll do it via the following structure
- **what** exactly is Kafka?
- **why** use Kafka?
- **when** should Kafka be used
- **where** in the industry is Kafka being used today

## What is Kafka

Kafka, or its full name Apache Kafka, by definition is a `distributed event data store optimized for ingesting and processing streaming data in real-time`. Cool but what exactly does this mean?

### Example: Santa's factory
Let's break down this definition using Santa's toy factory as an anology: 

> Distributed event data store

Santa created magical orb which contains the information about the gifts people around the world have asked for Christmas. Kafka is the tool that helps transport the information from the orb to the Elves "XMas Dashboard" on their portable devices.

> optimized ingesting and processing streaming data

Kafka was built to withstand the large amount of Christmas Wishes and allows this information to be easily distributed among elves Portable devices (which they use to access the XMas Dashboard).

> streaming data in real-time

In order for the Elves to be as efficient as possible. Their portable devices needs show the latest updates of the global Christmas wishes.

Coming back to reality, you can think of this constant data sharing between the orb and Elves XMas dashboard as event streaming. Where one database (orb) is commuicating to software application (Elf XMas Dashboard). Now Kafka was built in flexibility in mind so you replace the database with another event source such as a sensor, mobile device, cloud service, etc.. (bonus: Think of the Elves portal devices as IoT devices.)

```
TL:DR - Kafka moves data from one system to another, in real-time
```

## Why Kafka?

We're glad the Elves can manage all the Christmas chaos, but why even use Kafka?

### History:
- Kafka was [originally developed at Linkedin](https://www.linkedin.com/pulse/kafkas-origin-story-linkedin-tanvir-ahmed/), and was subsequently open sourced in Early 2011.
- The creators behind Kafka set out to solve a problem Linkedin had when trying to ingestion large amounts of data using low latency. At the time data transmission was performed via batch systems. 
- Do note that there were real-time systems at this time however they seemed a bit overkill given the scope of Linkedin's ambition.

Given that Linkedin had ~1 billion events (user interactions) a day, it was a no brainer for them to create a system which facilitated real-time data streaming.

### Technical Concepts
Kafka leverages three cruical technical concepts to function:
1. To **publish (write)** and **subscribe to (read)** streams of events, including continuous import/export of your data from other systems.
2. To **store** streams of events durably and reliably for as long as you want.
3. To **process** streams of events as they occur or retrospectively.

Kafka is a distributed systems consisting of servers and clients that communicate via a high-performance TCP network protocol.
- **Servers:** Kafka is ran as a cluster of one or more servers, a Kafka cluster performs the communication with existing relational databases. These clusters 
- **Clients:** Allow you to write distributed applications and microservices that read, write, and process streams of events from that Kafka cluster(s). 


## When Kafka?

If you're a project manager or architect, its important to pick the right tool for your project. Kafka fits right in if you're dealing with a ton of data ingestion on a daily basis. 

#### Cases where you should use Kafka
- **Real-Time Data Streaming:** As already mentioned Kafka excels in scenarios requiring real-time data ingestion and stream processing (i.e, log aggregation, IoT snesor data, user activity streams)
- **Event-Driven Architecture:** If you're building an event-driven microservice where services react to specific events asynchronously
- **High-Throughput Ingestion:** If you're project deals with large volumes of streaming data where high-throughout is needed (i.e, financial, banking applications).
- **Real-time monitoring:** If your app needs to collect logs from distributed systems and feeds them into monitoring alerting

#### Cases where you shouldn't use kafka
- **Batch processing:** If your project is performing extensive data transformations and or ETL jobs then you might find yourself using Apache Spark instead.
- **Machine Learning:** For advanced analyics and graph processing its better to use a batch based system
- **Data Exploration:** If you're looking to have a more transparent overview of your data then Kafka might not be the best tool for you
- **Data Warehousing:** Kafka is not the best tool in the shed for dealing with big data storage systems such as Hadoop or S3, which requires large-scale data processing.

## Where Kafka?

Kafka is a highly popular system used across various industries in the tech world. Some examples are:
- Netflix: uses Kafka to monitor user activity in real-time
- Linkedin: As previously mentioned
- Verizon: Kafka is used for processing logs from network devices to identify issues and optimize performance
- Healthcare: Kafka streams data from IoT medical devices which allows medical profesionals to monitor patient vitals
- Uber: Kafka is used to handle real-time streams from drivers and riders. Ensuring real-time updates
- Mail-Delivery: Companies like FedEx and UPS use kafka to stream location data for real-time package tracking
- Twitter: Kafka is used to proces billions of tweets and user inactions a day

## Conclusion

Kafka is a very nifty technology which helps solve not only Linkedin's inital problem but many of our own. 

Like any technology or software, you must treat it as a tool in the toolbox. If properly used the tool can add to your productivity, otherwise it'll simply not get the job done.

This is a high-level overview so if you would like to learn more about the underlying architecture and technical concepts then feel free to visit Apache Kafka's website below!

## Resources:
- https://kafka.apache.org/intro
- https://books.google.com/books?hl=en&lr=&id=jehZEAAAQBAJ&oi=fnd&pg=PA1&dq=what+is+kafka&ots=A-TSoDSHKC&sig=jRFoBbmbD5VNjdziQcb6EejZv20#v=onepage&q=what%20is%20kafka&f=false
- https://www.ibm.com/blog/apache-kafka-use-cases/
- https://netflixtechblog.com/evolution-of-the-netflix-data-pipeline-da246ca36905
- https://engineering.linkedin.com/teams/data/data-infrastructure/streams/kafka
- https://www.uber.com/blog/kafka-tiered-storage/
- https://blog.x.com/engineering/en_us/topics/insights/2018/twitters-kafka-adoption-story

