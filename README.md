# docker-lamp
Simple docker Apache + PHP server with multiple PHP versions

### install docker
```
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo usermod -aG docker {user}
```

### install docker-compose
```
sudo curl -L https://github.com/docker/compose/releases/download/1.21.2/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
```

### commands
```
# run
LAMP_RUN

# restart
LAMP_R

# add host
LAMP_ADD domain.tld projet/root/ 7.4

# remove host
LAMP_DELETE domain.tld

# create db
DB_CREATE dbname

# remove db
DB_DROP dbname

# import db
DB_IMPORT file.sql dbname

# export db
DB_EXPORT dbanem file.sql

```
