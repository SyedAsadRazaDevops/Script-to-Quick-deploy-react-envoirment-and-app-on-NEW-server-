# Script-to-Quick-deploy-react-envoirment-and-app-on-NEW-server-
```
#----------INSTALL NODEJS & NPM-------------------------------#
###install nodejs and npm###
sudo apt-get install curl
sudo curl -sL https://deb.nodesource.com/setup_16.x | sudo -E bash -
sudo apt-get install nodejs
sudo apt install nodejs

OR

**NVM is a Node Version Manager tool**. Using the NVM utility, you can install multiple node.js versions on a single system.

sudo apt install curl 
curl https://raw.githubusercontent.com/creationix/nvm/master/install.sh | bash 

source ~/.bashrc   

nvm install node 

### WORKING WITH NVM

nvm ls 
nvm ls-remote
nvm use 12.18
nvm run default --version

#----------CHECK NODE & NPM VERSION---------------------------#
node -V
npm --v

#----------INSTALL LATEST NGINX VERSION-----------------------#

sudo apt install curl gnupg2 ca-certificates lsb-release ubuntu-keyring
curl https://nginx.org/keys/nginx_signing.key | gpg --dearmor \
     | sudo tee /usr/share/keyrings/nginx-archive-keyring.gpg >/dev/null
echo "deb [signed-by=/usr/share/keyrings/nginx-archive-keyring.gpg] \
     http://nginx.org/packages/ubuntu `lsb_release -cs` nginx" \
     | sudo tee /etc/apt/sources.list.d/nginx.list
echo -e "Package: *\nPin: origin nginx.org\nPin: release o=nginx\nPin-Priority: 900\n" \
     | sudo tee /etc/apt/preferences.d/99-nginx
sudo apt update
sudo apt install nginx -y

#----------CLONE GITHUB REPO---------------------------------#
cd /public	

#----------RUN NPM AND AUDIT FIX-----------------------------#
npm install
npm audit fix

#----------INSTALL CERTBOT FOR SSL---------------------------#
sudo apt install snapd
sudo snap install core; sudo snap refresh core
sudo snap install --classic certbot
sudo ln -s /snap/bin/certbot /usr/bin/certbot

#----------GENRATE SSL FOR DOMAINS---------------------------#
sudo certbot --nginx
```
for nginx: https://github.com/SyedAsadRazaDevops/who-to-install-and-upgrade-nginx-1.20-on-Ubuntu-20.04


# NGINX Site-Avalible
Once on the server, look for your web server configuration in /etc/nginx/sites-enabled. There is also a directory called sites-allowed; this directory includes configurations that are not necessarily activated. Once you find the configuration file, display the output in your terminal with the following command:
```
cat /etc/nginx/sites-available/your_domain
```
If your site has no HTTPS certificate, you will receive a result similar to this:

Output
```
server {
	  
        listen 80;
	listen [::]:80;
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

Visit: https://www.inmotionhosting.com/support/website/ssl/lets-encrypt-ssl-ubuntu-with-certbot/

Visit: https://askubuntu.com/questions/1389719/install-nginx-1-20-2-on-ubuntu-20-04

Visit: https://dev.to/xarala221/the-easiest-way-to-deploy-a-react-web-application-2l8a
