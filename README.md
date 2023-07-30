# hello_flask
# Tutorial # 1 How to publish project from your own GitHub Repo in Azure
Prep 0: Clone Repo 

To clone the repository **`https://github.com/alfazick/hello_flask`** into your own GitHub repository, follow these steps:

1. Create an empty repository on your GitHub account. Let's say your new repository is named **`my_hello_flask`**.
2. Open a terminal or command prompt on your local machine.
3. Navigate to the directory where you want to clone the repository. You can use the **`cd`** command to change directories.
4. Run the following command to clone the original repository into your local machine:

```bash

git clone https://github.com/alfazick/hello_flask
```

1. This will create a new directory named **`hello_flask`** containing the cloned repository.
2. Now, navigate into the cloned **`hello_flask`** directory:

```bash

cd hello_flask
```

1. To change the remote URL from the original repository to your new repository, use the following command:

```bash

git remote set-url origin https://github.com/your_username/my_hello_flask.git

```

Replace **`your_username`** with your GitHub username.

1. Now, push the code to your new repository:

```bash

git push origin master
```

code from **`https://github.com/alfazick/hello_flask`** should now be cloned into your new repository **`https://github.com/your_username/my_hello_flask`**. You can verify this by going to your GitHub account and checking the new repository.

Remember to replace **`your_username`** with your actual GitHub username in step 7.
Block # 1) App Service Plan and App Service

1. **Create an App Service Plan**
    
    An App Service Plan defines a set of compute resources for a web app to run.
   These compute resources are analogous to the server farm in conventional web hosting.
    
    - Sign in to the **[Azure portal](https://portal.azure.com/)**.
    - On the left side, click on "Create a resource".
    - In the "Search the Marketplace" box, type "App Service Plan" and select it from the dropdown.
    - Click the "Create" button to start creating an App Service Plan.
    - Fill in the details:
        - **Subscription**: Choose your Azure subscription.
        - **Resource Group**: Choose an existing resource group or create a new one.
        - **Name**: Enter a unique name for the App Service Plan.
        - **Operating System**: Choose "Linux".
        - **Region**: Choose a region close to you or your customers.
        - **Pricing tier**: Choose a pricing tier based on your needs. For testing, you can choose the Free or Shared (F1 or D1) tier.
    - Click "Review + create" and then "Create" to create your App Service Plan.
3. **Create an App Service**
    
    Now that we have an App Service Plan, we can create an App Service. This is where your Flask application will run.
    
    - In the Azure portal, click on "Create a resource".
    - In the "Search the Marketplace" box, type "Web App" and select it from the dropdown.
    - Click the "Create" button.
    - Fill in the details:
        - **Subscription**: Choose your Azure subscription.
        - **Resource Group**: Choose the same resource group you used for the App Service Plan.
        - **Name**: Enter a unique name for the web app. This will form part of the URL for your Flask application
          (like **`https://<your-app-name>.azurewebsites.net`**).
        - **Publish**: Choose "Code".
        - **Runtime stack**: Choose "Python 3.8" or whichever version you need.
        - **Operating System**: Choose "Linux".
        - **Region**: Choose the same region as your App Service Plan.
        - **App Service Plan**: Choose the App Service Plan you created earlier.
    - Click "Review + create" and then "Create" to create your App Service.

Block # 2

**Deploy the GitHub repository to Azure App Service:**

- In the Azure portal, go to your Web App.
- Click on "Deployment Center" in the left-hand menu.
- For the "Source Control", choose "GitHub".
- Connect your GitHub account and choose your repository and branch.
- For the "Build Provider", choose "App Service Build Service".
- Click "Continue", review the summary, and then click "Finish".

After following these steps, your code should be deployed to Azure App Service, and you should be able to access your Flask app at the URL shown 
in the "Overview" tab of your Web App. This will look something like **`https://<your-app-name>.azurewebsites.net`**.
