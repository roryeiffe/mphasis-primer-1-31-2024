## Scenario
- Shopping app with front-end and a back-end
- Need to store our data permanently 
- 2 back-end developers, 2 front-end developers, 1 Azure expert
- How do we set this up in Azure? What resources do we provision?

## Solution
- Utilize CI/CD
  - Continuous Integration - Each team individually can commit their code to a central repo
    - Could use Github or Azure
  - Continuous Delivery - building your project in a temporary spot and can do manual testing
    - Could use Github Actions or set up a pipeline in Azure Repos
  - Continuous Deployment - once changes are committed, and the tests/checks pass, then deploy to production
    - Github Actions/Azure Repos
  - Keep in mind that because back-end and front-end utilize different technologies, we will set up 2 repos, 2 builds, etc.
- Where do we store our data?
  - SQL Database - Structured and can store object-oriented data (items, users, reviews)
    - Can pick between any of the Azure SQL services offered like MySQL, PostgreSQL, etc.
      - When setting up a database, need to specify a username, password and you should get a connection string which we use to connect to our database from our back-end
- Back-End Application
  - Using the connection string that you get from the database service, we can use that in the back-end codebase to actually utilize that database
    - ex: For a spring app, we would put that info in application.properties (If this is a public repo, and for best practice, we can use Azure Secrets Manager to store these secrets)
  - For hosting, we have a few options
    - WebApp Service lets us connect our Github account and automatically configure the actions for us (PaaS)
    - Azure Virtual Machine which is just a virtual instance. We would have to do some manual environment setup including installing technologies and cloning the repo (IaaS)
    - Container Approach - AKS Azure Kubernetes Service to manage the deployment of containers
  - For the web app in particular, we get a generated link which is the endpoint for our back-end. 
    - Instead of just a Hello-World like we did in class, it can have many routes to add customers, get items, delete, etc...
- Front-End Application
  - Front-end Team works on their app, probably testing it with a local instance of the back-end to test or even some dummy data
  - But once the back-end is deployed and they have an endpoint, can then access it from the front-end
    - Axios/HttpClient can consume endpoints
      - Aside: Will probably need to enable CORS from the back-end (enables a web page to access it without throwing an access error)
    - Now, can host it on Blob Storage as a static website
      - Even if you're working with Angular or React or some other library/framework, can build the project into an index.html so we can host it in the same way as a very simple index.html (as long as we upload all of the helper JS files)

## Services Used:
- Github/Azure Repos - CI/CD
- Azure MySQL - hosting database -> connection string
- Web App - deploy the back-end code -> endpoint
- Storage Account - Blob - hosting the front-end code -> link
- Azure Key Vault - store secrets such as database passwords/connections


## How to implement Solution Using ARM Templates
1. Log on to Azure Portal
1. Search "Template" and "Deploy a Custom Template"
1. Can pick a pre-made template or start from scratch
  - Wouldn't hurt to go through some of the pre-made templates to understand what's going on and the general format of these templates
1. Build your own template
1. Can select a resource from the "Add Resource" drop-down and fill in the parameters
1. The template code should be updated automatically
1. Add more services until you have everything you need for your app
1. Once done setting up the blueprint for our app, hit save, then review + create
1. The resources should be created based on the blue print


## Template Specs
- Can upload our own template and store them
- Can create a spec, give name, description, version, etc.
- Fill out the template code and then create
- Go to resources to view template
- Once the template is created, should have the option to deploy all of the services that are configured in the template