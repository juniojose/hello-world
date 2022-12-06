# Install [MariaBD](https://mariadb.org/) on WSL

| Bash |
| ---- |
| `sudo apt update` |
| `sudo apt install default-mysql-server` |

Check the installed mysql version with command `mysql --version`. Something like *mysql  Ver 15.1 Distrib 10.1.48-MariaDB, for debian-linux-gnu (x86_64) using readline 5.2* should be returned, otherwise something went wrong.

Initialize mariadb with command:

| Bash |
| ---- |
| `sudo service mariadb restart` |

To check mariadb status use command:

| Bash |
| ---- |
| `sudo service mariadb status` |

Start the security script prompts:

| Bash |
| ---- |
| `sudo mysql_secure_installation` |

1. `Enter current password for root (enter for none):` `enter`
2. `Switch to unix_socket authentication [Y/n]` `n`
3. `Change the root password? [Y/n]` `n`
4. `Remove anonymous users? [Y/n]` `n`
5. `Disallow root login remotely? [Y/n]` `Y`
6. `Remove test database and access to it? [Y/n]` `n`
7. `Reload privilege tables now? [Y/n]` `Y`

Access mysql for a user configuration:

| Bash |
| ---- |
| `sudo mysql`

*Of course you should exchange a-user-name, a-password and test for data that meets your needs.*

| MySQL |
| ----- |
| `CREATE USER 'a-user-name'@'localhost' IDENTIFIED BY "a-password";` |
| `CREATE DATABASE test;` |
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
