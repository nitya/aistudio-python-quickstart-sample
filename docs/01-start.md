# 01 | Introduction

!!!warning "Azure AI Studio is currently **In Preview**"
    **Preview versions are provided without a service level agreement, and they are not recommended for production workloads. Certain features might not be supported or might have constrained capabilities. For more information, see [Supplemental Terms of Use for Microsoft Azure Previews](https://azure.microsoft.com/en-us/support/legal/preview-supplemental-terms/).**


## Learning Objectives

This tutorial walks you through the process of creating a copilot enterprise chat UI using custom Python code to ground copilot responses in your company data and APIs. By completing these steps, you'll also gain familiarity with the core features and functionality available in the Azure AI Studio preview, Azure AI CLI and Azure AI SDK for Python. 

**By the end of this lab, you should have learned how to:**

1. [Setup your dev environment](./03-dev-env.md) - using prebuilt dev containers.
2. [Provision your Azure AI resources](./04-azure.md) - using Azure AI CLI `ai init` command.
3. [Populate your Data & Indexes](./05-search.md) - using Azure AI CLI `ai search` command.
4. [Test your Copilot with a question](./06-copilot.md) - using Azure AI SDK for Python.
5. [Evaluate your Copilot with metrics](./07-evaluate.md) - using chatgpt to compare results.
5. [Deploy your Copilot to Azure](./08-deploy.md) - and use the endpoint in your own apps.

_Treat this sample as a starting point for your exploration._ Once you've got the basic Copilot deployed, try modifying the data or adding new features, to adapt it to your own scenario.


## Pre-Requisites

**You will need the following to complete this tutorial:**

1. An Azure subscription - [Create one for free](https://azure.microsoft.com/free/cognitive-services)
1. Access to Azure OpenAI - [Request access here](https://aka.ms/oai/access)
1. A GitHub account - [Create one for free](https://github.com/signup)
1. Access to GitHub Codespaces - [Free quota should be sufficient](https://docs.github.com/en/billing/managing-billing-for-github-codespaces/about-billing-for-github-codespaces#monthly-included-storage-and-core-hours-for-personal-accounts)

**We assume you have familiarity with the following:**

1. _Programming_: Python and Jupyter Notebooks
1. _Editor_: Visual Studio Code and Extensions
1. _Azure_: Cloud Computing Concepts, Azure Portal 
1. _AI/ML_: Fundamental Concepts, LLM, Generative AI

## Bring Your Data

This tutorial builds a copilot for a fictional company (**Contoso Outdoors**) that sells camping and hiking gear to outdoor adventuring enthusiasts. The `data/` folder has sample records for:

 - **product-info** - 20 item of product catalog data
 - **customer-info**  - 13 records or customer order history
 - **misc** - policy information and other miscallaneous company data
 - **chat-history** - conversation history with customers (for context)

We use the data to _ground_ our copilot responses. Once you have completed the sample, we encourage you to **bring your own data** (schemas and records) and try to adapt or extend the sample to suit your specific company data and application scenarios.

!!!abstract "Next Up: [**Learn Core Concepts**](./02-technology.md)"
