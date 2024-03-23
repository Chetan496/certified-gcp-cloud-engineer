# Infrastructure as Code

- It is a specification on how an environment should look like
- Provides a declarative approach on provisioning infrastructure

## Deployment Manager

- Provides repeatable deployments
- Uses .yaml templates or Python for describing our environment
- These templates can be stored and versioned in Cloud Source Repositories
- Deployment Manager provides version control, rollback capabilities, and preview functionality for infrastructure deployments.
- It supports creating, updating, and deleting resources across various Google Cloud services, such as Compute Engine, Cloud Storage, and Cloud SQL

## Cloud deployment manager (v2)
 - DM V2 is the next generation of Deployment Manager, built on top of the Google Cloud Resources Library (GCRL).
 - It supports defining infrastructure resources using the same YAML or Python configuration files as Deployment Manager, with improved performance and scalability.
 - DM V2 provides enhanced features like environment promotion, resource dependencies, and support for Terraform configurations.
