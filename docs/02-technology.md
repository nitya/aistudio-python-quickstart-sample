# 02 | Core Concepts

Lte's talk briefly about some of the core terms, concepts and technologies used in this quickstart tutorial. This is not a comprehensive coverage of the topics so check the [Resources page](./09-resources.md) for relevant documentation and training links.


## 1. Tools


![Azure AI Studio](https://learn.microsoft.com/en-us/azure/ai-studio/media/explore/ai-studio-home.png)


### 1.1 [**Azure AI Studio**](https://learn.microsoft.com/azure/ai-studio/)

 Azure AI Studio is a web-based UI that helps developers seamlessly explore, build, test, and deploy **enterprise-grade generative AI applications** using cutting-edge AI tools and ML models, grounded in responsible AI practices. It has three core value propositions:

 - **Explore** - for _discovery_.  Browse models, services or solutions in the Azure AI platform.
 - **Build** - for _developers_. Build and customize AI models & AI solutions via code or UI.
 - **Manage** - for _admins_. Oversee policy, billing, access control, infra usage etc.
 

### 1.2  [**Azure AI CLI**](https://aka.ms/azureaistudio)

The Azure AI CLI provides an command-line based tool to interact with the Azure AI platform with a rich set of capabilities that includes:

- **`ai init`** - creation of the Azure AI resource (default or customized)
- **`ai dev`** - configure environment variables for local dev environment
- **`ai service`** - manage connections to Azure AI resources and services
- **`ai flow`** - work with prompt flows from your local dev environment
- **`ai chat`** - chat with your deployed copilot from local dev environment
- **`ai help`** - get help with Azure AI CLI commands and options


### 1.3 [**Azure AI SDK**](https://learn.microsoft.com/azure/ai-studio/how-to/sdk-install?tabs=linux)

The Azure AI SDK is a family of packages that provide access to Azure AI services such as Azure OpenAI and Speech. The **Azure AI Generative package** is part this SDK and contains functionality (below) to _support local development_ that you can optionally remove if unused.

- **`[index]`** package to build indexes locally.
- **`[evaluate]`** package to run evaluation & calculate metrics locally.
- **`[promptflow]`** package to develop locally with prompt flow connected to Azure AI project.


## 2. Terminology

### 2.1 What is a Copilot

A copilot is an application that uses modern AI and large language models (LLM) to assist you in completing complex cognitive tasks. 

In this particular tutorial, we are building a copilot that assists you in answering user questions _about your company data_, by using the [Retrieval Augmented Generation (RAG)](https://learn.microsoft.com/azure/ai-studio/concepts/retrieval-augmented-generation) pattern  with your preferred LLM deployment endpoint.

### 2.2 What is RAG?

[Retrieval Augmented Generation (RAG)](https://learn.microsoft.com/azure/search/retrieval-augmented-generation-overview) is a pattern where you _augment_ the capability of the default Large Language Model (LLM) by adding an _information retrieval system_. This provides you more control over the data used by the LLM in generating responses to user "questions", allowing you to tailor copilot responses to reflect your company data and requirements.

![How does RAG Work?](https://learn.microsoft.com/azure/ai-studio/media/index-retrieve/rag-pattern.png)

The RAG pattern (shown above) maintains a data store with your custom data. When the copilot receives a user question, it retrieves data matching the question from this store. It then combines the user question with retrieved data to form the prompt sent to the LLM, helping ground the returned responses.

![What is an Index and why do I need it?](https://learn.microsoft.com/azure/ai-studio/media/index-retrieve/rag-pattern-with-index.png)

Searching and retrieving data quickly and accurately is critical. The RAG pattern achieves this by proactively maintaining _search indexes_ (as shown above) to improve performance and accuracy.

Azure AI provides an Index asset to use with RAG - where the asset knows where the index is stored, how to access it, what search modes it supports, whether it has vector search capability, what embedding model it uses for this, and more. Currently, Azure AI Search is the primary Index solution for Azure AI projects. | **See: [Retrieval Augmented Generation and Indexes](https://learn.microsoft.com/en-us/azure/ai-studio/concepts/retrieval-augmented-generation#how-does-rag-work)**

### 2.3 What is Vector Search?
Vector search is an information retrieval approach using numeric representations of content for search scenarios. The search engine now matches on vectors that are the most similar to the query, without needing to match exact terms. This helps it power similarity search, multi-modal search, recommendations engines, or apps implementing the 
[Retrieval Augmented Generation (RAG)](https://learn.microsoft.com/azure/search/retrieval-augmented-generation-overview) architecture.

Vector search is available in Azure AI Search by default, and works as shown below. In this project, we use Azure AI Search to create a vector store for the product information data, then use Azure Open AI `text-embedding-ada-002` deployment for embedding data in vectors, for more efficient search and retrieval later. | **See: [Vector search in Azure AI Search](https://learn.microsoft.com/en-us/azure/search/vector-search-overview).**

![What's vector search in Azure AI Search?](https://learn.microsoft.com/azure/search/media/vector-search-overview/vector-search-architecture-diagram-3-high-res.png#lightbox)



## 3. Azure Resources

As developers, we have three options for interacting with Azure AI services and models:

 - **Azure AI Studio** - browser-based low-code approach.
 - **Azure AI CLI** - terminal-based command-line approach.
 - **Azure AI SDK** - editor-based code-first approach (Python & Jupyter Notebooks)

In this sample, we will primarily work with the Azure AI CLI and Azure AI SDK for developing our copilot solution. We'll use the Azure AI Studio primarily to verify the outcomes of our deployment. 

### 3.1 [Azure AI Services](https://learn.microsoft.com/azure/ai-services/what-are-ai-services?context=%2Fazure%2Fai-studio%2Fcontext%2Fcontext)

Azure AI services help developers and organizations rapidly create intelligent, cutting-edge, market-ready, and responsible applications with out-of-the-box and pre-built and customizable APIs and models. Most Azure AI services can be accessed via API or SDK for code-first integrations. Browse the [available Azure AI services](https://learn.microsoft.com/en-us/azure/ai-services/what-are-ai-services?context=%2Fazure%2Fai-studio%2Fcontext%2Fcontext) to understand the range of capabilities.


### 3.2 [Azure AI Resource](https://learn.microsoft.com/azure/ai-studio/concepts/ai-resources)

The Azure AI Resource is the top-level resource required before you can start working on an AI Project. It provides the working environment for a team to plan and execute their solution from design to deployment. And it is typically used by the _admin_ in the team to oversee access controls, billing and resource usage across the multiple AI projects it might be supporting.

The Azure AI Resource will expose API endpoints and keys for any _prebuilt AI services_ that you use in your AI solution. The default AI Resource configuration includes the [Azure OpenAI](https://learn.microsoft.com/azure/ai-services/openai/), [Content Safety](https://learn.microsoft.com/en-us/azure/ai-services/content-safety/), [Speech](https://learn.microsoft.com/en-us/azure/ai-services/speech-service/), and [Vision](https://learn.microsoft.com/en-us/azure/ai-services/computer-vision/) AI services - and makes them accessible via a _common API key_.


### 3.3 [Azure AI Project](https://learn.microsoft.com/azure/ai-studio/how-to/create-projects)

The Azure AI Project resource is used to organize your work and save state while building customized AI apps. Projects are hosted by an Azure AI resource that provides enterprise-grade security and a collaborative environment for the project team. Learn more about how to [create an Azure AI Project](https://learn.microsoft.com/azure/ai-studio/how-to/create-projects) using the Azure AI Studio (visually) or using the Azure AI CLI/SDK (programmatically).

### 3.4 [Azure AI Search](https://learn.microsoft.com/azure/search/search-what-is-azure-search) 


Azure AI Search (formerly called _Azure Cognitive Search_) provides tools, APIs and infrastructure to **support information retrieval at scale** over heterogeneous data sources - for traditional and conversational search solutions. It is a [proven solution for information retrieval in RAG architectures](https://github.com/Azure-Samples/azure-search-openai-demo) and can be accessed from Azure AI Studio, Azure AI SDK or Azure AI CLI. 


!!!abstract "Next Up: [**Setup Development Environment**](./03-dev-env.md)"