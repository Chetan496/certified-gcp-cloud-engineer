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
