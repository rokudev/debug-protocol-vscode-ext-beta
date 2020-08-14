# VSCode extension for Roku BrightScript Debug Protocol

Roku provides a VSCode extension for debugging channels with the BrightScript remote network debug protocol.
![general_design_diagram](https://image.roku.com/ZHZscHItMTc2/6-debug-vsix-general-design.png)


## Installation
1. Install python 3.5+. 

    - You can explicitly specify the path to the python executable. Use "pathToPython" field in the JSON configuration. This is useful if python3.5+ cannot be installed globally by default.

    - The path to the python3 executable may be specified with the **pathToPython** var in run confuguration if it is not available to run globally.
    - For Windows, add the Roku debug VSCode extension to the global PATH variable

2. Download the **roku-debug-2.0.0+4.zip** file and extract it. 

3. Open Visual Studio Code and install the extracted **roku-debug-2.0.0+4.vsix** file.

    ![install_from_vsix](https://image.roku.com/ZHZscHItMTc2/7-debug-vsix-install-from-vsix.png "install_from_vsix")

## Getting started

To use this extension, follow these steps:

1. Add the debug config with the required data. All folders should exist. The extension does not have rights to create folders.![open_bs_project_folder](https://image.roku.com/ZHZscHItMTc2/4-debug-vsix-add-debug-config.png "open_bs_project_folder" )
2. Run your Roku channel with the debug protocol

  ![open_bs_project_folder](https://image.roku.com/ZHZscHItMTc2/5-debug-vsix-fill-config-and-run.png "open_bs_project_folder")

## Features

- Pause executions (all threads)
- Receive threads list
- Recieve backtrace of current thread
- Continue execution (all threads)
- Stop execution

## Launch config parameters overview
| Parameter                      | Default                     | Description                                                  |
| ------------------------------ | --------------------------- | ------------------------------------------------------------ |
| rokuIp                         | Prompt shown if doesn't set | IP Address of Roku device                                    |
| devPassword                    | ""                          | Roku developer password.<br /><br />This must be entered before debugging. |
| projectRootFolder              | ${workspaceFolder}          | Project root folder. Default is currently open folder.       |
| outFolder                      | ${workspaceFolder}/out      | Project out folder for zip file                              |
| trace                          | true                        | Enables logging of the Debug Adapter Protocol.               |
| (optional) pathToPython        | ""                          | Path to python3.5+ executable. Use if bin is not available in env. |
| (optional) javaPath            | ""                          | Path to java executable. Use if bin is not available in env. |
| (dev usage only) debugToolPath | ""                          | Path to the rokudebug.py tool                                |
## Known issues:

* Roku devices may reboot during launch
