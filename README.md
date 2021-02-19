## Setup

```shell
$ docker-compose up --build -d
# srcフォルダの中身空にして実行する
$ docker-compose exec web composer create-project --prefer-dist laravel/laravel . "5.5.*"# permittionエラーの場合はsudoをつける
```

### The stream or file "/var/www/storage/logs/laravel.log" could not be opened: failed to open stream: Permission denied

```shell
sudo chmod -R 777 src/
```

### npm install

```shell
$ docker-compose run --rm node npm install
```
