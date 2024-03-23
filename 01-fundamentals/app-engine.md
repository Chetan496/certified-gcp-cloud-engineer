# App Engine

- App Engine is a PaaS (Platform-as-a-Service) offering. It is a serverless platform.
- The App Engine service managed the hardware and the networking infrastructure
- App Engine provides built-in services that many web-application need, such as NoSQL databases, in-memory caching, logging, health checks, load balances, etc.
- We only pay for resources that we use, App Engine is recommended for application where load is highly variable. App Engine uses a pay-as-you-go pricing model based on resource usage, such as instance hours, network egress, and storage.
- App Engine provides built-in services like Memcache (in-memory caching), Task Queues (for asynchronous task execution), and Cron Service (for scheduling background tasks).
- App Engine offers two environment configurations: Standard Environment and Flexible Environment. The Standard Environment is a more managed and restricted environment, while the Flexible Environment provides more control and customization.
- Applications can be deployed to App Engine using various methods, including the Google Cloud Console, the gcloud command-line tool, or continuous deployment through Cloud Build.
- App Engine supports traffic splitting, allowing you to serve different versions of your application to a specific percentage of incoming traffic.
-  App Engine allows you to configure warm-up requests to ensure your instances are ready to serve traffic after scaling or deployment.
-  App Engine integrates with Google Cloud's monitoring and logging services, providing detailed insights into your application's performance and behavior.
-  App Engine supports authentication and authorization through Google Cloud Identity and Access Management (IAM), as well as OAuth 2.0 and OpenID Connect.
-  App Engine seamlessly integrates with other Google Cloud services, such as Cloud Storage, Cloud Datastore, Cloud SQL, and Cloud Tasks, allowing you to build comprehensive applications.
-  App Engine enforces various quotas and limits on resource usage to ensure fair distribution and prevent abuse. Understanding these quotas and limits is essential for proper application design and deployment.
-  App Engine offers several options for data persistence, including Cloud Datastore (a NoSQL document database), Cloud SQL (a fully-managed relational database service), and Cloud Storage (an object storage service).
-  App Engine supports deploying applications across multiple regions and locations, enabling you to better serve users worldwide and improve application availability.

## App Engine Standard Environment

- Offers a simple deployment experience compare to the Flexible Environment. It is more restricted than flexible app engine.
- Offers fined-grained autoscaling
- Offers free daily usage quota (low usage service may run at no charge)
- Google provides several SDKs for development and deployment on AppEngine. We can test the application locally before uploading it to the AppEngine Service
- AppEngine runtimes: specific versions of Java, PHP, Python, Go, .NET and Node.js
- For other languages we may want to consider the Flexible Environment
- Sandbox: software construct independent of the hardware. Constraints:
    - No writing to local files
    - All requests time out in 60 seconds
    - Limits in third-party software

## App Engine Flexible Environment

- Instead of the sandbox, we can specify the container the App Engine is running on
- App Engine manages the containers, we get to chose where they are running
- App Engine applications can access GC services such as data stores, memory caches, task queues, etc.

## App Engine Standard vs Flexible Comparison

|                            | App Engine Standard                                                   | App Engine Flexible                                         |
|----------------------------|-----------------------------------------------------------------------|-------------------------------------------------------------|
| Instance startup           | Milliseconds                                                          | Minutes                                                     |
| SSH access                 | No                                                                    | Yes (not by default)                                        |
| Write to local disk        | No                                                                    | Yes (ephemeral writes only)                                 |
| Support 3rd party binaries | No                                                                    | Yes                                                         |
| Network Access             | Via App Engine services                                               | Yes                                                         |
| Pricing Model              | After free daily use, pay per instance class, with automatic shutdown | Pay for resource allocation per hour, no automatic shutdown |

## App Engine Config Files

- `app.yaml`: defines our configuration settings for our runtime as well as general app, network, and other resource settings
- `cron.yaml`: a cron.yaml file should in the root directory of your application (alongside app.yaml) and configures scheduled tasks for our applications
- `dispatch.yaml`:  allows us to override routing rules. We can use the dispatch.yaml to send incoming requests to a specific service (formerly known as modules) based on the path or hostname in the URL
- `index.yaml`: we can use Firestore in Datastore mode (Datastore) for storing data for our applications that run in the flexible environment. We define indexes our app needs in a index.yaml configuration file

## App Engine IAM Roles

- App Engine Admin (`roles/appengine.appAdmin`):
    - Read/Write/Modify access to all application configuration and settings
    - To deploy new versions, a principal must have the Service Account User (roles/iam.serviceAccountUser) role on the App Engine default service account, and the Cloud Build Editor (roles/cloudbuild.builds.editor) and Cloud Storage Object Admin (roles/storage.objectAdmin) roles on the project
- App Engine Creator (`roles/appengine.appCreator`):
    - Ability to create the App Engine resource for the project
- App Engine Viewer (`roles/appengine.appViewer`):
    - Read-only access to all application configuration and settings
- App Engine Code Viewer (`roles/appengine.codeViewer`):
    - Read-only access to all application configuration, settings, and deployed source code
- App Engine Deployer (`roles/appengine.deployer`):
    - Read-only access to all application configuration and settings
    - To deploy new versions, you must also have the Service Account User (roles/iam.serviceAccountUser) role on the App Engine default service account, and the Cloud Build Editor (roles/cloudbuild.builds.editor) and Cloud Storage Object Admin (roles/storage.objectAdmin) roles on the project
    - Cannot modify existing versions other than deleting versions that are not receiving traffic
- App Engine Service Admin (`roles/appengine.serviceAdmin`):
    - Read-only access to all application configuration and settings
    - Write access to module-level and version-level settings. Cannot deploy a new version
