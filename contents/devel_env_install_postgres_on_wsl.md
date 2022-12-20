# Install [PostgreSQL](https://www.postgresql.org/)

## Preparing

| Bash |
| ---- |
| `sudo apt update` |
| `sudo apt upgrade` |
| `sudo apt install lsb-release` |
| `sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'` |
| `wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc \| sudo tee /etc/apt/trusted.gpg.d/pgdg.asc` |
| `sudo apt-get update` |

## Install

| Bash |
| ---- |
| `sudo apt install postgresql` |

## Try connect

| Bash |
| ---- |
| `sudo su - postgres` |
