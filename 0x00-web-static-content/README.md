# Deploy a static website onto a cloud platform

The aim of this project is to deploy the static content to an AWS cloud platform

## How Tos:
1. Ensure the website content to be deployed is already pushed to GitHub or any version control system registery
2. Create an Account in AWS
3. Lauch an EC2 instance in your AWS account
4. ssh into your EC2 instance
5. create a short bash script(deploy-static.sh) as shown below to automate the task
``` bash
#!/usr/bin/env bash

apt update -y

apt install nginx

git clone https://github.com/lawalgodwin/hng-devops.git

cd hng-devops

cp ./0x00-web-static-content/* /var/www/html
```
6. Run the command below in your EC2 instance, to make the script executable:
``` bash 
chmod +x deploy-static.sh
```
7. Finally, run the command below to, deploy and serve the content via nginx:
``` bash 
sudo ./deploy-static.sh
```
8. Just sit back and watch while you enjoy your life.

## Disclaimer:
- Please be informed that this method is not the only way of doing this as there are plethora ways this can be done.
- It is assumed you already know how to ssh into a remote linux server
- The script can be customized to your taste using variables and args. I intentionally scripted it this way for simplicity and please do not forget to replace the github repo url with yours

### Thank you
- I am always reachable email: godwinl200@gmail.com
