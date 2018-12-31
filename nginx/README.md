Nginx Setup
===========

Compile
-------
Compile Nginx with SSL, HTTP2 and auth_request modules:

```bash
wget http://nginx.org/download/nginx-1.15.8.tar.gz
tar -zxvf nginx-1.15.8.tar.gz
cd nginx-1.15.8
brew link openssl # if running on Darwin, check for LDFLAGS and CPPFLAGS 
./configure --with-http_ssl_module \
    --with-http_v2_module \
    --with-http_auth_request_module \
    --with-ld-opt="-L/usr/local/opt/openssl/lib" \
    --with-cc-opt="-I/usr/local/opt/openssl/include"
make
``` 


Proxy Only and Terminate TLS
----------------------------

Run [PHP http server](../php/README.md)

```bash
./nginx-1.15.8/objs/nginx -p . -c conf/proxy-pass.conf
```

Vouch
-----

Run [Vouch server](../vouch/README.md)
 
```bash
./nginx-1.15.8/objs/nginx -p . -c conf/proxy-auth-vouch.conf
```


OAuth2_Proxy
-----

Run [oauth2_proxy server](../oauth2_proxy/README.md)
 
```bash
./nginx-1.15.8/objs/nginx -p . -c conf/proxy-auth-oauth2_proxy.conf

```








