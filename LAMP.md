# DevOps
Install Linux, Apache, MySQL, PHP (LAMP) stack
**----cmd------**
sudo apt update -y
sudo apt install apache2

**-------- Status & start -------**
sudo systemctl status apache2
sudo systemctl start apache2
sudo systemctl enable apache2


---Apache Firewall rule---
sudo ufw app list
sudo ufw allow in "Apache"
sudo ufw status
sudo ufw enable

----Install Mariadb-server & Mariadb-client----
sudo apt install mariadb-server mariadb-client -y
sudo systemctl status mariadb
sudo systemctl start mariadb

---- Installing MySQL-----
sudo mysql_secure_installation

---- Installing PHP-------
sudo apt install php php-mysql php-gd php-cli php-common -y

-------- File unzip-----
sudo apt install unzip

-------Download Wordpress-----
sudo wget https://wordpress.org/latest.zip

--- Copy Wordpress files to html directory----
sudo cp -r wordpress/* /var/www/html/

---- File owner change---
sudo chown www-data:www-data -R /var/www/html/

---create database----
sudo mysql -u root -p
create database wordpress;
create user "admin"@"%" identified by "Admin123";
grant all privileges on wordpress.* to "admin"@"%";

------------Basic cmd----------
sudo systemctl stop apache2
sudo systemctl start apache2
sudo systemctl restart apache2
sudo systemctl status apache2



---Other Firewall rule---
sudo ufw allow OpenSSH
sudo ufw allow 80/tcp
sudo ufw allow 443/tcp
sudo ufw allow 5349/tcp
sudo ufw allow 3478/udp
sudo ufw allow 10000/udp
sudo ufw allow 25/tcp
sudo ufw status
If not enable firewall then ( sudo ufw enable )
