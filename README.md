# LAMP STACK PROJECT

## WHAT'S NEEDED:

- Basic Linux Skill
- Cloud Service Provider - AWS, AZURE, DIGITAL OCEAN, etc.
- Internet Connection

## STEP 1 --> LAUNCHING EC2 INSTANCE
Launch an instance in the cloud using Ubuntu's package manager.

![](https://github.com/Adedoja/LampStack-Project/blob/main/LampStack%20Files/aws-devops.PNG)


SSH into the EC2 instance using your downloaded key and run the command below to update the

list of packages in the package manager

```
sudo apt update
```

## STEP 2 --> INSTALLING APACHE WEB SERVER
To install Apache, run this command

```
sudo apt install apache2
```

To verify that apache2 is running perfectly in your OS:

```
sudo systemctl status apache2
```

![](https://github.com/Adedoja/LampStack-Project/blob/main/LampStack%20Files/apache1-devops.PNG)

You can also check it out in your browser to view the Apache default page (http://"youripaddress":80) in your browser

![](https://github.com/Adedoja/LampStack-Project/blob/main/LampStack%20Files/apache2-devops.PNG)

## STEP 3 --> INSTALLING MYSQL
To install MySQL, run the ```
sudo apt install mysql-server
```

When prompted, confirm installation by typing Y which means yes and then ENTER.

When the installation is finished, log in to the MySQL console and  type:

```
sudo mysql
```

This will take you to the MySQL server database. Set up your password using the command below:

```
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'yourpassword';
```

To exit, run ```exit```

Then run ```sudo mysql_secure_installation```

![](https://github.com/Adedoja/LampStack-Project/blob/main/LampStack%20Files/mysql-devopos.PNG)

## STEP 4 -->  INSTALLING PHP
You have Apache installed to serve your content and MySQL installed to store and manage your data.

In addition to the php package, you’ll need php-mysql, a PHP module that allows PHP to communicate with MySQL-based databases.

You’ll also need libapache2-mod-php to enable Apache to handle PHP files. Core PHP packages will automatically be

installed as dependencies. To install these 3 packages at once, run:

```
sudo apt install php libapache2-mod-php php-mysql
```

![](https://github.com/Adedoja/LampStack-Project/blob/main/LampStack%20Files/php-devops.PNG)

## STEP 5 --> CREATING A VIRTUAL HOST
In this project, you will set up a domain called myproject, but you can replace this with any domain of your choice.

Create the directory for 'myproject' using ```mkdir``` command as follows:

```
sudo mkdir /var/www/myproject
```
Next, assign ownership of the directory with your current system user:

```
sudo chown -R $USER:$USER /var/www/myproject
```

After that, assign ownership of the directory with your current system user:

```
sudo chown -R $USER:$USER /var/www/myproject
```

Create and open a new configuration file in Apache’s sites-available directory using:

```
sudo vim /etc/apache2/sites-available/myproject.conf
```

This will create a new blank file.

Paste in the following bare-bones configuration by hitting on i on the keyboard to enter the insert mode, and paste the text:

```
<VirtualHost *:80>
ServerName myproject
ServerAlias www.myproject
ServerAdmin webmaster@localhost
DocumentRoot /var/www/myproject
ErrorLog ${APACHE_LOG_DIR}/error.log
CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

Use ```a2ensite``` command to enable the new virtual host:

sudo ```a2ensite``` newproject

To disable Apache’s default website use a2dissite command, type:

```
sudo a2dissite 000-default
```

To make sure your configuration file doesn’t contain syntax errors, run:

```
sudo apache2ctl configtest
```

Reload Apache so these changes take effect:

``` 
sudo systemctl reload apache2
```









