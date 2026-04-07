PrestaShop Deployment on AWS

Overview
This project demonstrates deploying PrestaShop on AWS using EC2 for the application and RDS for the database, leveraging only free-tier resources.

 Architecture
EC2 Instance: Ubuntu, Apache, PHP
RDS: MySQL database
Security Groups: HTTP/HTTPS/SSH for EC2, MySQL (3306) for RDS

('docs/architecture.png')

Steps Implemented
1. Provisioned EC2 instance and installed dependencies.
2. Created RDS MySQL database and configured connectivity.
3. Installed PrestaShop and connected it to RDS.
4. Secured installation by removing `/install` folder.
5. Verified Front Office and Back Office access.

Screenshots
See `/docs/screenshots` for AWS Console, EC2 terminal, and PrestaShop installer steps.

Public URL
 Front Office: http://3.15.156.167  
 Back Office:(admin panel) http://3.15.156.167/admin7331nm7wto41w9snhgi

Author
Tony — Cyber Security specialist
