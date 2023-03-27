# basic-site-public

A basic website to quickly get a webserver up and running.

On AWS, launch a new instance with an Ubuntu AMI and the following bootstrap script:

```
#!/bin/bash
sudo apt update
sudo apt -y install apache2
sudo systemctl enable apache2
sudo apt -y install unzip
wget -P /home/ubuntu/ https://github.com/jdores/basic-site-public/archive/refs/heads/main.zip
unzip /home/ubuntu/main.zip -d /home/ubuntu/
sudo su
cp -a /home/ubuntu/basic-site-public-main/public/* /var/www/html/
```
