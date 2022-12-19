# Install [MongoDb](https://www.mongodb.com/) on WSL

## Preparing

| Bash |
| ---- |
| `cd ~` |
| `sudo apt update` |
| `sudo apt install gnupg2 wget curl` |
| `wget -qO- https://www.mongodb.org/static/pgp/server-5.0.asc \| sudo tee /etc/apt/trusted.gpg.d/mongodb.asc` |
| `echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/5.0 multiverse" \| sudo tee /etc/apt/sources.list.d/mongodb-org-5.0.list` |
| `sudo apt update` |

## Install MongoDB

| Bash |
| ---- |
| `sudo apt install mongodb-org` |

Confirm installation and get the version number:

| Bash |
| ---- |
| `mongod --version` |

## Add the init script to start MongoDB as a service

Try these commands:

| Bash |
| ---- |
| `curl https://raw.githubusercontent.com/mongodb/mongo/master/debian/init.d \| sudo tee /etc/init.d/mongodb >/dev/null` |
| `sudo chmod +x /etc/init.d/mongodb` |

If the error `Restarting database: mongod failed` occurs when trying to start mongo with the command `sudo service mongodb start` try it:

| Bash |
| ---- |
| `curl https://raw.githubusercontent.com/mongodb/mongo/cad54eb5ebdff24ecec53b56788cd151d8d64272/debian/init.d >/dev/null \| sudo tee /etc/init.d/mongodb` |
| `sudo chmod +x /etc/init.d/mongodb` |

## Run a Mongo instance

| Bash |
| ---- |
| `sudo service mongodb start` |

Check if it worked:

| Bash |
| ---- |
| `mongo --eval 'db.runCommand({ connectionStatus: 1 })'` |

A value of 1 for the "ok" field in the response indicates that the server is working.

For more details see [Install MongoDB](https://learn.microsoft.com/en-us/windows/wsl/tutorials/wsl-database#install-mongodb) and [MongoDB Installation Tutorials](https://www.mongodb.com/docs/manual/installation/#mongodb-installation-tutorials).
