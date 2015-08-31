# Varnish Docker container

> Debian Jessi
> Varnish 4.x

## Usage

Add the following to your docker-compose.yml file:

```
varnish:
    image: yappabe/varnish:4.0
    volumes_from:
        - app
    links:
        - nginx
    environment:
        DNSDOCK_ALIAS: varnish.yourdomain.docker
        VCL_CONFIG: /var/www/app/varnish.vcl
        VARNISHD_PARAMS: -a "0.0.0.0:8080" -T "0.0.0.0:6083" -p default_ttl=3600 -p default_grace=3600

```

## ENV vars

You can configure Varnish daemon by following env variables:

> **VCL_CONFIG** `/etc/varnish/default.vcl`
> **CACHE_SIZE** `64m`
> **VARNISHD_PARAMS** `-p default_ttl=3600 -p default_grace=3600`
