Kafka: Interesting, Useful, or Weird
====================================

Here's a brief, but growing, collection of media that I've found to be one of the above (or something else) as relates to Kafka and, more broadly, streaming data.

Tools
-----

`Kafka Pixy <https://github.com/mailgun/kafka-pixy>`__ REST and gRPC Kafka proxy, which automagically controls consumer group assignment, subscription, and termination. That's cool! From their documentation: "It is designed to hide the complexity of the Kafka client protocol and provide a stupid simple API that is trivial to implement in any language." I like that!

`Application Reset Tool <https://kafka.apache.org/21/documentation/streams/developer-guide/app-reset-tool>`__ From Apache! A blessed tool to force an application that reads Kafka messages to reprocess said messages from the beginning by resetting topic offsets.

Consumers
---------

`Kafka Consumers: Reading Data from Kafka <https://www.oreilly.com/library/view/kafka-the-definitive/9781491936153/ch04.html>`__

`What determines Kafka consumer offsets? <https://stackoverflow.com/a/32392174/2387597>`__ Great StackOverflow answer explaining how consumer offsets get configured. For reference, a consumer offset tells something reading messages from one or more topics where to resume reading from on the occasion that it's execution paused.

`How to reset Kafka consumer group offset <https://gist.github.com/marwei/cd40657c481f94ebe273ecc16601674b>`__

Kafka configuration and performance management
----------------------------------------------

`Which Knobs To Turn? <https://bigdatagurus.wordpress.com/2017/07/28/kafka-which-knobs-to-turn/>`__ Short! That's good! Bare minimum configuration changes that need to happen to run Kafka in production.

`Configuring Apache Kafka for Performance and Resource Management <https://www.cloudera.com/documentation/kafka/latest/topics/kafka_performance.html>`__

`Introducing Kafka-Kit: Tools for Scaling Kafka <https://www.datadoghq.com/blog/engineering/introducing-kafka-kit-tools-for-scaling-kafka/>`__

Topic partitioning & configuration
----------------------------------

`Effective Strategies for Kafka Topic Partitioning <https://blog.newrelic.com/engineering/effective-strategies-kafka-topic-partitioning/>`__

`Handling GDPR with Apache Kafka: How does a log forget? <https://www.confluent.io/blog/handling-gdpr-log-forget/>`__ Configure topics that store personally identifying information (PII) to perform log compaction, which (eventually) deletes messages with the same key. Requires that messages be keyed and deletion is not instantaenous, though it's quick from a human's perspective. I've used log compaction in a simple way to keep the currrent state of some entity for the Maestro (Teachable Masters) project.

`Kafka, GDPR and Event Sourcing <https://danlebrero.com/2018/04/11/kafka-gdpr-event-sourcing/>`__

Stream Processing
-----------------

`Faust <https://github.com/robinhood/faust>`__ Like `Kafka Streams <https://kafka.apache.org/documentation/streams/>`__ but for Python!

Miscellaneous, cool
-------------------

`Streaming data from PostgreSQL to Kafka using Debezium <https://medium.com/@tilakpatidar/streaming-data-from-postgresql-to-kafka-using-debezium-a14a2644906d>`__

`Publishing with Apache Kafka at The New York Times <https://app.getpocket.com/read/1881803965>`__ This is the article that got me interested in using Kafka in novel ways. The New York Times,  the Grey Lady, uses Kafka as a durable, forever data store. This is wildand I don't think will ever actually work anywhere else in practice but it's very intersting / shows the power of Kafka and its configurability.