# Big Data and Machine Learning

## Google Cloud Big Data Services

- They are serverless services, managed by Google
- Services:
    - Cloud Dataproc (managed Hadoop):
        - Is an open-source framework for big data
        - It is based on the map-reduce programming model
        - Dataproc is a fast and easy managed way to run Hadoop, Spark, Hive and Pig on GCP
        - A cluster can be created in 90 seconds or less
        - We can scale up and down jobs on the fly
        - We pay only for hardware resources used during the life of the cluster (billing is done down to second)
        - We can save money by using preemptible compute instances (up to 80% cheaper)
    - Cloud Dataflow:
        - It is an unified programming model and managed service
        - It can be used for ETL, batch processing, stream processing
        - We use Dataflow to create data pipelines used for batch processing and streaming purposes
        - Orchestration: we can create pipelines that coordinate services, including external services
        - Dataflow integrates with Cloud Storage, Pub/Sub, BigQuery and BigTable
    - BigQuery:
        - Ad-hoc SQL queries on massive datasets
        - Provides near real-time interactive analysis of massive datasets
        - It is a fully managed, low cost, petabyte scale data warehouse
        - No cluster maintenance is required
        - It lets us specify the region where the data will be kept, compute and storage is separated with terabit network in-between
        - We only pay for storage and processing used
        - Provides automatic discount for long-term data storage (after 90 days)
    - Cloud Pub/Subs:
        - It is meant to serve as a simple, reliable, scalable foundation for stream analytics
        - Publishers and subscribers are completely decoupled, meaning they don't need to know about each other's existence or location. This allows for loose coupling and independent scaling of publishers and subscribers
        - Subscribers don't continuously receive messages; instead, they pull (poll) messages from their subscriptions asynchronously, either manually or through a configured pull schedule.
        - Cloud Pub/Sub supports push subscriptions, where messages are pushed to a webhook or Cloud Function asynchronously as they become available, without the subscriber actively polling for messages
        - Cloud Pub/Sub guarantees at-least-once delivery of messages, ensuring that no message is lost, even in the event of failures or restarts.
        - While Cloud Pub/Sub provides ordering guarantees for messages within the same publisher, the order in which subscribers receive messages is not guaranteed, as subscribers can process messages at different rates.
        - It is great for decoupling systems
        - It is designed to provide at least once delivery at low latency (some messages might be deliver more than once)
        - It is recommended to be used of systems where data arrives at high and unpredictable rates (example IOT)
        - We can configure subscribers to receive messages on a push or pull basis
        - asynchronous messaging architecture is particularly useful in scenarios such as event-driven architectures, real-time data processing pipelines, and distributed microservices-based applications, where components need to communicate and exchange data in a decoupled and reliable manner.
    - Cloud Datalab:
        - Built on project Jupyter, it provides managed lab notebooks
        - It lets us create web based notebooks containing Python code
        - We only pay for the resources used for the compute
        - Data can be visualized with Google Charts of Matplotlib
    - Cloud data fusion:
        - Fully managed data integration service by Google Cloud
        - Visual interface for building ETL pipelines without code
        - Pre-built connectors for various data sources
        - Supports hybrid and multi-cloud deployments
        - Scalable and high-performance processing
        - Integrates with Google Cloud services like BigQuery and Dataflow
        - Includes data transformation and cleansing functionalities
        - Monitoring, management, and security features
        - Cost-effective pay-as-you-go pricing model
        
## Cloud Machine Learning Platform

- Google Machine learning solutions as a managed service
- Tensorflow:
    - Open source tool to build and run neural network models
    - It has wide platform support
- We can run Tensorflow on GCP ML Platform
- Tensorflow can take access of Tensor processing units provided by GCP
- Google Cloud Machine Learning Engine:
    - Fully managed machine learning service
    - Optimized ofr Google infrastructure, integrates with BigQuery and Cloud Storage
- Cloud Vision API:
    - Managed platform used to understand the content of an image
    - Can quickly classify images
    - Can provide sentiment analysis and text extraction
- Cloud Speech API:
    - Convert audio to text
    - We can transcribe audio files to text
- Cloud Natural Language API:
    - Uses machine learning models to reveal structure and meaning from text
    - Can extract information about items mentioned in text documents, news articles and blog posts
- Cloud Translation API:
    - Translate arbitrary text into another language
- Cloud Video Intelligence API:
    - Can be used to annotate contents of videos
    - Can detect scene changes
    - Can be used to flag inappropriate content
    - Supports a variety of video formats
