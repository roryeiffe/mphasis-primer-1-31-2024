## Steps
### Set up Resource
1. Go to the Azure Portal and look up "Storage Accounts"
1. On the Storage Accounts page, click "Create"
1. On the Create Page, fill out the following:
  1. Subscription
  1. Resource Group
  1. Name - must be globally unique across all storage accounts, only letters and numbers
  1. Region
  1. Performance - can keep standard
  1. Redundancy - Keep default
1. Navigate to the resource
1. Optional: To test out uploading files, can go to "Blob Service" and try creating a container and uploading some document
1. Enable Static Website hosting by going to the main overview of the service and clicking on capabilities -> static website
1. On the static website page, enable the feature
1. Enter names for the main page and error page (index.html, error.html)
1. Click save
1. A url should appear. You can try going there but the page will probably say "The requested website is not configured."

### Create a website
1. Create 2 files called "index.html" and "error.html"
  1. Make sure they match what you configured for the static website
1. Fill out with dummy data:
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>
  <h1>Hello this is a dummy web page!</h1>
</body>
</html>
```
1. Set up error page:
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>
  <h1>Hello this is a error web page! The route selected is probably invalid!</h1>
</body>
</html>
```
1. If you have an Angular or React project, you can build the app into an index and do the same thing.

### Deploy the website
1. Go back to the storage account overview
1. Go to blob service
1. You should see a folder called $web
1. Upload the index and error files to this folder.
1. Once the html files are uploaded, the website link should work
1. Try adding "/whatever" to the endpoint and see the error page