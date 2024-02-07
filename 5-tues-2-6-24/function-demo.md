## Inital Steps
1. Download and Install [Visual Studio Code](https://code.visualstudio.com/)
1. Install the Azure Functions extension (go to extensions, search in marketplace, and click install)
1. Make sure you have an Azure account

## Creating the Code
1. Using the newly installed Azure Functions extension, create a new function
  - Might need to right-click and enable the Azure extension
1. If you try to interact with the extension, you should be prompted to login to your Azure account
1. Under Workspace, create a Function
  - Choose a destination folder
  - Pick a language (Java)
  - Pick a version (17)
  - For Java, pick project details and package names
  - Pick a new function name or leave default
  - For Java, pick Maven/Gradle
1. After building project, should appear under workspace -> local project -> functions
1. Feel free to inspect the code
1. To test locally, first run the code and then under the workspace, right-click and "execute function now"
  - If this doesn't work, we can connect it to the resource that we will create and run it there

## Provisioning our Resource
1. Can allocate via the portal like normal or we can allocate via the extension
1. Go to "Resources" under your Azure extension, click the plus and choose "Create Function App in Azure".
  - Need globally unique name
  - Pick matching tech stack
  - Pick Region
1. When done, we can check the portal to see the new function as well as the extension
1. In the extension, can inspect the new function and if there is an error "bracnhDataProvier.getResourceItem..."
  - Delete .vscode folder and restart VSCode

## Connect our code to the service
1. Deploy the project by right-clicking the resource and select Deploy to Function App
  - Select the local folder where the code is stored
  - Alternatively, can do Ctrl-Shift-P and type "Deploy to Function App"
1. Test the function by right-clicking the resource and "Execute Function Now"
  - Do this in the "Resources" section and not the "Workspace" section
1. From command line, can run the following:
  - curl -d "HTTP Body" {your host}/api/HttpExample
  - curl "{your host}/api/HttpExample?name=HTTP%20Query"
  - Can grab the hose url from the resource on the portal
