# Availability

* Fault Tolerance
* % of time, the system works (operational)
* HA or High Availability when its 99.999% or more

Availability is ensured by Redundancy.

* Active Redundancy\
  Requests are handled by one server, and if it fails, one of the other takes over by "leader elections". (Something like master slave)
* Passive Redundancy: All the servers receives requests and if one fails, other continues to work and the requests are transferred to the working ones. (Something like cluster)

### Definitions

#### Availability

The odds of a particular server or service being up and running at ay point in time, usually measured in percentages. A server that has 99% availability will be operational 99% of the time.

#### High Availability

When a system is available for `>=99.999` (5 or more nine's)

#### SLA: Service Level Agreement

An SLA is a collection of guarantees given to a  customer by a service provider. SLAs typically make guarantees on a system's availability, among other things.&#x20;

SLA are made up of one or multiple SLOs.

#### SLO: Service Level Objectives

#### Nines

| Nines | Percentage | Yearly Down Time       |
| ----- | ---------- | ---------------------- |
| 2     | 99         | 87.7 Hours (3.65 days) |
| 3     | 99.9       | 8.77 Hours             |
| 4     | 99.99      | 52.6 Mins              |
| 5     | 99.999     | 5.26 Mins              |
| 6     | 99.9999    | 31.56 Secs             |
