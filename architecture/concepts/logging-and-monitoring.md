# Logging And Monitoring

### Logging

The act of collecting and storing logs, useful information about events in your system. Typically your programs will output log messages to its STDOUT or STDERR pipes, which will automatically get aggregated into a centralized logging solution.

* Implemented via `Time Series` Database.

#### Technologies:

* Prometheus (Monitoring & Time Series DB) \[OSS]
* Grafana: Makes graphs from a time-series DB \[OSS]

#### Things to consider in a real-world problem:

* Rollup data

### Monitoring

The process of having visibility into a system's key metrics, monitoring is typically implemented by collecting important events in a system and aggregating them in human readable charts.



### Alerting

The process through which system administrators get notified when critical system issues occur. Alerting can be set up by defining specific thresholds on monitoring charts, past which alerts are sent to a communication channel like slack.



### Technologies we could use:

#### Sumo-logger:

* centralized logging system (For UI, APIs, etc.)
* You can query and filter logs.

**New Relic:**

* Logging and Monitoring

#### PagerDuty

Used for alerting. Supports Email and phone. People can be on rotation to be on "the call".

* Follow the sun, approach for globally distributed teams
