Vouch Proxy
===========

Step by step guide to run [vouch](https://github.com/vouch/vouch) (aka [lasso](https://github.com/LassoProject/lasso)) against Auth0 

Build
-----

```bash
#git clone git@github.com:LassoProject/lasso.git 
git clone git@github.com:vouch/vouch.git
cd  lasso
./do.sh build
```

Configure
---------

```bash
cp config/config.yml_auth0 lasso/config/config.yml 
```

Open `lasso/config/config.yml` and configure


Run
---

```bash
cd lasso
./

```       
   

