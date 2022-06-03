---
description: Tools to use for API Design
---

# API Development

> If the API is process intensive, you should use a multi-threaded based tool, like Java Spring Boot.\
> This is for IO intensive or less process based APIs using Node as base Platform



### Requirements

#### Functional Requirements

* Based on Business use-case and the problem we are trying to solve

#### Non Functional Requirements

*

### Points of Views

#### Architects

Questions

* What is the load and how do we mange load?

Problems to solve:

* Load balancing - horizontal scaling of upstream servers
* Caching - Redis, distributed
* Performance
  * Per request
  * d
* Security
* Metering
* Logging

#### Team Lead

#### Developer



### Technologies Involved



### Tool set - Development

#### Base Platform

* Node JS
* Typescript Language
* Express JS as base Server for Restful

#### DX

* Prettier
* Es-Lint

#### Frameworks

* Express JS for REST APIs
* `apollo-server` for Graph-QL support
* `prisma` as ORM, allow you to switch to whatever DB you want.
* `sqllight3` as DB for sample projects and ideas, in production prefer `postgres` SQL.

#### Utility&#x20;

* Input validation by `joi` : Object schema validation
*

#### Testing

* Jest for unit testing of functions
* `ajv` for JSON Schema validation of REST API Response

### Tool set - Production

* Logging
* Monitoring
* Health checks

