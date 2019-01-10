# Secure Nginx

This repository contains a basic and secure configuration for the Nginx reverse proxy.

## Use

Copy the `snippets` folder content in `/etc/nginx/snippets/`.

Edit the path to your certificate and your private key files in `certs.conf`

Generate a Diffie-Hellman key with:
```shell
openssl dhparam -dsaparam -out /etc/ssl/certs/dhparam.pem 4096
```

Override the default website config in `/etc/nginx/sites-available` with the `default` file and edit the `server_name` variable.

Run 
```shell
nginx -t
```
to test the configuration is correct.

Then restart the nginx service with: 
```shell
sudo service nginx restart
```