# Install Wordpress in /var/www/html on WLS

| Bash |
| ---- |
| `cd /var/www/html` |
| `sudo wget https://wordpress.org/latest.tar.gz` |
| `sudo tar -vzxf latest.tar.gz` |
| `sudo rm latest.tar.gz` |
| `cd ..` |
| `sudo chown -R www-data:www-data wordpress/` |
| `sudo find wordpress/ -type d -exec chmod 775 {} \;` |
| `sudo find wordpress/ -type f -exec chmod 664 {} \;` |

Create a database for wordpress:

| Bash |
| ---- |
| `sudo mysql` |

| MySQL |
| ----- |
| `CREATE DATABASE wordpress;` |
| `GRANT ALL PRIVILEGES ON wordpress.* TO 'a-user-name'@'localhost';` |
| `FLUSH PRIVILEGES;` |
| `QUIT` |

Check it:

Open a browser and access the `https://localhost/wordpress` address.
