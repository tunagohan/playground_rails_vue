## 環境構築

- 環境変数の設定

direnv などで設定してください。

```bash

export MYSQL_ROOT_PASSWORD=root_password
export MYSQL_USER=mysql_user
export MYSQL_PASSWORD=mysql_password
export DB_PORT=3307
export APP_PORT=8080

```

- 立ち上げ

```bash

$ docker-compose up -d

```

## 仕様


Service | Version
:---|:---
Rails | 6.0.0.rc1
Ruby | 2.6.3p62
Mysql | 5.7.26
yarn | 1.16.0
webpack | 4.31.0
node | 10.15.3
vue | 2.6.10



rails server と webpacker-dev-server を利用

webpacker-dev-server によって毎回 **bin/webpack** を流さなくても JSの変更を反映させることが可能です。

http://localhost:8080 にて動きます


```
config.x.webpacker[:dev_server_host] = "http://localhost:8080"
```


## 何を作るか未定