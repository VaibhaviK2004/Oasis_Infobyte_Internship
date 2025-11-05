Task 3: SQL Injection on DVWA (Low Security)

Let's break down each step in detail, including which tools to use and how to perform them. This guide assumes you are using Kali Linux or another Debian-based system, but the process is similar for Ubuntu or other Linux distributions.
1. Install and Configure DVWA

Tool: Terminal (for commands), Web browser (for setup)

Steps:

    Update your system and install dependencies:

bash
sudo apt update
sudo apt install apache2 mariadb-server php php-mysql git php-gd php-mbstring php-xml php-curl -y

Start Apache and MariaDB:

bash
sudo systemctl start apache2
sudo systemctl start mariadb
sudo systemctl enable apache2
sudo systemctl enable mariadb

Download DVWA:

bash
cd /var/www/html
sudo git clone https://github.com/digininja/DVWA.git
sudo mv DVWA dvwa

Set permissions:

    bash
    cd /var/www/html/dvwa
    sudo chown -R www-data:www-data /var/www/html/dvwa
    sudo chmod -R 755 /var/www/html/dvwa

2. Configure the Database

Tool: Terminal (MariaDB/MySQL)

    Log in to MariaDB:

bash
sudo mysql -u root -p

Create database and user:

    sql
    CREATE DATABASE dvwa;
    GRANT ALL PRIVILEGES ON dvwa.* TO 'dvwa'@'localhost' IDENTIFIED BY 'dvwa';
    FLUSH PRIVILEGES;
    EXIT;

3. Configure DVWA Application

Tool: Terminal (nano text editor)

    Navigate to config directory and copy config file:

bash
cd /var/www/html/dvwa/config
sudo cp config.inc.php.dist config.inc.php
sudo nano config.inc.php

Edit these lines in config.inc.php:

    php
    $_DVWA[ 'db_user' ] = 'dvwa';
    $_DVWA[ 'db_password' ] = 'dvwa';

        Save and exit (in nano: Ctrl+X, then Y, then Enter).

4. Adjust PHP Configuration

Tool: Terminal (nano text editor)

    Edit PHP config file:

bash
sudo nano /etc/php/*/apache2/php.ini

Find and set:

    text
    allow_url_include = On

        Save and exit.

5. Restart Apache

Tool: Terminal

bash
sudo systemctl restart apache2

6. Set Up DVWA in Browser

Tool: Web browser (Firefox, Chrome, etc.)

    Go to:

        http://localhost/dvwa/setup.php

    Click "Create / Reset Database" to initialize DVWA.

7. Log In

Tool: Web browser

    Default credentials:

        Username: admin

        Password: password

8. Set Security Level to Low

Tool: Web browser

    Go to the "DVWA Security" tab (usually in the left sidebar).

    Set security level to "Low" and save.

9. Perform SQL Injection

Tool: Web browser

    Go to the "SQL Injection" section in DVWA.

    In the User ID field, enter:

    text
    1' OR '1'='1

    Submit the form and observe the results.

        You should see that the application returns all users or bypasses authentication, demonstrating the vulnerability.

Tools Used

    Terminal: For installation and configuration commands.

    Web browser: For DVWA setup, login, and exploitation.

    Text editor (nano): For editing configuration files.

