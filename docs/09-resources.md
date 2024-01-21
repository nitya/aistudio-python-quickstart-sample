# 09 | Learning Resources


!!!warning "Azure AI Studio is currently **In Preview**"
    **Preview versions are provided without a service level agreement, and they are not recommended for production workloads. Certain features might not be supported or might have constrained capabilities. For more information, see [Supplemental Terms of Use for Microsoft Azure Previews](https://azure.microsoft.com/en-us/support/legal/preview-supplemental-terms/).**

This page provides an evolving set of links to documentation, training, samples and other resources that may be helpful to self-guided learners on this journey. **Check back often for updates since the platform capabilities and tools are evolving fast**.


## Azure AI Documentation

1. [Azure AI Services](https://learn.microsoft.com/azure/ai-services/) - Pre-built AI services available for deployments (API key, endpoints)
1. [Azure AI Resource](https://learn.microsoft.com/azure/ai-studio/concepts/ai-resources) - Top-level resource to admin billing, access, policies, resource usage
1. [Azure AI Project](https://learn.microsoft.com/azure/ai-studio/how-to/create-projects) - Resource to organize work & save state when building AI solutions
1. [Azure AI SDK](https://learn.microsoft.com/azure/ai-studio/how-to/sdk-generative-overview) - Generative AI SDK, drive code-based interactions with Azure AI platform
1. [Azure AI CLI](https://learn.microsoft.com/azure/ai-studio/how-to/cli-install) - .NET implementation, drive command-line interactions with Azure AI platform
1. [Azure AI Studio](https://learn.microsoft.com/azure/ai-studio/) - UI, drive web-based interactions with  the Azure AI platform.
1. [Using vector search in Azure Cognitive Search](https://learn.microsoft.com/training/modules/improve-search-results-vector-search) - Tutorial.
1. [Deploy a web app for chat on your data](https://learn.microsoft.com/azure/ai-studio/tutorials/deploy-chat-web-app) - Tutorial.
1. [Moderate text and images with content safety in Azure AI Studio](https://learn.microsoft.com/azure/ai-studio/quickstarts/content-safety) - Quickstart


## Azure AI Samples

Fork and explore these samples to get hands-on experience with the SDK and CLI in different contexts. Star the repo if you find it useful!

1. [Build a Copilot with Your Data - with Python SDK](https://github.com/Azure-Samples/aistudio-python-quickstart-sample)
1. [Build a Copilot with Your Data - using Promptflow](https://github.com/Azure-Samples/aistudio-python-promptflow-sample)
1. [Build a Copilot with Your Data - using LangChain](https://github.com/Azure-Samples/aistudio-python-langchain-sample)
1. [Build a Copilot with Your Data - using Semantic Kernel](https://github.com/Azure-Samples/aistudio-python-semantickernel-sample)
1. [Build a Production RAG - using PromptFlow, with LLM Ops](https://github.com/Azure-Samples/contoso-chat)


## OpenAI Cookbook

The [OpenAI Cookbook](https://github.com/openai/openai-cookbook) has example code and guides for accomplishing common tasks with the OpenAI API. Most code examples are written in Python but applicable to others. 

This collection includes the following Azure-centric samples:

1. [Azure OpenAI chat completions example](https://cookbook.openai.com/examples/azure/chat) - **for:** multi-turn, content filtering
1. [Azure OpenAI completions example](https://cookbook.openai.com/examples/azure/completions) - **for:** single prompt, content filtering
1. [Azure OpenAI embeddings example](https://cookbook.openai.com/examples/azure/completions) - **for:** converting nlp input to numerical representation.
1. [Azure OpenAI functions example](https://cookbook.openai.com/examples/azure/functions) - **for:**  function definition, function calling
1. [Azure OpenAI chat completion models with your own data (preview)](https://cookbook.openai.com/examples/azure/chat_with_your_own_data) - **for:**  RAG pattern
1. [Azure AI Search as vector database for OpenAI embeddings](https://cookbook.openai.com/examples/vector_databases/azuresearch/getting_started_with_azure_cognitive_search_and_openai) - **for:** similarity, hybrid, semantic

The main concepts covered are:
 
- **Completions** - 'question-answer' text generation with {model, prompt} as inputs
- **Chat Completion** - 'multi-turn' text generation  with {model, messages} as inputs
- **Embeddings** - vector representation, meassures 'relatedness' (similarity) of text 
- **Functions** - used to connect LLMs to external tools (convert NLP inputs into API calls)

**Messages**: are defined by {role, content} where the role can be _system_ (context), _assistant_ (response) or _user_ (question). Using the _[Chat Completions API](https://platform.openai.com/docs/guides/text-generation/chat-completions-api)_ is recommended (works with latest models) where a "completion" is effectively a single message containing a user question.

**Function Calling**: where the function is a "tool" (code) that takes a string input (JSON), executes the call (to API), and returns the response as a string (JSON). Chat completion request has a "tools" argument to pass in relevant functions. The model can choose to call one or more functions which return response as a new "message" that model can use for summarizing results in its response.

**Embeddings**: can be used for: search (ranking), clustering (topics), recommendations (items), anomaly detection )(outliers), diversity measurement (similairity), and classification (labels).

!!!abstract "Next Up: [**Summary & Wrap-Ups**](./10-summary.md)"