# 03 | Dev Environment

!!!warning "Azure AI Studio is currently **In Preview**"
    **Preview versions are provided without a service level agreement, and they are not recommended for production workloads. Certain features might not be supported or might have constrained capabilities. For more information, see [Supplemental Terms of Use for Microsoft Azure Previews](https://azure.microsoft.com/en-us/support/legal/preview-supplemental-terms/).**


For this project, we need a development environment with the following:

 - **A Python 3.x runtime** (3.10 or higher) with all _requirements_.
 - **A Visual Studio Code editor** with all _required extensions_.
 - **Azure AI CLI tooling** (binary) _for latest stable version_.

---

### Fork The Sample

Before you begin, we recommend you **fork the sample repo** into your own profile on GitHub. This is useful for two reasons:

1. You keep a snapshot of the sample at this point in time, even as the main sample evolves. _This lets you have a stable and familiar version that corresponds to your walkthrough_,
1. You can make changes to the code if you want to experiment on this later. _For example, you may want to try adding your own data, or exploring new features_.

To fork the repo:

1. Visit [Azure-Samples/aistudio-python-quickstart-sample](https://github.com/Azure-Samples/aistudio-python-quickstart-sample). Click the **Fork** button:

    ![Create Fork](./img/devenv-create-fork.png)

1. Click **Create Fork** leaving the default options unchanged.

    ![Confirm Fork](./img/devenv-confirm-fork.png)

!!!success "Congratulations! You have forked the sample to your profile!"


## Pick a Setup Option

To setup your development environment, use one of these three options:

1. **Pre-built, cloud VM** - using GitHub Codespaces.
2. **Pre-built, local VM** - using Docker Desktop.
3. **Manual, local OS** - using your preferred environment.

The repository is instrumented with a [dev container](https://containers.dev) configuration that creates a pre-built development environment in a Docker container,r eady for your use. The first two options allow you to run this container in the cloud or on your local device. The final option is to do the entire setup yourself, in your preferred environment or OS.

We've documented the three options below from least-effort to most, for setup. **Pick one**.

!!!tip "Recommended Option: Pre-built Container On GitHub Codespaces!"

    The Azure AI Studio preview and related Azure AI SDK and Azure AI CLI are likely to evolve quickly to reflect changes and updates. We **strongly recommend using the pre-built development environment** option to minimize your effort in maintaining your local environment, to stay up-to-date with these changes.



### 1: Pre-built Container, in Cloud

1. To get started, click the button below to launch [GitHub Codespaces](https://docs.github.com/codespaces) directly in your browser.

    [![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://github.com/Azure-Samples/aistudio-python-quickstart-sample/)

    Alternatively, you can launch GitHub Codespaces by clicking the "Code" button in the repository UI, selecting the "Codespaces" tab - and then creating a new codespace. _Previously created codespaces will be listed if active or available for resume_.
    
    ![Launch GitHub Codespaces](./img/01-launch-codespaces.png)   

2. The first time you launch the codespace, you will see a new tab open with something like this indicating that the Codespace (dev container) is being built. Clicking the `Show Logs` button in the output console will produce the detailed output shown below.

    ![Codespace build](./img/02-setup-codespaces.png)

3. Once the build completes, you should see the tab refresh to show a Visual Studio Code editor in the browser, as shown below. The blue bar at the bottom left of the screen should show you the name of the running Github Codespaces instance.
    
    ![Codespace build](./img/03-running-codespaces.png)

    If you refresh the repository page and view that 'Codespaces' tab again, you should see the same name show up as an active codespace for that repository.
    ![Codespace build](./img/03-view-codespaces.png)

    🟩 Congratulations! You're Codespaces is ready!


### 2: Pre-built Container, on Device

> [!NOTE]  
>  This option is recommended if you prefer to work locally on your device. Continue getting the benefits of a prebuilt development environment using Docker Desktop as your container host.

1. **Install Docker Desktop**. Follow the instructions [here](https://code.visualstudio.com/docs/devcontainers/containers#_installation) to install Docker Desktop on your device.
2. **Clone this repository** to your local device as usual, and open the repository in Visual Studio Code. Then follow the instructions [here](https://code.visualstudio.com/docs/devcontainers/containers#_quick-start-open-an-existing-folder-in-a-container) to open the repository in a dev container hosted in Docker Desktop. It will take a few minutes to build the container, but the end result will look like this. Note that the blue bar at the bottom left of the screen now indicates you are running in a `Dev Container` rather than a named GitHub Codespace.

    ![Dpcker build](./img/03-view-docker.png)

    🟩 Congratulations! You're local Dev Container is ready!


### 3: Manual Setup, on Device

> [!NOTE]  
> This option is provided only for completeness. It is best for advanced users who are willing to tradeoff complexity (in maintenance) for control (in local environment setup). The user is accountable for making related updates when the Azure AI Studio, SDK or CLI dependencies change.

To minimize disruption to other projects on your local device, we recommend using a _managed_ virtual environment (like _venv_ or _conda_) to install the required Python version and dependencies for this project. 

1. **Install and activate a virtual environment**. Follow the guidance in the [How to get started with the Azure AI SDK](https://learn.microsoft.com/azure/ai-studio/how-to/sdk-install?tabs=linux) documentation to install your preferred virtual environment (venv or conda) - and activate it. You need `Python 3.10 or higher` to use the Azure AI SDK.

2. **Install the Azure AI SDK**. Use the `requirements.txt` file in this repo and install dependencies as follows:
    ```bash
    pip install -r requirements.txt
    ```
3. **Install the Azure AI CLI**. Use the following command if your local environment on Ubuntu. To install the CLI on Windows and MacOS, follow the instructions [here](https://github.com/Azure/azureai-insiders/blob/main/previews/aistudio/how-to/use_azureai_sdk.md#install-the-cli) instead.
    ```
    curl -sL https://aka.ms/InstallAzureAICLIDeb | sudo bash
    ```

🟩 Congratulations! You're local environment is ready!

---

## Validate Your Setup

We assume you've completed one of the three options above to setup your development environment. Now, let's validate the setup by checking if the Azure AI CLI is installed. 

```bash
ai help
```
If setup correctly, you should see the help screen for the Azure AI CLI. as shown below. Hit `Esc` to exit the help screen and get back to your commandline prompt.

![Validate Setup](./img/04-validate-setup.png)

🟩 Congratulations! You've validated your dev environment!

## Next Steps

We've setup and validated our development environment. Next, we'll create our Azure AI project and provision resources to build our copilot solution.

!!!abstract "Next Up: [**Provision Azure Resources**](./04-azure.md)"