# Install [MongoDb](https://www.mongodb.com/) on WSL

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
