# Cloud Functions

- Cloud Functions is a serverless computing platform designed to run single-purpose pieces of code in response to events in the GCP environment
- There is no need to provision or manage VMs, containers, or clusters when using Cloud Functions
- Cloud Functions provides the "glue" between services that are otherwise independent

## Cloud Functions Execution Environment

- The functions execute in a secure, isolated execution environment
- Compute resources scale as needed to run as many instances of Cloud Functions as needed without you having to do anything to control scaling
- The execution of one function is independent of all others. The lifecycles of Cloud Functions are not dependent on each other
- By default, the functions will time out after one minute, although we can set the timeout for as long as 9 minutes
- Note: In Cloud Functions (2nd gen), the maximum timeout duration is 60 minutes (3600 seconds) for HTTP functions and 9 minutes (540 seconds) for event-driven functions.
- Cloud Function Runtimes:
    - NodeJS
    - Java
    - .NET
    - Ruby
    - Python
    - Go
    - .NET Core
 
## Cloud Functions V1 vs Cloud Functions V2

| Feature                | Cloud Functions V1                                  | Cloud Functions V2                             |
|------------------------|-----------------------------------------------------|------------------------------------------------|
| Runtime Environment    | Uses Node.js, Python, and Go runtimes              | Adds support for additional runtimes like Ruby, Java, .NET |
| Networking             | Limited to HTTP(S) triggers                        | Adds support for Eventarc for event-driven architecture |
| Stateful Functions     | Stateless functions only                           | Adds support for stateful functions with stateful invocations |
| Execution Environment | Runs on Google-managed infrastructure              | Offers choice between Google-managed or self-managed infrastructure |
| Dependency Management  | Manually manage dependencies                       | Supports dependency management with built-in package managers |
| Scaling                | Automatic scaling based on incoming traffic        | Introduces new scaling options and customization |
| Timeout                | Maximum configurable timeout of 540 seconds        | Maximum configurable timeout of 540 seconds for HTTP functions, and 5400 seconds for non-HTTP functions |
| Pricing Model          | Based on execution time and resources consumed     | Similar pricing model, but may differ for certain features |
| Event Sources          | Limited event sources (HTTP, Pub/Sub, Cloud Storage) | Expands support for various event sources and integrations |


