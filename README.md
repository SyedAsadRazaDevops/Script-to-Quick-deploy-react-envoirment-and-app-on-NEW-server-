# Script-to-Quick-deploy-react-envoirment-and-app-on-NEW-server-

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


Visit: https://www.inmotionhosting.com/support/website/ssl/lets-encrypt-ssl-ubuntu-with-certbot/
Visit: https://dev.to/xarala221/the-easiest-way-to-deploy-a-react-web-application-2l8a
