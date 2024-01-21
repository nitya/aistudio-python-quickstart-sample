# 04 | Provision Azure

!!!warning "Screenshots may not be exactly the same as your experience"
    Screenshots were captured with a GitHub Codespaces environment, and may have been refreshed in different sections to reflect changes made to the codebase or updates to the tools. While the details may have small variations, **the process and expected outcomes should remain consistent**.

In this step we'll setup the top-level **Azure AI Resource** and provision it with the required **Azure AI Project**, **Azure OpenAI Service** and **Azure AI Search** service capbilities, with a single command!!

1. Run the following command.

    ```
    ai init
    ```

    You should see an interactive wizard that walks you through the process of creating an Azure AI project and provisioning the required Azure AI resources. **This can take a few minutes to complete**.
    ![Ai init](./img/05-ai-init.png)


1. If you are not already logged into your Azure account, you will be prompted to do so at this time. Choose the interactive option.

    ![Az Login](./img/06-az-login.png)

   You will be given a code to enter in a browser to complete the authentication flow. If successful, you should see this message. Return to the terminal to continue the init process. 
    
    ![Az Login](./img/07-az-signedin.png)

1. Next, you will be prompted to create the Azure AI Resources for the project you are setting up. The process will include setting up a resource group and Azure AI project resource, then adding a new Azure Oen AI Deployment (Chat model) including the region and OpenAI model deployments for chat (`gpt-35-turbo-16k-0613`) and embeddings (`text-embedding-ada-002-2`).

    ![Ai init](./img/08-ai-resource.png)

1. Next, you will be prompted to create the Azure AI Search resource - I opted to have this be created in the same region as the other resources, and associated with the same resource group for convenience. You should now see a `config.json` file created with the following properties, with values set by your project.

    ```json
    {
        "subscription_id": "your_subscription_id",
        "resource_group": "your_resource_group",
        "project_name": "your_project_name"
    }
    ```

5. Your Azure AI Project is ready. Visit [Azure AI Studio](https://ai.azure.com) and look under the `Manage` tab for the Azure AI resource created. Click to see details as shown below - including a handy link to the Azure Portal for additional actions and information.

    ![Ai Studio](./img/09-ai-studio.png)

## Next Steps

🟩 Congratulations! Our Azure AI project is ready. Now, it's time to build the Azure AI Search index for our product data, and use it for Retrieval Augmented Generation in our copilot.

!!!abstract "Next Up: [**Populate Data & Indexess**](./05-search.md)"

