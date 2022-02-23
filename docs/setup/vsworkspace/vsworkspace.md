# Setting up vs-code

## Create a workspace

In vs-code go to File -> Open Folder and select the CSSE3010 folder.

The folder should be visible in the Explorer section of vs-code. It should have 2 sub-folders, sourcelib and repo.

File -> Save Workspace As -> name the workspace. e.g. csse3010.code-workspace

Now, whenever you open up vscode, open this workspace file to resume where you left off.

File -> Open Workspace from file

Using workspaces will greatly help you nagivate between different files in your code as well as sourcelib.

## Install the C/C++ extension

You will need this for IntelliSense (autocompletion) and browsing your code. Go to the extensions tab, search for C/C++ and install it. Restart vscode.

## Create workspace settings

Navigate to any makefile in sourcelib

```
make vscode
```
In vscode, under explorer, click the refresh explorer button, a new folder should appear under the root folder called .vscode. This folder contains a settings file that modifies some vscode behaviour as well as a properties file which contains the folders where your code should look for includes and files.
