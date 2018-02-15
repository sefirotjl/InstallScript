# [Odoo](https://www.odoo.com "Odoo's Homepage") Install Script

This script is based on the install script from André Schenkels (https://github.com/aschenkels-ictstudio/openerp-install-scripts)
but goes a bit further and has been improved. This script will also give you the ability to define an xmlrpc_port in the .conf file that is generated under /etc/
This script can be safely used in a multi-odoo code base server because the default Odoo port is changed BEFORE the Odoo is started.

## Installation procedure

##### 1. Download the script:
```
sudo wget https://raw.githubusercontent.com/Yenthe666/InstallScript/11.0/odoo_install.sh
```
##### 2. Modify the parameters as you wish.
There are a few things you can configure, this is the most used list:<br/>
```OE_USER``` will be the username for the system user.<br/>
```INSTALL_WKHTMLTOPDF``` set to ```False``` if you do not want to install Wkhtmltopdf, if you want to install it you should set it to ```True```.<br/>
```OE_PORT``` is the port where Odoo should run on, for example 8069.<br/>
```OE_VERSION``` is the Odoo version to install, for example ```11.0``` for Odoo V11.<br/>
```IS_ENTERPRISE``` will install the Enterprise version on top of ```11.0``` if you set it to ```True```, set it to ```False``` if you want the community version of Odoo 11.<br/>
```OE_SUPERADMIN``` is the master password for this Odoo installation.<br/>

#### 3. Make the script executable
```
sudo chmod +x odoo_install.sh
```
##### 4. Execute the script:
```
sudo ./odoo_install.sh
```

##### 6. Configure Https:
 Nginx on Ubuntu 16.04 (xenial)

Install

On Ubuntu systems, the Certbot team maintains a PPA. Once you add it to your list of repositories all you'll need to do is apt-get the following packages.

$ sudo apt-get update
$ sudo apt-get install software-properties-common
$ sudo add-apt-repository ppa:certbot/certbot
$ sudo apt-get update
$ sudo apt-get install python-certbot-nginx 

Automated Get Started

Certbot has an Nginx plugin, which is supported on many platforms, and certificate installation.

$ sudo certbot --nginx

Running this command will get a certificate for you and have Certbot edit your Nginx configuration automatically to serve it. If you're feeling more conservative and would like to make the changes to your Nginx configuration by hand, you can use the certonly subcommand:

$ sudo certbot --nginx certonly

To learn more about how to use Certbot read our documentation.

Automating renewal

The Certbot packages on your system come with a cron job that will renew your certificates automatically before they expire. Since Let's Encrypt certificates last for 90 days, it's highly advisable to take advantage of this feature. You can test automatic renewal for your certificates by running this command:

$ sudo certbot renew --dry-run

More detailed information and options about renewal can be found in the full documentation.
