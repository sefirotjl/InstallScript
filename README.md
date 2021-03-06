# [Odoo](https://www.odoo.com "Odoo's Homepage") Install Script

This script is based on the install script from André Schenkels (https://github.com/aschenkels-ictstudio/openerp-install-scripts)
but goes a bit further and has been improved. This script will also give you the ability to define an xmlrpc_port in the .conf file that is generated under /etc/
This script can be safely used in a multi-odoo code base server because the default Odoo port is changed BEFORE the Odoo is started.

## Installation procedure

##### 1. Download the script:
```
sudo wget https://raw.githubusercontent.com/sefirotjl/InstallScript/11.0/odoo_install.sh
```
##### 2. Modify the parameters as you wish.
There are a few things you can configure, this is the most used list:<br/>
```OE_USER``` will be the username for the system user.<br/>
```INSTALL_WKHTMLTOPDF``` set to ```False``` if you do not want to install Wkhtmltopdf, if you want to install it you should set it to ```True```.<br/>
```OE_PORT``` is the port where Odoo should run on, for example 8069.<br/>
```OE_VERSION``` is the Odoo version to install, for example ```11.0``` for Odoo V11.<br/>
```IS_ENTERPRISE``` will install the Enterprise version on top of ```11.0``` if you set it to ```True```, set it to ```False``` if you want the community version of Odoo 11.<br/>
```OE_SUPERADMIN``` is the master password for this Odoo installation.<br/>
```DB_USER``` is the admin user for the Postgres installation.<br/>
```DB_PASSWORD``` password for the admin user for the DB.<br/>
```DB_HOST``` host to connect to the DB.<br/>

#### 3. Make the script executable
```
sudo chmod +x odoo_install.sh
```
##### 4. Execute the script:
```
sudo ./odoo_install.sh
service odoo-server status
service odoo-server start
```
##### 5. Install Nginx:
```
sudo apt-get install nginx
sudo service nginx start
```
##### 6. Configure Certificates:

The certbot-auto wrapper script installs Certbot, obtaining some dependencies from your web server OS and putting others in a python virtual environment. You can download and run it as follows:
```
wget https://dl.eff.org/certbot-auto
sudo chmod a+x ./certbot-auto
sudo ./certbot-auto --nginx -d [Public Domain Name]
```
##### 7. Configure Https Redirection:

https://www.odoo.com/documentation/11.0/setup/deploy.html#https

