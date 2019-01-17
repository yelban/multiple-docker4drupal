# Multipe Docker4Drupal
Multiple docker zones of docker4drupal
***

### Getting Started
##### Start Traefik
* `cd ./traefix`
* `docker-compose up -d`
***

## Add Zone 1
##### Add Zone 1 network
* `docker network create client001`

##### Start Zone 1 
* `cd ../zone001`
* `docker-compose up -d`

##### Add traefik etwork link to client001_nginx
* `docker network connect --link client001_nginx:client001_nginx client001 base_traefik`

##### Installing Drupal with Drush
* `docker-compose exec php drush si standard --db-url=mysql://client001:client001.000@mariadb/drupal --account-name=admin --account-pass=password --site-name=zone01 --site-mail=noreply@example.com --locale=zh-hant -y`
***

## Add Zone 2
##### Add Zone 2 network
* `docker network create client002`

##### Start Zone 2 
* `cd ../zone002`
* `docker-compose up -d`

##### Add traefik etwork link to client002_nginx
* `docker network connect --link client002_nginx:client002_nginx client002 base_traefik`

##### Installing Drupal with Drush ( Japanese )
* `docker-compose exec php drush si standard --db-url=mysql://client002:client002.000@mariadb/drupal --account-name=admin --account-pass=password --site-name=zone01 --site-mail=noreply@example.com --locale=ja -y`
***

## Add Zone 3
##### Add Zone 3 network
* `docker network create client003`

##### Start Zone 3
* `cd ../zone003`
* `docker-compose up -d`

##### Add traefik etwork link to client003_nginx
* `docker network connect --link client003_nginx:client003_nginx client003 base_traefik`

##### Installing Drupal with Drush ( Trandictional Chinese )
* `docker-compose exec php drush si standard --db-url=mysql://client003:client003.000@mariadb/drupal --account-name=admin --account-pass=password --site-name=zone01 --site-mail=noreply@example.com --locale=zh-hant -y`

