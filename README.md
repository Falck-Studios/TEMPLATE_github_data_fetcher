# TEMPLATE_github_data_fetcher

For this to run as expected you need to do the following steps:

__1. Create GitHub App__

You'll need to create a GitHub App to be abe to fetch the usage of GitHub Copilot. 

Go to `Org. Settings -> Developer Settings -> GitHub Apps -> New GitHub App`.

The Application needs the organization permission read-only on _GitHub Copilot Business_.
Webhooks can be deacivated. 

__2. Install the GitHub App on your organization__

Once you have created the app, make sure you install it on your organization.

__3. Create a private key__

Create a private key for your GitHub App. Go to the settings of the GitHub App -> General -> under Private Keys -> create new private key. Download the key, we will need the content later.

__4. Set repository secrets and variables__

You'll need to create one variable and one secret. 
`Repository settings -> Security -> Secrets and Variables -> Actions -> Secrets or Variables`

Variable: 

Name: _APP_ID_

Value: _Paste the APP Id of your GitHub App_

Secret:

Name: _APP_PRIVATE_KEY_

Value: _Full content of your private key file_

__5. Change the workflow to use the result__

This contains a workflow that fetches the usage of GitHub copilot for your organization. 
This is then outputted to a file called `copilot-metrics.json`, if you want to persist or use this data you have to implement the function for doing so. 

That could be to upload it to a blob storage, database etc.
