1. **gcloud auth login**: Authenticate to Google Cloud Platform. This command prompts you to log in with your Google Cloud credentials.
2. **gcloud auth revoke** : logout/invalidate the credentials

3. **gcloud config set project [PROJECT_ID]**: Set the default project for the current configuration.

4. **gcloud config list**: List all properties in the current configuration.

5. **gcloud config set compute/zone [ZONE]**: Set the default compute zone for the current configuration.

6. **gcloud config set compute/region [REGION]**: Set the default compute region for the current configuration.

7. **gcloud config set core/account [ACCOUNT]**: Set the default account for the current configuration.

8. **gcloud config set core/project [PROJECT_ID]**: Set the default project for the current configuration.

9. **gcloud projects list**: List all projects accessible to the current authenticated user.

10. **gcloud projects describe [PROJECT_ID]**: Describe a specific project.

11. **gcloud projects create [PROJECT_ID]**: Create a new project.

12. **gcloud projects delete [PROJECT_ID]**: Delete a project. (Note: This is irreversible and should be used with caution.)

13. **gcloud projects describe [PROJECT_ID]**: Describe a specific project.

14. **gcloud billing accounts list**: List all billing accounts associated with the current authenticated user.

15. **gcloud billing projects link [PROJECT_ID] --billing-account=[BILLING_ACCOUNT_ID]**: Link a project to a billing account.

16. **gcloud iam service-accounts list**: List all service accounts in the default project.

17. **gcloud iam service-accounts create [NAME]**: Create a new service account.

18. **gcloud iam service-accounts keys create**: Create a new service account key.

19. **gcloud iam service-accounts delete [EMAIL]**: Delete a service account.

20. **gcloud iam service-accounts keys list**: List all keys for a service account.

21. **gcloud iam service-accounts keys delete [KEY_ID]**: Delete a key for a service account.

22. **gcloud iam service-accounts add-iam-policy-binding [EMAIL] --role=[ROLE] --member=[MEMBER]**: Add an IAM policy binding to a service account.

23. **gcloud iam service-accounts remove-iam-policy-binding [EMAIL] --role=[ROLE] --member=[MEMBER]**: Remove an IAM policy binding from a service account.

24. **gsutil ls**: List all buckets in Google Cloud Storage.

25. **gsutil cp**: Copy files and objects to and from Google Cloud Storage.

26. **gsutil mb**: Create a new bucket in Google Cloud Storage.

27. **gsutil rb**: Remove a bucket from Google Cloud Storage.

28. **gsutil rm**: Remove objects or buckets from Google Cloud Storage.

29. **gsutil mv**: Move files and objects within Google Cloud Storage.

30. **gsutil acl**: Update access control lists for objects and buckets in Google Cloud Storage.

31. **gcloud container clusters list**: List all Kubernetes Engine clusters in the default project.

32. **gcloud container clusters get-credentials [CLUSTER_NAME]**: Set up kubectl access to a Kubernetes cluster.

33. **gcloud container clusters describe [CLUSTER_NAME]**: Describe a Kubernetes cluster.

34. **gcloud container clusters create**: Create a new Kubernetes Engine cluster.

35. **gcloud container clusters delete**: Delete a Kubernetes Engine cluster.

36. **gcloud container clusters resize**: Resize the number of nodes in a Kubernetes Engine cluster.

37. **kubectl apply -f [CONFIG_FILE]**: Apply a configuration file to create or update Kubernetes resources.

38. **kubectl get pods**: List all pods in a Kubernetes cluster.

39. **kubectl get services**: List all services in a Kubernetes cluster.

40. **kubectl describe pod [POD_NAME]**: Describe a specific pod in a Kubernetes cluster.

## Interacting with Cloud SQL and BigQuery
- **gcloud bigquery datasets list**: List all datasets in the default project.

- **gcloud bigquery datasets describe [DATASET_ID]**: Describe a specific dataset in BigQuery.

- **bq ls [PROJECT_ID]:[DATASET_ID]**: List all tables in a dataset using the BigQuery command-line tool (bq).

- **bq show [PROJECT_ID]:[DATASET_ID].[TABLE_ID]**: Describe a specific table in BigQuery using the BigQuery command-line tool (bq).

- **bq query --use_legacy_sql=false '[SQL_QUERY]'**: Run a SQL query against BigQuery using the BigQuery command-line tool (bq).

- **gcloud sql instances list**: List all Cloud SQL instances in the default project.

- **gcloud sql instances describe [INSTANCE_NAME]**: Describe a specific Cloud SQL instance.

- **gcloud sql databases list --instance=[INSTANCE_NAME]**: List all databases in a Cloud SQL instance.

- **gcloud sql databases describe [DATABASE_NAME] --instance=[INSTANCE_NAME]**: Describe a specific database in a Cloud SQL instance.

- **gcloud sql users list --instance=[INSTANCE_NAME]**: List all users in a Cloud SQL instance.

- **gcloud sql users describe [USERNAME] --instance=[INSTANCE_NAME]**: Describe a specific user in a Cloud SQL instance.

- **gcloud sql connect [INSTANCE_NAME]**: Connect to a Cloud SQL instance using the MySQL client.

- **gcloud sql connect [INSTANCE_NAME] --user=[USERNAME]**: Connect to a Cloud SQL instance using a specific user.
