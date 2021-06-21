# SQSnobFit Plugin

This plugin allows Rxn Rover to connect with an instance of `SQSnobFit 
<https://pypi.org/project/SQSnobFit/>`_, a Python reimplementation of the 
`SNOBFIT <https://www.mat.univie.ac.at/~neum/software/snobfit/>`_ blackbox 
optimization algorithm. A Python program is provided with the plugin to launch 
an instance of SQSnobFit for use with this plugin. This program uses a 
modified objective function with built-in communication capabilities. The 
SQSnobFit algorithm, along with other aspects of the program, can be 
configured by specifying a configuration file (example files are provided).

## Installation

### Prerequisites

This plugin requires Python 3.x. Download it from https://www.python.org/.

### Getting the Plugin

Download this plugin by clicking the "Code" button in the top right of its 
GitHub repository and selecting "Download ZIP". Extract the ZIP file into your 
`<documents>/Plugins/Optimizers` directory. 

### Setting up SQSnobFit Optimizer

Inside `<documents>/Plugins/Optimizers/SQSnobFit` there are two folders, 
`plugin`, where the Rxn Rover plugin resides, and 
`sqsnobfit_remote_optimizer`, where the necessary code to launch an 
instance of SQSnobFit that can communicate with the plugin. If you are using
Linux or Mac, simply type `make install` in the `sqsnobfit_remote_optimizer`
directory to download and install dependencies into a virtual environment.

If using Windows, open a terminal in the `sqsnobfit_remote_optimizer` 
directory and type the following commands:

```batch
python -m venv venv             # Creates a virtual environment (venv)
.\venv\Scripts\activate         # Activates the venv
pip install -r requirements.txt # Installs dependencies in venv
deactivate                      # Deactivates the venv
```

## Configurations

The SQSnobFit optimization can be configured by editing or creating a new 
config file in the `sqsnobfit_remote_optimizer/config` directory. An example
configuration file with default values is provided as `default-config.json`.

## Plugin Scripts

Scripts used by the plugin are located in the 
`sqsnobfit_remote_optimizer/config` subdirectory. When creating a new script,
ensure that it activates the `venv`, runs `src/main.py` with the correct 
config file as a command line argument, and deactivates the `venv` when 
complete.