# Keycloak node demo
### Service Setup
```
docker run -d --name=sso -p 8080:8080 -e KEYCLOAK_LOGLEVEL=DEBUG jboss/keycloak
docker run --name nginx -p80:80 -v `pwd`/nginx.conf:/usr/local/openresty/nginx/conf/nginx.conf:ro -d openresty/openresty
git clone https://github.com/sjkyspa/keycloak-node
cd app && npm install && node app

```
### Routing
```
echo "127.0.0.1 sso.tzion.me" > /etc/hosts
echo "127.0.0.1 api.tzion.me" > /etc/hosts
```

### Keycloak setup
1. create realm named node
2. create client named node
1. create realm:admin, realm:user role
2. create user and assign role above to the user

### Visit
1. [http://api.tzion.me/service/public](http://api.tzion.me/service/public)
2. [http://api.tzion.me/service/secured](http://api.tzion.me/service/secured)
3. [http://api.tzion.me/service/admin](http://api.tzion.me/service/admin)

