# Latency and Throughput

For measuring performance these two are very important

### Definitions

#### Latency

How much time does it take to perform a single task.

* how much time will it take for the API to save the user data in the database?
* How much time will it take to read a single file from the file system?

#### Throughput

How many tasks can be performed in a given time unit.

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

### FAQs

#### Concurrent Users Vs Load

* Concurrent Users - Including "Dead Times"
* Load: Actual Requests

