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
