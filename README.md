
# vscode_example

----

This project demonstrates of using Visual Studio Code for RISC-V embedded development.  
Details in the Wiki.

## Requirenments

* Visual Studio Code
* Plugin "C/C++" (cpptools)
* Plugin "Native Debug"
* Plugin "Makefile Tools" (optional)
* RISC-V tools

## Configuration

Project contains build and launch configurations in `c_cpp_properties.json`, `launch.json`, `tasks.json` (in folder `/.vscode/`).

Build done with makefile and tasks "Makefile" and "Makefile clean" in `tasks.json`. Build started by `Ctrl+Shift+B`.

File `launch.json` contains debug configurations.  
There are two configurations variants "cpptools Debug" and "Native Debug", they are similar with slight differences.  
Choose configuration in debug palette and launch debugging by `F5`.

File `tasks.json` contains tasks "preLaunchTask" and "postDebugTask" for `launch.json`.  
OpenOCD (and Spike) starts as tasks in background.  
All task-processes automatically terminate by stop/disconnect (with task "Termitate all tasks").

## Quick start

Set actual paths in files `paths`, `c_cpp_properties.json`, `launch.json`, `tasks.json`.

Build project: `Ctrl+Shift+B`.

**Launch with hardware**:  
Set configuration in `launch.json`:

        "preLaunchTask": "startOpenocdHW"

**Launch with Spike**:  
Set configuration in `launch.json`:

        "preLaunchTask": "startOpenocdSpike"

Tested on VS Code ver.1.67.2.

----
