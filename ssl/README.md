SSL Configuration
=================
Using "Let's Encrypt" CA for the sake of this demo:

Let's Encrypt 
-------------

```bash
brew install certbot

certbot certonly --manual \
    -d private.auth0.life \
    --logs-dir . \
    --config-dir . \
    --work-dir .
```
 
ACME Challenge
--------------


```bash
cd nginx
echo DATA.SECRET > html/.well-known/acme-challenge/DATA
./nginx-1.15.8/objs/nginx -p . -c conf/acme-challenge.conf
```

Additional Login Domain (for Vouch)
-----------------------------------

```bash
certbot certonly --manual \
    -d login.auth0.life \
    --logs-dir . \
    --config-dir . \
    --work-dir .
```

Renew All Domains
-----------------

```bash
certbot renew \
        --logs-dir . \
        --config-dir . \
        --work-dir .
```
