# 10 | Summary & Wrap-Up

## 🚨 | Clean up

> [!WARNING]  
> Once you have completed this tutorial, please remember to delete the Azure resource group and relevant resources to ensure you don't incur any unexpected charges. 

Note that you may need to delete the Azure AI project resource and Azure AI service resource separately, first, before you can delete the resource group.

## 💡 | Additional Tips and Resources

### Explore the full tutorial

For a more detailed tutorial on this topic, you can follow the [Build a co-pilot using the Azure AI SDK](https://github.com/Azure/azureai-insiders/blob/aistudio-preview/previews/aistudio/tutorials/copilot_with_sdk.md) tutorial.

### Customize the development container

You can pip install packages into your development environment but they will disappear if you rebuild your container and need to be reinstalled (re-build is not automatic). You may want this, so that you can easily reset back to a clean environment. Or, you may want to install some packages by default into the container so that you don't need to re-install packages after a rebuild.

To add packages into the default container, you can update the Dockerfile in `.devcontainer/Dockerfile`, and then rebuild the development container from the command palette by pressing `Ctrl/Cmd+Shift+P` and selecting the `Rebuild container` command.


!!!abstract "Next Up: [**Contributing & Trademarks**](./99-contributing.md)"