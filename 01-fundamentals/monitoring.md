# Monitoring

## Cloud Logging
- Was previously known as StackDriver. Now renamed to Cloud Logging
- It is the tool provided by GCP for monitoring, logging and debugging
- It gives insides to application health, performance and availability
- Stackdriver Logging lets define metrics based on logs. These metrics can be displayed on dashboards 
- Stackdirver Error Reporting: tracks errors in applications and it can notify us when new errors are detected
- Stackdriver Trace: report on application latency and sampling
- Stackdriver Debugger: it connects application production data to the source code for inspecting application state
- Supports various logging agents (e.g., Stackdriver Logging agent, Fluentd) for log collection
- Pricing based on log ingestion volume, log storage, and log exports
- Access control governed by IAM roles and permissions

## Core components of Cloud logging
Core components:
 - Log entries (metadata and payloads)
 - Log sinks (exporting logs to destinations like BigQuery or Cloud storage)
 - Log buckets (organizing and managing logs)
 - Log viewers (filtering and searching logs)
 - Log routing (sending logs to specific destinations)
 - Log exclusions (excluding certain log entries)

