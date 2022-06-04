---
description: Back End | Front End | Data Store
---

# Tech Stack

General Stuff to consider

* Can perform the tasks
* Community (Check stack overflow tags)
* Popularity (Google trends)
  * It affects community
  * Developer interests
  * Supply of Skilled Developers



### Backend Stacks

| Language  | App Types                           | Type System | Cross Platform | Community          | Performance | Learning Curve |
| --------- | ----------------------------------- | ----------- | -------------- | ------------------ | ----------- | -------------- |
| .NET      | All                                 | Static      | No             | Large              | OK          | Long           |
| .NET Core | Web Apps, Web API, Console, Service | Static      | Yes            | Medium but Growing | Great       | Long           |
| Java      | All                                 | Static      | Yes            | Huge               | OK          | Long           |
| Node JS   | Web Apps, Web API                   | Dynamic     | Yes            | Huge               | Great       | Medium         |
| PHP       | Web Apps, Web API                   | Dynamic     | Yes            | Large              | OK          | Medium         |
| Python    | All                                 | Dynamic     | Yes            | Huge               | OK          | Short          |

#### Dot Net (.NET) Classing

* Founded in 2001 by Microsoft&#x20;
* General purpose
* Object Oriented
* Statically typed
* IDE - Visual Studio
* Windows Only (Not Platform)
* Performance - OK
* Very Mature
* Blurred Roadmap

#### Dot Net (.NET) Core

* .NET vNext
* Cross Platform
* Great performance
* Not fully baked yet
* IDE - Visual Studio, VS Code
* Vocal, growing community

#### Java

* Founded in 1995 by Sun Micros systems
* Very popular
* General purpose
* Object Oriented
* Statically typed
* Huge community

#### Node JS

* Founded in 2009 by Ryan Dahl
* Optimized for highly-concurrent Web Apps
* JavaScript-based
* Dynamically typed
* Large community
* Great performance
* Not Good for Long Running Processes

#### PHP

* Founded in 1994 by Rasmus Lerdorf
* A little messy
* Very easy to learn
* Not polished
* Large community
* Focused on Web Apps & Web API
* Not Good for Long Running Processes

#### Python

* Founded in 1989 by Guido van Rossum
* Scripting Language
* Very popular
* Very easy to learn
* Huge, supportive community
* Supports any type of applications

### Front End

Application types that has front end

* Web Apps
  * React
  * Angular
* Mobile Apps
  * Native
  * Hybrid
  * Cross Platform
* Desktop Apps
  * Windows: WinForm, WPF, UWP

#### Windows&#x20;

|                | WinForms | WPF       | UWP                            |
| -------------- | -------- | --------- | ------------------------------ |
| Founded        | 2001     | 2006      | 2015                           |
| UI Flexibility | Limited  | Unlimited | Unlimited but runs ina sandbox |
| Learning Curve | Short    |  Long     | Long                           |
| Runs on        | PCs      | PCs       | PCs, XBOX, IOT                 |

### Data Store

#### Data Store Types

* SQL
* No-SQL

#### SQL

* Stores data in tables
* Tables have concrete set of columns
* Tables have relationships with each other
* Transactions: Atomic set of actions&#x20;
  * ACID (Atomicity, Consistency, Isolation, Durability)
* Query: Uses SQL (Structured Query Language), Very Mature

When to use:

* When the data is not huge like < 10TB
* Structured Data
* Data consistency&#x20;

Any product would work. I Prefer Postgres

Note: Postgres and MS SQL Server - allows for JSON Query

#### NoSQL

* Emphasis on scale and performance
* Eventual Consistency: Data can be temporarily inconsistent
* Query: d

When to use:

* Data is huge
* Data is Un- or Semi- Structured

Note: MongoDB supports transactions (full ACID Support)



