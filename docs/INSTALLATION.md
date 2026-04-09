PrestaShop Deployment on AWS – Installation Guide

This document provides a detailed step‑by‑step guide for deploying PrestaShop on AWS using EC2 for the application and RDS (MySQL) for the database. All steps leverage AWS Free Tier resource below.


1. EC2 Instance Setup
Launch an EC2 instance (Ubuntu 20.04 LTS).
Configure Security Groups:
Allow HTTP (80), HTTPS (443), and SSH (22).
Connect via SSH:
Bash
  ssh -i your-key.pem ubuntuEC2-Public-IP

Update packages:(Your terminal)
  sudo apt update && sudo apt upgrade -y

Install Apache, PHP, and required extensions:
Bash;
  sudo apt install apache2 php php-mysql libapache2-mod-php unzip -y

2. RDS Database Setup
Create an RDS MySQL instance (Free Tier).
Configure Security Group to allow MySQL (3306) from EC2.
Note down:
  RDS endpoint
	Database name
 	Username & password

3. PrestaShop Installation
   Download PrestaShop:
   Bash;
     wget https://download.prestashop.com/download/releases/prestashop_1.7.8.9.zip

Extract and move files:
Bash;
   unzip prestashop_1.7.8.9.zip -d prestashop
    sudo mv prestashop/* /var/www/html/

Set permissions:
Bash;
sudo chown -R www-data:www-data /var/www/html/
sudo chmod -R 755 /var/www/html/

Restart Apache:
Bash;
sudo systemctl restart apache2

4. Connect PrestaShop to RDS
Open browser: enter http://EC2-public-IP
Follow installer steps:
Enter RDS endpoint, DB name, username, password.
Complete installation.

5. Post‑Installation Security
Bash;
sudo rm -rf /var/www/html/install

Verify:
Front Office: http://EC2-Public-IP 
Back Office: http://EC2-Public-IP>/admin***

6. Screenshots
See /docs/screenshot/ for: 
EC2 setup
RDS setup
PrestaShop installer
Final Front Office & Back Office

Conclusion
You now have a fully deployed PrestaShop e‑commerce platform on AWS using EC2 and RDS, secured and ready for use.








