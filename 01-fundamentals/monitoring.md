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

 ## Log Sinks
  - Mechanism for exporting logs to different destinations
  - Destinations include:
     - Cloud Storage buckets
     - BigQuery datasets
     - Pub/Sub topics
     - Third-party services (via webhooks)
  - Allows log data to be processed, analyzed, or archived
  - Can filter logs based on various criteria (e.g., log type, severity, resource)
  - Supports real-time or batched export of logs

## Log Routing
 - Allows routing log entries to different destinations based on specific criteria
 - Destinations include Log buckets, Log sinks, Exclusions
 - Routing criteria can be based on log entry metadata (like severity or resource type) or log entry content
 - Enables separating logs for different purposes (e.g., debugging, security, compliance)
 - Multiple routing rules can be defined with different priorities
 - Supports advanced filtering and log processing capabilities
 - Can be managed via Cloud Console, gcloud, or Logging API
   


 
 - Log exclusions (excluding certain log entries)

