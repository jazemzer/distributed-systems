# Designing data-intensive applications

## What are the 5 standard building blocks

![](../images/building-blocks.svg)

* **Databases** to store data
* **Caches** to speed-up reads or remember expensive operation
* **Queues/Streams** for asynchronous processing
* **Indexes** for searching and filtering stored data
* **Offline processing** for crunching accumulated data or async operations

## What are the 3 major concerns in most software systems

* **Reliability** - means making systems work correctly, even when faults occur. Can the system gracefully handle hardware/software faults and human errors? This is about being fault-tolerant or resilient.
* **Scalability** - means having strategies for keeping performance good, even when load (either in traffic or data volume) increases. 
* **Maintainability** - is about making life better for engineering and operations teams

## Define Reliability 

System's ability to continue to work correctly, even when things go wrong. The things that can go wrong are called faults

### What is the difference between Fault vs Failure

In a complex system, fault is when one of the components deviates from the specification. Whereas, failure is when the system as a whole stops working.

### What are the different types of faults
* Hardware faults
    * disk crash, faulty RAM, power blackout, network failure
* Software Errors 
    * Edge cases crashing the process
    * Memory leak
    * Cascading failures
* Human errors
    * Configuration errors

### How to handle different types of faults
* Hardware failures - Add redundancy to individual hardware component
    * Disk - RAID configuration
    * Server - Dual power supplies
    * Hot-swappable CPUs
    * Datacenter with backup power (batteries or diesel generators)
* Software Errors
    * Testing
    * Process isolation
    * Allow crash and automatic restart
    * Monitoring & Alerting
* Human Errors
    * Fully featured Sandbox environment
    * Thorough testing - Unit test, Integration test, etc
    * Gradual code rollout
    * Ease to rollback configuration changes
    * Telemetry - Detailed monitoring
    * Good training 

## Define Scalability

System's ability to cope up with increase load (traffic/data)

### How to describe a system's current load?

Current load on the system can be described using a number (called **load parameter**) as below:

* web req/sec
* ratio of db reads and writes
* Cache hit ratio
* simultaneous active users

### How to describe a system's performance ?

Before investigating what happens when the load increases, the system's performance can be benchmarked 

* Batch systems
    * Throughput
    * Time take to complete work that uses a dataset of fixed size
* Online systems
    * latency/response time measured in percentiles

#### What are tail latencies?
High percentiles of response time are called tail latencies. They are important because it can represent customers with the most data

### How to cope with increased load?

* Design and build systems for estimated future growth
* Choose wisely between scaling-up and scaling-out
    * Consider `elastic` systems that scale automatically when the load increases
    * Consider `shared-nothing` architectures

## Define Maintainability 

It can be defined in these 3 design principles

* **Operability** - Make it easy for operations teams to run the system smoothly
* **Simplicity** - Make it easy for new engineers to understand the system
    * Avoiding `big ball of mud`
    * Removing `accidental complexity` with good abstractions
* **Evolvability** - Make it easy to make future changes - Extensibility or Plasticity

## Encoding and Evolution

Json 

* cannot distinguish integer and floating-point numbers and there is no precision
* doesn't support binary strings - sequence of bytes without any encoding

 Binary encodings of Json - MessagePack, BSON, BJSON, UBJSON, BISON, and Smile, to name a few

 What is the space saved for ProtoBuf compared to Json


Document databases 
* Doesn't nicely handle one-to-many information because you cannot do joins in db but have to do in application layer
* Schema flexibility due to storage locality

Network model - one record could have multiple parents - to represent both one-to-many and many-to-many relationships


Schema-on-read vs schema-on-write
	* 1 is advantageous when the schema is changing



Locality in Spanner, Oracle (Multi table  index cluster tables), Bigtable data model

Document reference in MongoDB
Mongodb offers MapReduce
Triple stores


