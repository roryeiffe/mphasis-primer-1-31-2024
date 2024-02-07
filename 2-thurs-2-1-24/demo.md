## Creating a Web App
### Creating our Application
- In this case, we can make a Spring (Java) application. 
- Go to start.spring.io, 
  - Use Java 17
  - Use Maven
  - JAR
  - 17
  - dependencies:
    - Spring Web
- Download, extract, and open up in an IDE
- Set up a simple controller with an endpoint that is blank/default
- Make sure to test locally with localhost:port
- Optional: Set up a test that can pass or fail so we can test out our pipeline later

### Hosting our App on Github/Version Control System
- Either initialize a repo, manually add the remote
- Some IDE's have a special option to push code as a repo
- Could clone from my repo: https://github.com/roryeiffe/web-app-2-1-2024/ 
  - NOTE: If there is .github folder, there will be stuff in there that you will want to change/delete
- At this point, we have Continuous Integration

### Spinning up a WebApp service on Azure
- Go to App Services
- Click create -> Web App
- Create Page - 
  - Subscription + Resource Group
  - Name - must be globally unique (can add numbers + name to make it unique)
  - Select "Code" radio button
  - Runtime Stack - pick Java 17 (this matches what our project was created as)
  - Select Embedded Server (we picked JAR)
  - OS - can leave default
  - Region - pick what's closest to you
  - Linux Plan - leave default
  - PRICING PLAN - PICK FREE
- Under the deployment tab, you can link up your Github account and select what repo you're actually hosting
  - Can also change this after the fact in "Deployment Center"

### Connecting Web App Service to Repo
- Once your service is up and running (deployed), we can inspect it and pay attention to a few things:
  - Default Domain - where the site will be hosted
  - Deployment Center - Where we configure our connection to our repo
    - Select Code Source - Github
    - Should prompt you to log in to your Github
    - Select your organization, repo, and branch
      - For repo, might have to type in the name
      - Whenever we push/update the specified branch on the repo, a new deployment should get triggered
    - Can leave Authentication Settings as default
- Take a peek at the preview file for Github Actions
  - Note the use of secrets
  - Try to determine the workflow
- Save
- Go back to Github and note the changes on the Repo and note the action in progress
- In Github actions, can see the build + deploy stages running
  - Public endpoint should show up: https://web-app-rory.azurewebsites.net/ 
  - Can also access the endpoint from Azure

### Testing out the Pipeline
- Try changing the code and pushing again to master/main
- A new action should automatically start and after it finishes, you should see the change
  - Might need to wait a few minutes for the change to appear or use an incognito/private tab
- Try to push with a failing test and ensure that the change doesn't go through.

### Cleaning Up
- Navigate to the resource, click delete, and type whatever confirmation message is required.
- Can also go to "All Resources" and delete all resources with the same resource group