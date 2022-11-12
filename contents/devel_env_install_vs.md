# Install Visual Studio Code with Windows Subsystem for Linux

My code editor choice is [Visual Studio Code](https://code.visualstudio.com/). Among other reasons I can highlight: as it directly support remote development and debugging with WSL. *Visual Studio Code allows you to use WSL as a full-featured development environment*.

See a complete guide at [Get started using Visual Studio Code with Windows Subsystem for Linux](https://learn.microsoft.com/en-us/windows/wsl/tutorials/wsl-vscode).

In the first step install Visual Studio Code on Windows. Download on [Visual Studio Code official website](https://code.visualstudio.com/download).

When prompted to Select Additional Tasks during installation, be sure to check the **Add to PATH** option so you can easily open a folder in WSL using the code command.

An important step is install [Remote Development extension pack](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack) on Visual Studio Code. This extension pack enabling you to open any folder in a container, on a remote machine, or in WSL.

Before running your Visual Studio Code in a WSL project is recommended update your Linux and run these two important commands:

| Bash |
| ---- |
| `sudo apt-get update` |
| `sudo apt install wget ca-certificates` |