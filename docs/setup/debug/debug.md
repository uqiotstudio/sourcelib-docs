# CSSE3010 Debug Guide

This document details how to set up and use a debugging environment.

---

## Setting up gdb tools

```
sudo apt-get install gdb-multiarch
sudo ln -s /usr/bin/gdb-multiarch /usr/local/bin/arm-none-eabi-gdb
```

## Setting up vs-code

Follow the setup instructions in the VSCode Settings section

Go into the extensions section and search for Cortex-Debug, install it, then restart vs-code

## Creating launch.json

go to your app

```
make launch
```
This will generate a launch.json file inside a folder called .vscode inside your CSSE3010 folder, this is needed for the debugger to work.

You will need to run this every time you flash a new application onto your board.

## Section 4: Running the Debugger

In vscode, press the Debug button on the left ribbon, at the top of the window, 2 configurations should become available, 

Debug Attach (Jlink)
Debug Launch (JLink)

Use Debug Attach to start a debug session on a currently running application and Debug Launch to restart the board and begin debugging.

Then use standard debugging commands to go through your code, e.g. Continue, Step Over, Step Into, etc

Click on the left of the line number to create breakpoints.

Start by putting a break point somewhere in main.







