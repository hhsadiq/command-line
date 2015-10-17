# server-configurations
A collection of commands which I used to configure server. Just for a backup and common place to look in future.

# Step by step guide to install first website on digital ocean with LEMP stack

Insatll LEMP stack

# Digital ocean
https://www.digitalocean.com/community/tutorials/how-to-set-up-nginx-virtual-hosts-server-blocks-on-ubuntu-12-04-lts--3
```shell
cd /var/www/html
sudo chown -R www-data:www-data /var/www/example.com/public_html
sudo ln -s /etc/nginx/sites-available/example.com /etc/nginx/sites-enabled/example.com #symlink
sudo rm /etc/nginx/sites-enabled/default

```
# Vagrant
```shell
vagrant init #initialize vagrant in new directory
vagrant up
vagrant reload --prvision #run this after updating yaml file
vagrant ssh
```

# Command line
```shell
tar czf home.tar.gz home/ #tar gz compression
tar xf file.tar #extract files
ls -l --block-size=M #listing with file sizes in MB
```


الحمد للہ۔ آج تقریبا دو ہفتے کی محنت کے بعد میں پہلی ویب سائٹ کو لائیو کرسکا ہو۔
5:59PM 17oct 2015
Digital ocean droplet, from lemp stack to launch of first site.
