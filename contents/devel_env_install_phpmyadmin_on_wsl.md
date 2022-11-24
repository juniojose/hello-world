# Install [phpmyadmin](https://www.phpmyadmin.net/) on WSL

| Bash |
| ---- |
| `sudo apt update` |
| `sudo apt install phpmyadmin php-mbstring php-gd php-mcrypt` |
| `sudo nano /etc/apache2/apache2.conf` |

Now insert the `Include /etc/phpmyadmin/apache.conf` at the end of `apache2.conf` file:

| Nano |
| ---- |
| `Include /etc/phpmyadmin/apache.conf` |

Check it:

| Bash |
| ---- |
| `sudo service apache2 restart` |

Open a browser and access the `localhost/phpmyadmin` address.
