## Setup

```shell
$ docker-compose up --build -d
$ docker-compose run --rm -v $(pwd)/src:/app composer create-project --prefer-dist laravel/laravel <project> "5.5.*"
$ docker-compose run --rm -v $(pwd)/src:/app composer create-project --prefer-dist laravel/laravel <project> "6.*"
```

### The stream or file "/var/www/storage/logs/laravel.log" could not be opened: failed to open stream: Permission denied

```shell
sudo chmod -R 777 src/
```

### npm install

```shell
$ docker-compose exec node npm install
```

## URL\

*.lvh.me

* は ../src 直下のディレクトリ名
