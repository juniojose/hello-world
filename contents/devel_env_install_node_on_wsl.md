# Install Node.js

| Bash |
| ---- |
| `sudo apt install curl` |
| `curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/master/install.sh | bash` |

Close your current terminal. Open again.

| Bash |
| ---- |
| `command -v nvm` |

This should return `nvm`. If you receive `command not found` or no response at all, [learn more in the nvm github repo](https://github.com/nvm-sh/nvm).

List which versions of Node are currently installed (should be none at this point):

| Bash |
| ---- |
| `nvm ls` |

Install the current stable LTS release of Node.js (recommended for production applications):

| Bash |
| ---- |
| `nvm install --lts` |

Verify that Node.js is installed and the currently default version with:

| Bash |
| ---- |
| `node --version` |

Verify that you have `npm`:

| Bash |
| ---- |
| `npm --version` |

To change the version of Node.js you would like to use for a project:

| Bash |
| ---- |
| `mkdir <newproject>` |
| `cd <newproject>` |
| `nvm <nodeVersion>` |

Try NodeJS with Visual Studio Code:

[See this MS Windows tutorial](https://learn.microsoft.com/en-us/windows/dev-environment/javascript/nodejs-beginners-tutorial#try-nodejs-with-visual-studio-code)
