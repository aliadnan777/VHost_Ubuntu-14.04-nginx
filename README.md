# VHost_Ubuntu-14.04-nginx

* first install nginx on your server
* `sudo apt-get install nginx`
* next step is to make directory for virtual host
* `sudo mkdir -p /var/www/daddy.com/public_html`
* now grant permission to the right user
* `sudo chown -R $USER:$USER /var/www/daddy.com/public_html`
* Additionally, it is important to make sure that everyone is able to read our new files
* `sudo chmod 755 /var/www`
* now create the index page inside the directory
* `sudo vi /var/www/daddy.com/public_html/index.html`
* add some text in index.html file
* now its time to create new virtual host file , follow below command
* `sudo cp /etc/nginx/sites-available/default /etc/nginx/sites-available/daddy.com`
* now setup the virtualhost, open daddy.com file and change following thing
* `sudo vi /etc/nginx/sites-available/daddy.com`
* change server name `daddy.com` and root `/var/www/daddy.com/public_html`
* save and exit the file
* last step is to activate the host by making symbolic link between sites-available directory and sites enable directory, in apache `a2ensite` command is used for this purpose
* `sudo ln -s /etc/nginx/sites-available/daddy.com /etc/nginx/sites-enabled/daddy.com`
* now restart your nginx server
* `sudo service nginx restart`
