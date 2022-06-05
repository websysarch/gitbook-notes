---
description: Software Quality Attributes
---

# Quality

Technical capabilities that should be used in order to <mark style="color:blue;">fulfill the non-functional requirements</mark>.

[Full list of System Quality Attributes](https://en.wikipedia.org/wiki/List\_of\_system\_quality\_attributes)

Generally, Non-functional requirements will map to set of quality attributes and would contribute towards final architecture.

#### Example of Non Functional requirements mapping to Quality

* The System must work under heavy load, but should not waste money on unused resources.
  * Scalability
*

### Scalability

Adding computing resources without any interruption.

* Vertical scaling / Scale Up - Use more powerful server
* Horizontal Scaling / Scale Out - increase the number of servers.

Always prefer, Horizontal Scaling.&#x20;

#### Vertical Scaling

* Add more cores and memory to the existing system

Not recommended because of below reasons:

* There is a limit to how much ram or cores/processors you could upgrade.
* More expensive
* Does not improve availability, if the server goes down, everything is down.

#### Horizontal Scaling

* Needs a load balancer
* Application should be designed stateless. (Why, different request from same user could be processed by different servers)
* Gives Redundancy
* No Limits

Generally, you would add additional servers and notify the load balancer.

Cloud providers offers something called "**Auto Scaling**" which does this automatically based on the load your server is receiving.

### Manageability

Know what's going on and take actions accordingly

Servers reports status to monitoring agents

#### Is it manageable?

* If the problems are reported by customers, Its not manageable.
* If the problems are reported by the system itself.

### Modularity

A system that is built from building blocks, that can be changed or replaced without affecting the whole system.

### Extensibility

A system that its functionality can be extended without modifying its existing code.

Common pattern for extensibility:

* Plugin framework with dependency injection

### Testability

How easy is it to test

* Independent modules and methods
* Single Responsibility

#### Types of Testing

* Manual Testing
* Unit Testing
* Integration Testing
* E2E Testing

