# Nextcloud development environment

An development apps environment for Nextcloud.

## Development environment

### Before first run

Copy `.env.example` to `.env` and change the values of `.env`

`VERSION_NEXTCLOUD` To this environment get a or branch of [Nextcloud server repository](https://github.com/nextcloud/server).

If you want to use PostgreSQL, comment the environments of MySQL on `.env` and the MySQL service on `docker-compose.yml`. The same if you want to use MySQL, comment all about PostgreSQL on `.env` and on `docker-compose.yml`

### PHP custom settings

If you need custom settings in PHP, change the file [`.docker/app/config/php.ini`](/.docker/app/config/php.ini).

### Up services
```bash
docker-compose up -d
```
Access in the browser using the port defined on `HTTP_PORT`.

After finish the setup, access this url: http://localhost/settings/admin/overview.

## Start development of apps

You will need create (or clone) the folder of the app that you will work inside the folder `volumes/nextcloud/apps`. Because the owner of folder `apps` is the root user, you will need do the follow steps (using LibreSign app repository as example):

```bash
sudo chown $USER:$USER volumes/nextcloud/apps
git clone git@github.com:LibreSign/libresign.git volumes/nextcloud/apps/libresign
sudo chown www-data:www-data volumes/nextcloud/apps
```
Good work!
