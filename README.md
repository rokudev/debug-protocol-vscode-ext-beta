# VSCode Roku debug extension

## Table of Contents
1. [Preconditions](#preconditions)
2. [Description](#description)
3. [Installation](#installation)
4. [Features/Usage](#features/usage)
5. [Known issues](#known-issues)
[Launch config parameters overview](#launch-config-parameters-overview)


## Preconditions
Platform used for testing:
- macOS 10.14.6
- Windows 7
- Python 3.6.5
- Roku Cooper 4640X, 9.8.0b573-29
- ~~rokudebug py tool (from p4/apps/)~~ (Embedded to extension)


## Description
This is a VSCode extension for debugging Roku BrightScript application using binary debug protocol.
![general_design_diagram](docs/6_general_design.png)


## Installation
1. Dependencies
    - install python 3.5+
       - Note: There is a possibility to explicitely specify path to python executable. Use "pathToPython" field in configuration json. (for case if no possibility to install python3.5+ globally by default)
    - For windows it should be added to global PATH variable
    - Note: path to python3 executable may be specified by pathToPython var in run confuguration if it's not available to run globally.

2. Open VSCode
### To run from source:
3. Open debug-adapter folder
![open_extension_folder](docs/1_open_extension_folder.png)
4. Run extension

    Debug > Start debugging F5 or

![run_extension_window](docs/2_run_extension.png)
5. In newly opened window open Roku BS project folder
![open_bs_project_folder](docs/3_open_project_folder.png)

### To use vsix extension distribution:
3. Download vsix archive
4. Install extension from vsix
![install_from_vsix](docs/7_install_from_vsix.png)

## Usage:

1. Add debug config with required data
![open_bs_project_folder](docs/4_add_debug_config.png)
Note: All folders should exist. Extension may not have rights to create folders.
2. Run channel with debug
![open_bs_project_folder](docs/5_fill_config_and_run.png)


## Features/Usage:
- Pause executions (all threads)
- Receive threads list
- Recieve backtrace of current thread
- Continue execution (all threads)
- Stop execution

## Known issues:
* Sometimes Roku reboots during launch

## Launch config parameters overview
| Parameter                      | Default                     | Description                                                        |
|--------------------------------|-----------------------------|--------------------------------------------------------------------|
| rokuIp                         | Prompt shown if doesn't set | IP Address of Roku device                                          |
| *devPassword                   | ""                          | Roku dev password                                                  |
| projectRootFolder              | ${workspaceFolder}          | Project root folder. Default is currently open folder.             |
| outFolder                      | ${workspaceFolder}/out      | Project out folder for zip file                                    |
| trace                          | true                        | Enable logging of the Debug Adapter Protocol.                      |
| (optional) pathToPython        | ""                          | Path to python3.5+ executable. Use if bin is not available in env. |
| (optional) javaPath            | ""                          | Path to java executable. Use if bin is not available in env.       |
| (dev usage only) debugToolPath | ""                          | Path to rokudebug.py tool                                          |
\* required to fill before run

[&#8593; Table of content](#table-of-Contents)
###### Copyright (c) 2019 Roku, Inc. All rights reserved.
