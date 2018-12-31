OAuth2 Proxy
============

Step by step guide to run [oauth2_proxy](https://github.com/bitly/oauth2_proxy) against Auth0

Build
-----
```bash
go get github.com/bitly/oauth2_proxy
``` 


Configure
---------
Edit [oauth2_proxy-auth0.cfg](./config/oauth2_proxy-auth0.cfg) and update Auth0 tenant and client details. 


Run
---
```bash
$GOPATH/bin/oauth2_proxy -provider oidc -config config/oauth2_proxy-auth0.cfg --set-xauthrequest
```

