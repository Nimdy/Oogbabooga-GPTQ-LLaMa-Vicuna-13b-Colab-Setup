# Oogbabooga Colab Notebook Beta Project

This project sets up and deploys the Oogbabooga text generation model on Google Colab. The notebook includes steps to download the required dependencies, set up the environment, and run the application.

## Getting Started

To use this project, follow these steps:

1. Open the Colab notebook from this repository.
2. Ensure you have GPU support enabled by going to Runtime > Change runtime type and selecting GPU as the hardware accelerator.
3. Run the notebook using Runtime > Run All (⌘/Ctrl+F9). It takes about 5 minutes to start, and you will be prompted to authorize Google Drive access.
4. To prevent Colab from disconnecting you, a music player is included that will loop infinitely (it's silent). This will help keep your session alive.

## Notebook Contents

### Initialization

In this section, all the necessary variables that will be used throughout the notebook are initialized. This includes the Google Drive folder where the data is stored, the path where Google Drive will be mounted, the URL of the text-generation repository, and others.

### Google Drive Mounting

This section mounts Google Drive to the specified path, creates a symbolic link between the Google Drive data directory and the current directory for easy access, and creates a text file in the data directory indicating the notebook that is currently using it.

### GPU Information

This section checks if the current Colab instance is connected to a GPU using the `nvidia-smi` command and prints the GPU info.

### RAM Information

This section prints the total available RAM on the current Colab instance and checks if the instance is a high-RAM runtime by comparing the total RAM with a threshold value.

### Text Generation WebUI Setup

This section clones the 'text-generation-webui' repository from GitHub into the data directory on Google Drive if it does not exist already. Then, the requirements for the repository are installed using pip.

### 4-bit Mode Support Setup

This section clones the 'GPTQ-for-LLaMa' repository from GitHub into the repositories directory under 'text-generation-webui' if it does not exist already. The necessary requirements for this repository are installed and the setup script is run.

### Download Model

This section downloads the model from Hugging Face and stores it in the text-generation-webui directory. The model is downloaded only if it does not exist already.

### Move Model File

This section moves the downloaded model file to a specific directory under 'models'. If the file already exists in the destination, it is not moved.

### Run Application

In the final section, the necessary version of Pillow is installed, and the application is run with the specified model and parameters.
