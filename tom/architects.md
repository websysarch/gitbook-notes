# Architects

### What is a  Architect

#### Career Path

Developer -> Team Leader -> Architect

#### Types

1. Infrastructure Architect
2. Software / Solution / Architect Architect
3. Enterprise Architect

Infrastructure Architects

* Servers, VMs, Network, Storage, etc
* Career Path: Infrastructure Experts

Enterprise Architect

* Works with Top level management - CEO, CIO
* Streamlines the IT to Support Business
* No Development-oriented Tasks
* Career Path: Senior Software Architect / Project Manager

Software / Solution / System Architect

> Software Architect, Solution Architect and System Architects are the same.

* Think about Your Client's Clients, Get in touch with your System Analyst

#### Responsibilities&#x20;

####

#### Baseline Requirements&#x20;

* Fast
* Secure
* Reliable
* Easy to Maintain



### Understand the Business

#### The System's Goals



Example 1:

| System       | HR System                          |
| ------------ | ---------------------------------- |
| Organization | Product-Oriented Company           |
| Goals        | Streamline the Recruitment Process |

Example 2:

| System       | Reporting & Mapping Criminal Incidents                                         |
| ------------ | ------------------------------------------------------------------------------ |
| Organization | Large City                                                                     |
| Goals        | <ol><li>Improve Police's Response Time</li><li>Attract New Residents</li></ol> |

Example 3:

| System       | Mobile Flash Sales                                                        |
| ------------ | ------------------------------------------------------------------------- |
| Organization | Young & Small Startup                                                     |
| Goals        | <ol><li>Generate Quick revenue Stream</li><li>Attract Investors</li></ol> |



### The Architecture Process

Before you start the process you should be aware of the business and the system's goals.

* Understand the System's requirements
* Understand the Non-Functional Requirements
* Map the components
* Select the Technology Stack
* Design the Architecture
* Write Architecture Document
* Support the Team

#### System's Requirements

_Functional Requirements:_ What the System Should Do

* Business Flows. Eg.: Login, Storing Photos, Receiving & Crunching telemetry data
* Business Services. Eg.: Login Service, Data Access Service, Telemetry Receiver, Telemetry Cruncher
* User Interfaces

#### Non Functional Requirements

What Should the System Deal With

* Performance
  * Always talk in numbers
  * [Latency](../topics/latency-and-throughput.md): how much time does it take to perform a single task.
  * [Throughput](../topics/latency-and-throughput.md): How many tasks can be performed in a given time unit.
* Load
  * Quantity of Work Without Crashing. Eg. In a web API, no. of concurrent requests
* Data Volume
  * How much data the System will accumulate over time
  * Helps deciding Database type, Designing Queries, Storage Planning
  * Day One Data, Annual growth of data
* Concurrent Users
  * How many users will be using the system simultaneously
  *
* SLA
  * 99.99% Equals to \~0.88hrs downtime/year

For Above, you should also take into consideration:

* How much fluctuation in those number happens
* Does it affected by external factors: Eg. Christmas, Black Friday Sales, etc.
* Does any policy like GDPR Affect the architecture?





#### Map the components

* Represent the Tasks of the System
* Non Technical

#### Technology Stack

* Front End
* Back End
* Data Store

Design the Architecture

* df

#### Architecture Document

* Describes the Process & the Architecture
* Must be relevant&#x20;

#### Support the Team

* Architecture will change

### FAQs

#### Architect vs Senior Developer

> Developer knows what can be done
>
> Architect knows what should be done

* Architect is less interested in how it's implemented, This is developers' job.
* Architect looks at the macro level and fuses the technology as a requirements.

#### Should An Architect Code?

Yes, They may not implement the entire thing, but should do sort of POCs.

* Architecture's Trustworthiness
* Support the Developers
* Respect

No, their time is valuable.

* Should focus on creating patterns and create documents



####

