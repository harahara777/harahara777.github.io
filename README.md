# [Paparspace Notebook for kohya Gui lora training](https://github.com/harahara777/kohya-lora-paperspace)
* This notebook is created with reference to [ffxvs](https://github.com/ffxvs)'s [sd-webui-complete-setup](https://github.com/ffxvs/sd-webui-complete-setup).
* We use specialized dokcer published by [ffxvs](https://github.com/ffxvs) to simplify the preparation of the environment.  
It includes python, torch, etc., and allows us to prepare an environment without going through complicated steps.

I recommended you to start with setup [sd-webui-complete-setup](https://github.com/ffxvs/sd-webui-complete-setup).  
If not, you will need to build your own python 3.10, torch, cuda cudnn, etc.

## How to start
* Sign-up and subscribe one of plan on [paperspace](https://www.paperspace.com/).
* click **"Create a project"** and input your project name.
* Select the **"Start from Scratch"** bellow.
* In **"Launch a notebook"** section,Choose one of the free GPUs with at least 16GB VRAM (except Free-P5000).
* Set the **"Auto-shutdown"** timeout to **"6 hours"**.
* Click View **"Advanced Options"** bellow.
* Fill in the Container's name and command field as follows and leave other field blank.  
Just click copy button on the right.  

   * Container's name
     * SD Web UI
     ```
       ffxvs/sd-webui-containers:auto1111-2024.09.21      
     ```
     * SD Web UI Forge
     ```
       ffxvs/sd-webui-containers:forge-2024.09.21
     ```
  * Container's command
     ```
     bash /paperspace-start.sh
     ```
* Click ***"Start notebook"*** bellow and wait until the machine is running.
* Click ***"Open in JupiterLab"*** in left side bar.
* You will have 3 notebooks, click to open one of ***"sd_webui_paperspace.ipynb"*** or ***"sd_webui_forge_paperspace.ipynb"***.
* Execute cells in order from top to bottom untill ***"1.3. Temporary Storage Settings"***.
* In ***"1.3. Temporary Storage Settings"*** you can choose which model type to use temporary storage.  
  Check the model type you want to save in the temporary storage.
* Now you have prepared the temporary storage and set up the shared storage, you are ready to setup kohya-gui.
### For more infomation about SD-webui setup and usage please see [here](https://github.com/ffxvs/sd-webui-complete-setup).
## Kohya GUI
* You need download Kohya-Lora.ipynb from this repository, Run the below command in terminal.
     * Terminal command
     ```
     cd /notebooks
     wget https://harahara777.github.io/pps-kohya-setup/kohya-lora.ipynb
     ```
     * Or you can manualy download notebooks and drag and drop to your directory  
[https://harahara777.github.io/pps-kohya-setup/kohya-lora.ipynb](https://harahara777.github.io/kohya-lora-paperspace/kohya-lora.ipynb)
<br>

* Execute cells in order from top to bottom.
* The current GUI version is v24.1.7 by default.
* As an option, there is a function to create a folder to put the dataset and a config toml for paperspace.  
It is recommended to run it if you are using the GUI for the first time.
* There are minimal features related to datasets, which are currently being developed.
* The download function is included in [sd-webui-complete-setup](https://github.com/ffxvs/sd-webui-complete-setup) notebooks. There are 1.5 and SDXL versions, please choose according to your purpose.
## Here are some tips on some common problems you may encounter.
* When you copy a path of file or folder, it will be **"notebooks/folder/file.txt"**, but when you actually use it, the correct path is **"/notebooks/folder/file.txt"**.
* Don't just right-click and delete files, use **"Delete File or Folder"** function.
* When the GUI launches, **Dreambooth** is selected by default, make sure select **Lora** tab for lora training.
* Once training is started, you don't need to keep blower tab opnen, Training process continues even if you shut down your PC.
## Known Issue
* Some of the console logs Info contain file paths and are very difficult to read.  
  please add **--console_log_simple** to additinal paramaters for avoid messy console logs.
* Tenderflow and tenserRT is not installed because of some issues, so logging with them is currently not possible for now.

<br>

## Credits
* [sd-webui-complete-setup](https://github.com/ffxvs/sd-webui-complete-setup) by ffxvs
* [sd-scripts](https://github.com/kohya-ss/sd-scripts) by kohya
* [kohya_ss](https://github.com/bmaltais/kohya_ss) by bmaltais


