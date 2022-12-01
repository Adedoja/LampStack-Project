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

```sudo apt install apache2
```

To verify that apache2 is running perfectly in your OS:

```sudo systemctl status apache2
```

![](https://github.com/Adedoja/LampStack-Project/blob/main/LampStack%20Files/apache1-devops.PNG)

You can also check it out in your browser to view the Apache default page (http://"youripaddress":80) in your browser

![](https://github.com/Adedoja/LampStack-Project/blob/main/LampStack%20Files/apache2-devops.PNG)

## STEP 3 --> INSTALLING MYSQL
To install MySQL, run the ```sudo apt install mysql-server```

When prompted, confirm installation by typing Y which means yes and then ENTER.

When the installation is finished, log in to the MySQL console and  type:

```sudo mysql
```

This will take you to the MySQL server database. Set up your password using the command below:

```ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'yourpassword';
```

To exit, run ```exit```

Then run ```sudo mysql_secure_installation```

![](https://github.com/Adedoja/LampStack-Project/blob/main/LampStack%20Files/mysql-devopos.PNG)











