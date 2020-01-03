# nginx

My configuration files for Nginx on whichever platforms I'm using it on.

These configs follow the *sites-available* and *sites-enabled* model, whereby config files are created in *sites-available* and then made live with a symlink from *sites-enabled*. When you're happy to test your config with `sudo nginx -t`, create a symlink with:

`ln -s /path/to/etc/nginx/sites-available/sitename /path/to/etc/nginx/sites-enabled/sitename`

Inactive configurations can be left in *sites-available* and the symlink deleted to disable.

## macOS
### Mojave

Install nginx with [homebrew](https://brew.sh/): `brew install nginx`

Prepare for log files: `sudo mkdir /var/log/nginx`

Prepare for encryption: `sudo openssl dhparam -out /etc/ssl/certs/dhparam.pem 2048`

Configuration files live in: `/usr/local/etc/nginx/`

Run it: `sudo brew services start nginx`


## Ubuntu
### Bionic

Install nginx with: `sudo apt install nginx`

Prepare for encryption: `sudo openssl dhparam -out /etc/ssl/certs/dhparam.pem 2048`

Configuration files live in: `/etc/nginx/`

Run it: `sudo systemctl start nginx`
