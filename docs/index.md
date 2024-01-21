# Quickstart - Python SDK

!!!warning "Azure AI Studio is currently **In Preview**"
    **Preview versions are provided without a service level agreement, and they are not recommended for production workloads. Certain features might not be supported or might have constrained capabilities. For more information, see [Supplemental Terms of Use for Microsoft Azure Previews](https://azure.microsoft.com/en-us/support/legal/preview-supplemental-terms/).**


## What You'll Learn

This repository contains the starter code and step-by-step quickstart tutorial for building a copilot with your own data, using the [Azure AI Studio preview](https://learn.microsoft.com/azure/ai-studio) and related tooling ecosystem. By the end of this exercise, you should be familiar with the following tools and their usage for building a RAG-based LLM application and deploying it to Azure.

* [**Azure AI Studio**](https://learn.microsoft.com/azure/ai-studio) - build, evaluate & deploy AI solutions from one space.
* [**Azure AI services**](https://learn.microsoft.com/azure/ai-services/what-are-ai-services) - AI models & APIs accessible from Azure AI Studio.
* [**Azure AI SDK**](https://learn.microsoft.com/azure/ai-studio/how-to/sdk-install) - access to Azure AI services from code (programmatic).
* [**Azure AI CLI**](https://learn.microsoft.com/azure/ai-studio/how-to/cli-install) - access to Azure AI services from command-line (shell).


## What You'll Build

In this quickstart sample you'll build a **enterprise copilot app**, using a _Retrieval Augmented Generation_ pattern to ground the chat agent's responses in your company's data and APIs. The sample is not meant for production use, but as a starting point for you to explore further customization of features and functionality, to support your own application requirements.

Follow the steps in our [**quickstart tutorial**](./01-start.md) to learn how to:

 - **Setup Environment**: for development, using pre-built or custom options
 - **Provision Azure**: create Azure AI resources and project to build the copilot
 - **Provision Data**: create an Azure Search index containing product information
 - **Run Copilot**: test your copilot with a sample question to validate operation
 - **Evaluate Metrics**: assess copilot quality using relevant metrics

In the process, you'll learn to use three tools that form the basis of the Azure AI Platform.

 - **Azure AI Studio** - For browser-based interactions with the Azure AI platform.
 - **Azure AI CLI** - For commandline interactions with the Azure AI platform.
 - **Azure AI SDK** - For code-based interactions with the Azure AI platform.

Plus, you'll learn to use the **Azure AI CLI** to simplify your setup process. And you'll learn to use the **Azure AI SDK** (from Python code or from Jupyter Notebooks) to interact programmatically with the Azure AI Platform (during development), and with your copilot (on deployment).

!!!danger "THIS IS NOT A PRODUCTION SAMPLE"

    We do not guarantee the quality of responses produced by this sample copilot or promote its suitability for use in your real-world production deployments. The copilot responses may vary over time as features and functionality of various components evolves. You must perform your own evaluation of copilot response quality to assess suitabilty for your specific use case or solution integration if you choose to repurpose the sample.


## Getting Started

Building the copilot requires setting up a few tools, libraries and extensions for the Azure AI and Visual Studio Code development environments. The quickest way to get started is to use our _pre-build development container_ which does all of this for you behind the scenes. Just log into GitHub and click the button below to launch GitHub Codespaces. 

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/Azure-Samples/aistudio-python-quickstart-sample?quickstart=1)

Re-open this file in the Visual Studio Code session in that environment. You can now continue the quickstart by picking one of the options below:

- [ ] [**Introduction**](./01-start.md) - start here to get introduced to project & technologies.
- [ ] [**Dev Environment**](./03-dev-env.md) - start here to dive straight into application development.

## Next Steps

This sample taught you to build a Copilot With Your Data - using the Azure AI SDK (Python) and CLI. The process involves a number of steps that we managed manually. When building more complex solutions in production, we can benefit from using _orchestration tools_ to streamline our end-to-end development. 

!!!example "Explore Advanced Azure AI Studio Samples"

    **Try these advanced samples** and learn to build the copilot using popular frameworks with the Azure AI SDK.
    
    1. [Build a Copilot With Your Data - **using Semantic Kernel**](https://github.com/Azure-Samples/aistudio-python-semantickernel-sample)
    1. [Build a Copilot With Your Data - **using Prompt Flow**](https://github.com/Azure-Samples/aistudio-python-promptflow-sample)
    1. [Build a Copilot With Your Data - **using LangChain**](https://github.com/Azure-Samples/aistudio-python-langchain-sample)



!!!abstract "Next Up: [**Preview Docs In Browser**](./00-preview.md)"