# Expression Engine Docker

This bundles MariaDB, PhpMyAdmin with Caddy serving Expression Engine over HTTPS.

## Installing / Getting started

Make sure to download a copy of Expression Engine and extract all the files into the src directory.
Your src directory should look something like so.

```shell
./src
├── LICENSE
├── admin.php
├── images
├── index.php
├── system
└── themes
```

Make sure to change any configuration details such as the mysql root password before continuing.

To start the containers simply run `docker-compose up` in the root directory of this repo.
Now you should be able to access your site via `https://localhost/admin.php`.
When asked for the database details make sure to `db` for the server address. The other details will be the same ones you set in the `docker-compose.yml` file.

Once everything is setup I recommend going to `https://localhost/admin.php?/cp/settings/urls` and removing everything in `Website index page` as Caddy will rewrite `index.php` to `/` as per the Expressions Engine documentation.

PhpMyAdmin can by accessed from `http://localhost:8080`.

### Deploying

To deploy the server into production I highly suggest you look over the Caddyfile as you'll want to use a real TLS/SSL cert instead of a self signed one.
After updating the tls line with your email and replacing localhost with your domain Caddy should handle the rest.

## Contributing

If you'd like to contribute, please fork the repository and use a feature
branch. Pull requests are warmly welcome.

## Licensing

One really important part: Give your project a proper license. Here you should
state what the license is and how to find the text version of the license.
Something like:

"The code in this project is licensed under MIT license."
