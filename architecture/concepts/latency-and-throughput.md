# Latency and Throughput

For measuring performance these two are very important

> If you've ever experienced lag in a video game, it was most likely due to a combination of high latency and low throughput. And lag sucks.

### Definitions

#### Latency

How much time does it take to perform a single task.

* how much time will it take for the API to save the user data in the database?
* How much time will it take to read a single file from the file system?

#### Throughput

How many tasks can be performed in a given time unit.&#x20;

Throughput of a server can often be measured in request/query per second (RPS/QPS)

* How many users can be saved in the database in a minute.
* How many files can be read in a second.

Note:

* Generally throughput is increased via scaling, preferably horizonal
* Load changes are handled via using queues and scaling.

#### Example: Saving User Data

|            |                               |   |
| ---------- | ----------------------------- | - |
| Latency    | 1 Second                      |   |
| Throughput | Requirement: 100req/sec       |   |
|            | Well Designed app: >100       |   |
|            | Badly designed apps: <60      |   |
| Load       | 500 requests without crashing |   |
|            |                               |   |

### Common Latency

#### Network Latency

Time taken for a request to do the complete roundtrip. (client -> Server and Server -> client)

#### Disk Latency

Time taken to read the data from a disk.



Using different components in a system  design, will have different latency (and associated cost) and hence these components affect the overall performance.

Below table demonstrates the latency of different operations & components.

| Task                                                   | Latency |
| ------------------------------------------------------ | ------- |
| Reading 1MB from **RAM**                               | 0.25ms  |
| Reading 1MB from **SSD**                               | 1ms     |
| Transfer 1MB over **Network** (eg within same network) | 10ms    |
| Reading 1MB from **HDD**                               | 20ms    |
| Inter-Continental Round Trip (Internet Request)        | 150ms   |

### FAQs

#### Concurrent Users Vs Load

* Concurrent Users - Including "Dead Times"
* Load: Actual Requests

#### Latency Vs Throughput

* They are not co-related, i.e. you can not make assumption of one given the other.
*

