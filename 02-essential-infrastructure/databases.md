# Databases

## Cloud SQL

- It is a fully managed service of either MySQL, PostgreSQL or Microsoft SQL server
- Patches and updates are automatically applied
- We still have to manage and administer users for these databases
- Cloud SQL supports many clients:
    - `gcloud sql`
    - App Engine, Google Workspace scripts
    - Applications and tools:
        - SQL Workbench, Toad
        - External applications using standard MySQL drivers
- Cloud SQL high performance and scalability:
    - Up to 64 TB of storage
    - Up to 60_000 IOPS
    - Up to 624 GB or RAM per instance
    - Ability to scale out with read replicas
- Other Cloud SQL services:
    - HA configuration: primary-standby instances with synchronous replications
    - Backup service: automated and on-demand backups
    - Import/export
    - Scaling: up (change machine capacity), out (read replicas)
- Connecting to a Cloud SQL instance:
    - Same project in the same region: chose private IP connection for most performance and most secure
    - Other region, or from outside of GCP:
        - Recommended: use Cloud SQL proxy (offers key rotation)
        - Manual SSL connection
        - Connect from authorized network (if no SSL connection is available)

## Cloud Spanner

- It is a service built for the cloud to combine the benefits of relational structure with non-relational horizontal scale
- Can provide petabyte scale with transactional consistency at global scale
- Provides schemas, SQL and automatic replication for high availability
- Use cases include financial applications and inventory applications, traditionally served by relational databases
- Monthly uptime SLAs:
    - Regional: 99.99%
    - Multi-regional: 99.999%
- Cloud Spanner architecture:
    - Cloud Spanner replicates data in N cloud zones (on region or several regions)
    - Replication of data is synchronized through Google's global network
    - Uses atomic clocks to ensure atomicity
- Recommended when our data outgrown a traditional relational database

## Firestore

- It is a fast, fully managed, serverless, NoSQL document database
- Simplifies storing, syncing and querying data for mobile, web and IoT data at global scale
- Client libraries provide live synchronization and offline support
- Supports ACID transactions
- With automatic replication, data is safe and available even is case of disaster (multi-region replication)
- It offer a powerful querying engine
- Firestore is the next generation of Cloud Datastore. Firestore can operate in Datastore mode making it backwards compatible with Datastore
- Firestore removes some Datastore limitations such as:
    - Queries are no long eventually consistent
    - Transactions are no longer limited to 25 entity groups
    - Writes per entity are no longer limited to 1 per second
- Firestore in Native mode introduces the following features:
    - Strongly consistent storage layer
    - Collection and document data model
    - Real-time updates
    - Mobile and web client libraries
- General guideline is:
    - Use Firestore in Datastore mode for server applications
    - Use Firestore in Native mode for mobile and web apps