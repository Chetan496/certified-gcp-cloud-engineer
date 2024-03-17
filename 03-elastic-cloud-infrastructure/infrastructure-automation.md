# Infrastructure Automation

## Terraform

- Infrastructure as code (IaC) tool, allowing us to quickly provision and remove infrastructures
- It provides the following features:
    - A repeatable deployment process
    - A declarative language
    - Parallel deployments
    - Template-drive infrastructure
 
## Deployment manager:
It is IAC service native to Google cloud platform. You can define IAC code in YAML or Python template files.

You can also add a -preview to the deployment manager to preview what changes its going to do.   
Aside: One advantage of using google cdn is you get SEO automatically   
Also refer for [cloud foundation toolkit](https://cloud.google.com/foundation-toolkit) to understand about the deployment best practices across different environments.


## Google Cloud Marketplace

- Let's us quickly deploy production-grade solutions from third party vendors, who already made their deployment configurations based on Terraform
- Google Cloud automatically updates the images provided on the marketplace, but it does not upgrade already deployed infrastructure
- Google Cloud Marketplace provides direct access to partner support
