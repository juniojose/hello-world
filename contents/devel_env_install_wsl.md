# Install Windows Subsystem for Linux (WSL)

To install my development environment, I first install [Windows Subsystem for Linux](https://learn.microsoft.com/en-us/windows/wsl/) on Windows. I follow the steps in this [Microsoft tutorial](https://learn.microsoft.com/en-us/windows/wsl/install).

I like [Debian](https://www.debian.org/) Linux Distribution, so I use this command:

| Powershell |
| ------------------------- |
| `wls --install -d Debian` |

At the end of the installation, `wls` will open a shell window asking for the username and password. This password will be used to give you [sudo](https://www.sudo.ws/) access to Linux, so don't forget it.

Once you set the username and password, take the opportunity to update Debian:

| Bash |
| ------------------------- |
| `sudo apt update && sudo apt upgrade` |

#### Important notes

- If you shut down or restart your computer, you will need restart your Linux installation. When necessary, use this command:

| Powershell |
| ------------------------- |
| `wls` |

- If you have problems with WSL, check if you can find the solution at [Troubleshooting Windows Subsystem for Linux](https://learn.microsoft.com/en-us/windows/wsl/troubleshooting?source=recommendations).

- For a list of basic WSL commands visit [Basic commands for WSL](https://learn.microsoft.com/en-us/windows/wsl/basic-commands?source=recommendations).

- To open your WSL project in Windows File Explorer, enter:

| Bash |
| ---- |
| `explorer.exe .` |

*Be sure to add the period at the end of the command to open the current directory*.

- Store your project files on the same operating system as the tools you plan to use. For more datails see [File storage and performance across file systems](https://learn.microsoft.com/en-us/windows/wsl/filesystems#file-storage-and-performance-across-file-systems)