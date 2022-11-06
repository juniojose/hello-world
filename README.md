# hello-world by Júnio José

This repository contains systems and applications configuring notes that I use to develop computer programs and others experiences.

## About

At the time of writing this content, I am using an Asus notebook with Windows (currently running version 10).

I don't have the concern to evaluate the compatibility with this or that equipment/system. What's here works on my equipment. Try at your own risk. 

## Licence

Copyright (c) 2022 Junio Jose

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

## Contents

### Installing Windows Subsystem for Linux (WSL)

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

-  If you have problems with WSL, check if you can find the solution at [Troubleshooting Windows Subsystem for Linux](https://learn.microsoft.com/en-us/windows/wsl/troubleshooting?source=recommendations).

- For a list of basic WSL commands visit [Basic commands for WSL](https://learn.microsoft.com/en-us/windows/wsl/basic-commands?source=recommendations).

- To open your WSL project in Windows File Explorer, enter:

| Bash |
| ---- |
| `explorer.exe .` |

*Be sure to add the period at the end of the command to open the current directory*.

- Store your project files on the same operating system as the tools you plan to use. For more datails see [File storage and performance across file systems](https://learn.microsoft.com/en-us/windows/wsl/filesystems#file-storage-and-performance-across-file-systems)

### Installing Hyper Terminal Command

I like use [Hyper](https://hyper.is/) Terminal. To install, [download](https://hyper.is/#installation) the appropriate version and install it normally like any other program for Windows.

Once you’ve got Hyper installed, open the `.hyper.js` configuration file and make one key change. To do this, open Hyper (look at the Windows start bar), click on the sandwich menu (at the top left of the Hyper window [figure 1]), then click **>Edit >Preferences**.

| Figure 1 |
| -------- |
| ![Figure 1](https://github.com/juniojose/hello-world/blob/main/images/hyper.png) |

What I want is open `Bash` by default. To do this find the **shell** line and change it to `shell: 'C:\\Windows\\System32\\bash.exe',`.

### Installing Visual Studio Code with Windows Subsystem for Linux

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

### Open a WSL project in Visual Studio Code

To open a project from your WSL distribution, open the Hyper, move to project directory with [`cd`](https://linuxconfig.org/cd) command and enter: `code .`

See a Microsoft example with Ubuntu:

![Open a WSL project with Visual Code](https://learn.microsoft.com/en-us/windows/wsl/media/wsl-open-vs-code.gif)

It's important know how Visual Studio Code extensions work inside of VS Code WSL. For that see [Extensions inside of VS Code WSL](https://learn.microsoft.com/en-us/windows/wsl/tutorials/wsl-vscode#extensions-inside-of-vs-code-wsl).

#### The extensions I use in Visual Studio Code are:

- [GitLens — Git supercharged](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)

- [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python)

- [Dev Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)

- [DotENV](https://marketplace.visualstudio.com/items?itemName=mikestead.dotenv)

- [Jupyter Keymap](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter-keymap)

- [Microsoft Edge Tools for VS Code](https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools)

- [Nomo Dark Icon Theme](https://marketplace.visualstudio.com/items?itemName=be5invis.vscode-icontheme-nomo-dark)

- [Portuguese (Brazil) Language Pack for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=MS-CEINTL.vscode-language-pack-pt-BR)

- [Remote - SSH](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-ssh)

- [Remote - SSH: Editing Configuration Files](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-ssh-edit)

- [Remote Development](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack)

- [WSL](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl)

- [Bootstrap 5 Quick Snippets](https://marketplace.visualstudio.com/items?itemName=AnbuselvanRocky.bootstrap5-vscode)

- [Dependency Analytics](https://marketplace.visualstudio.com/items?itemName=redhat.fabric8-analytics)

- [EditorConfig for VS Code](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig)

- [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)

- [GitHub Pull Requests and Issues](https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github)

- [HTML CSS Support](https://marketplace.visualstudio.com/items?itemName=ecmel.vscode-html-css)

- [Import Cost](https://marketplace.visualstudio.com/items?itemName=wix.vscode-import-cost)

- [IntelliCode](https://marketplace.visualstudio.com/items?itemName=VisualStudioExptTeam.vscodeintellicode)

- [IntelliCode API Usage Examples](https://marketplace.visualstudio.com/items?itemName=VisualStudioExptTeam.intellicode-api-usage-examples)

- [isort](https://marketplace.visualstudio.com/items?itemName=ms-python.isort)

- [Jest](https://marketplace.visualstudio.com/items?itemName=Orta.vscode-jest)

- [Jupyter](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter)

- [Jupyter Cell Tags](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.vscode-jupyter-cell-tags)

- [Jupyter Notebook Renderers](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter-renderers)

- [Jupyter Slide Show](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.vscode-jupyter-slideshow)

- [Kubernetes](https://marketplace.visualstudio.com/items?itemName=ms-kubernetes-tools.vscode-kubernetes-tools)

- [Live Share](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare)

- [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)

- [Node Essentials](https://marketplace.visualstudio.com/items?itemName=afractal.node-essentials)

- [Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense)

- [PHP Debug](https://marketplace.visualstudio.com/items?itemName=xdebug.php-debug)

- [PHP Intelephense](https://marketplace.visualstudio.com/items?itemName=bmewburn.vscode-intelephense-client)

- [Pylance](https://marketplace.visualstudio.com/items?itemName=ms-python.vscode-pylance)

- [Quokka.js](https://marketplace.visualstudio.com/items?itemName=WallabyJs.quokka-vscode)

- [Test Adapter Converter](https://marketplace.visualstudio.com/items?itemName=ms-vscode.test-adapter-converter)

- [Test Explorer UI](https://marketplace.visualstudio.com/items?itemName=hbenl.vscode-test-explorer)

- [YAML](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml)

See how manager extensions on [Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-marketplace)

### Installing [GIT](https://git-scm.com/)

| Bash |
| ---- |
| `sudo apt install git` |

After install config Git file setup:

*Of course you need to change* **"Your name"** *to your preferred git username.*

| Bash |
| ---- |
| `git config --global user.name "Your Name"` |

*And "youremail @ domain.com" with the email you prefer*

| Bash |
| ---- |
| `git config --global user.email "youremail@domain.com"` |

For more details about Git on WSL see [Get started using Git on Windows Subsystem for Linux](https://learn.microsoft.com/en-us/windows/wsl/tutorials/wsl-git).

### Install [MariaBD](https://mariadb.org/)

| Bash |
| ---- |
| `sudo apt update` |
| `sudo apt install mysql-server` |

Check the installed mysql version with command `mysql --version`. Something like *mysql  Ver 15.1 Distrib 10.1.48-MariaDB, for debian-linux-gnu (x86_64) using readline 5.2* should be returned, otherwise something went wrong.

Initialize mysql with command:

| Bash |
| ---- |
| `sudo service mysql restart` |

To check mysql status use command:

| Bash |
| ---- |
| `sudo service mysql status` |

Start the security script prompts:

| Bash |
| ---- |
| `sudo mysql_secure_installation` |

Access mysql for a user configuration:

| Bash |
| ---- |
| `sudo mysql`

*Of course you should exchange a-user-name, a-password and test for data that meets your needs.*

| MySQL |
| ----- |
| ` CREATE USER 'a-user-name'@'localhost' IDENTIFIED BY "a-password";` |
| ` CREATE DATABASE test;` |
| `GRANT ALL PRIVILEGES ON test.* TO 'a-user-name'@'localhost';` |
| `FLUSH PRIVILEGES;` |
| `QUIT` |

Test connect mysql with data you entered in the previous commands:

| Bash |
| ---- |
| `mysql -u a-user-name -p` |

Check if created database is available to user:

| MySQL |
| ----- |
| `SHOW DATABASES;` |

To exit MySQL:

| MySQL |
| ----- |
| `QUIT` |

For more details see [Get started with databases on Windows Subsystem for Linux](https://learn.microsoft.com/en-us/windows/wsl/tutorials/wsl-database).

### Install [MongoDb](https://www.mongodb.com/)

Install MongoDB:

| Bash |
| ---- |
| `sudo apt install mongodb` |

Confirm installation and get the version number:

| Bash |
| ---- |
| `mongod --version` |

Open Hyper and go to your home directory and create a directory to store data:

| Bash |
| ---- |
| `cd ~` |
| `mkdir -p ~/data/db` |

Run a Mongo instance:

| Bash |
| ---- |
| `sudo service mongodb start` |

For more details see [Install MongoDB](https://learn.microsoft.com/en-us/windows/wsl/tutorials/wsl-database#install-mongodb) and [MongoDB Installation Tutorials](https://www.mongodb.com/docs/manual/installation/#mongodb-installation-tutorials).

### Install [Apache](https://www.apache.org/)

Install Apache2:

| Bash |
| ---- |
| `sudo apt update` |
| `sudo apt install apache2` |

Start Apache:

| Bash |
| ---- |
| `sudo service apache2 start` |

Check if it's working: open a browser and access the `localhost` address. You should see a page [You should see a page](http://localhost/).

## Did you like this content? Buy me a coffee!

<div>
<small>Support the <strong>author</strong> to create more educational materials. Send me a Brazilian PIX.</small>
</div>

## Contact

<a title="My LinkedIn" href="https://www.linkedin.com/in/juniojose/"><img width="64" alt="LinkedIn Logo" src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/01/LinkedIn_Logo.svg/64px-LinkedIn_Logo.svg.png"></a>
