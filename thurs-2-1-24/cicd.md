## CI/CD
Organizing and automating the development process. From planning/design to development all the way to production. Steps involved include testing, building deploying to production. The more we automate, the more we can focus on the code itself.

Going through each step of the pipeline, we see the steps build off of one another.

We can have CI on its own. But, in order to achieve Continuous Delivery, we must have Continuous Integration. In order to have Continuous Deployment, we must have the previous steps.

### Continuous Integration
Think of a common source where all the developed code is merged into. Github is a very popular example of this. We write code, commit/push it to the repository so we have this centralized location for the source code. It helps to detect problems early and iron out bugs as they come up ( as opposed to writing a bunch of code and then merging all at once). 

The best practice is to continuously integrate smaller changes. 

### Continuous Delivery
As we integrate the code into the central repository, we can continuously deliver the packaged app to a temporary stage where we can run tests, even manual tests. This gives the process a place to pause, test out whatever needs to be tested and then the option to deploy to some public endpoint is doable through "the push of a button". 

### Continuous Deployment
Every step of the process is automated. At this point, any change that is committed, should be thoroughly tested and, as long as the tests pass, should be automatically pushed to production. 

This is why it's important to write good tests. 

## Services
### Azure Web App
A service that lets us configure a code-base (web application that takes requests over HTTP), deploy as a web service, and can also scale depending on demand. All we have to worry about is setting up our code in a repository, pick whatever tech stack(Java, Python, .NET, PHP) we used, and Azure handles the rest. 

Is Azure Web App a SaaS, PaaS, IaaS? PaaS, we are writing our own application (Spring Web App) so it is not a SaaS. And, we don't need to manage our own environment/platform, so it is not IaaS. 

### Azure Functions
A serverless service that lets you run code without a dedicated server to be running. You can just plop some code into the service and configure the code to run based on certain events such as:
- Upload a file to BLOB Storage (another Azure Service that stores data)
- An HTTP request
- When a document is loaded in Azure Cosmos DB (which is a document-based storage approach that Azure offers)

### Logic Apps
Let you build workflows without writing much code, if it all. It's referred to as low-code/no-code. 

- Benefits - 
  - Low Code/No Code - visual interface which lets you drag and drop pieces of your workflow, without having to write code
  - Scalability - Workflows can scale to meet your workload needs
  - Flexibility - Integrate with different services across private cloud (on-premise), public, or hybrid
  - Security and Compliance - built-in security features

### Azure Repos
Azure's version of Git. You can create repos, branches, pull requests. It's a version control system that lets you manage/track your changes to your code. You can set up Pipelines similar to Github Actions. 

## Data-Centered Services

### Quick Terms

#### Data Governance
THe practice ot managing data, ensuring its secure. It includes the processes, policies, standards, that are put in place to make sure the data is regulated, accurate, consistent, secure.

#### Data Security
Protecting data from unauthorized access/use. Personal data, for example, should not be publicly available. Sensitive data that is stored should not be attainable from outside parties. 

#### Risk and Compliance
Mitigating risk, ensuring compliance with regulations and standards. 

### Data Lake Storage
A data lake is a collection of large amounts of data in a variety of formats. It's a centralized location for the data to sit and it can store structured data or unstructured data. Because it's all in one place it's easier to manage. 

Azure Data Lake Storage is Azure's cloud-based approach. It sets a foundation for the other services that we will talk about. 

### Azure Databricks
Built on Apache Spark. Used for large-scale data processing and analytics. Flexible - can run a lot of different types of workloads such as machine learning, data engineering, and interactive analytics. 

### HDInsight
Lets us run big data workloads. Includes access to different big data technologies such as Hadoop, Spark, and Kafka. Good option for those who have worked with these technologies as well as wanting control over configuration of clusters. 

### Azure Data Explorer
Analyzing large amounts of data in real-time to gain insights. Uses machine learning to extract insights, identify patterns, and create forecasting models. Characterized by high velocity and high volume. 

Uses Kusto Query Language (KQL) to query data. KQL is read-only. 

Use cases for Azure Data Explorer - log analysis, time series data, and ad-hoc queries

### Microsoft Purview (Azure Purview)
Unified solution that lets you manage, catalog, classify, understand, govern your data. Capabilities include governance, security, risk, and compliance.

### Azure Stream Analytics
A real-time analytics service that processes data in real-time. Can identify patterns and relationships in data. 

Use Cases - IoT, real-time fraud detection, and real-time monitoring


## Resources
- [Purview](https://learn.microsoft.com/en-us/purview/)
- [Azure Functions](https://learn.microsoft.com/en-us/azure/azure-functions/)
- [Azure Logic Apps](https://learn.microsoft.com/en-us/azure/logic-apps/logic-apps-overview)
- [Azure Data Explorer](https://learn.microsoft.com/en-us/azure/data-explorer/data-explorer-overview)
- [Data Lake Storage](https://learn.microsoft.com/en-us/azure/storage/blobs/data-lake-storage-introduction)
- [Azure Stream Analytics](https://learn.microsoft.com/en-us/azure/stream-analytics/stream-analytics-introduction)
- [Azure Repos](https://learn.microsoft.com/en-us/azure/devops/repos/?view=azure-devops)
- [Azure Insights](https://learn.microsoft.com/en-us/azure/hdinsight/spark/apache-spark-jupyter-spark-sql-use-portal)