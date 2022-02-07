# Script-to-Quick-deploy-react-envoirment-and-app-on-NEW-server-
```
#install nodejs and npm
sudo apt-get install curl
curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -
sudo apt-get install nodejs
apt install nodejs
#check version of nodejs and npm
nodejs -V
npm --v
#update and install nginx 
sudo apt update
sudo apt upgrade -y
sudo apt install nginx -y
#git-hub directory path
cd /public	
#install npm
npm install
npm audit fix
#Install Certbot in Ubuntu with snapd
sudo apt install snapd
sudo snap install core; sudo snap refresh core
sudo snap install --classic certbot
sudo ln -s /snap/bin/certbot /usr/bin/certbot
#Create an SSL Certificate with Certbot
sudo certbot --nginx
```

Visit: https://www.inmotionhosting.com/support/website/ssl/lets-encrypt-ssl-ubuntu-with-certbot/

Visit: https://dev.to/xarala221/the-easiest-way-to-deploy-a-react-web-application-2l8a

# NGINX Site-Avalible
Once on the server, look for your web server configuration in /etc/nginx/sites-enabled. There is also a directory called sites-allowed; this directory includes configurations that are not necessarily activated. Once you find the configuration file, display the output in your terminal with the following command:
```
cat /etc/nginx/sites-enabled/your_domain
```
If your site has no HTTPS certificate, you will receive a result similar to this:

Output
```
server {
	  
        listen 80;
        root <my-project-path>/build;
        index index.html index.htm index.nginx-debian.html;
        server_name <my-domain> www.<my-domain>;
       
 location / {
            try_files $uri  /index.html;
        }

}

```
Next, you need to create a symbolic link within the sites-enabled directory that points out to this configuration file:
```
sudo ln -s /etc/nginx/sites-available/<my-nginx-file-name> /etc/nginx/sites-enabled
```
