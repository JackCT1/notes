# Kafka

## Overview

Kafka (named after the writer Franz Kafka) is a distributed event-streaming platform used for real-time data pipelines and analytics.

A `producer` writes data to a `topic` which is replicated into different servers called `brokers`. Several brokers make up a `cluster`.

A `consumer` reads data from the cluster.

`Zookeeper` is a resource manager which ensures the servers in the cluster are running properly. It detects failures and provisions recovery.

A `topic` is a particular category of messages. A topic is partitioned into `logs` for different instances of that category. For example, a customer topic with 100 customers will have 100 partitions for each customer.

The data thats gets written to a topic is replicated in topics across all the different brokers.

A `log` is a stored list of events (or changes to the state) called records.
