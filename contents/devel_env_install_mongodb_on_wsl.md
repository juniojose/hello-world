# Install [MongoDb](https://www.mongodb.com/) on WSL

## Preparing

| Bash |
| ---- |
| `cd ~` |
| `sudo apt update` |
| `sudo apt install gnupg2 wget curl` |
| `wget -qO- https://www.mongodb.org/static/pgp/server-5.0.asc | sudo tee /etc/apt/trusted.gpg.d/myrepo.asc` |
| `echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/5.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-5.0.list` |
| `sudo apt update` |

## Install MongoDB:

| Bash |
| ---- |
| `sudo apt install mongodb-org` |

Confirm installation and get the version number:

| Bash |
| ---- |
| `mongod --version` |

## Add the init script to start MongoDB as a service

| Bash |
| ---- |
| `curl https://raw.githubusercontent.com/mongodb/mongo/master/debian/init.d | sudo tee /etc/init.d/mongodb >/dev/null` |
| `sudo chmod +x /etc/init.d/mongodb` |

Open Hyper and go to your home directory and create a directory to store data:

| Bash |
| ---- |
| `mkdir -p ~/data/db` |

Run a Mongo instance:

| Bash |
| ---- |
| `sudo service mongodb start` |

For more details see [Install MongoDB](https://learn.microsoft.com/en-us/windows/wsl/tutorials/wsl-database#install-mongodb) and [MongoDB Installation Tutorials](https://www.mongodb.com/docs/manual/installation/#mongodb-installation-tutorials).
