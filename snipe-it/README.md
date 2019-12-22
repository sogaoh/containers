# snipe-it 

## これは何？
個人的に snipe-it を動かしてみる意図の環境起動用ファイル一式です

## Pre-requirements
- Docker
- docker-compose


## 起動方法

.env の調整：以下を決めて記述してください
- YOUR_SUPER_SECRET_PASSWORD
- YOUR_snipeit_USER_PASSWORD


初回の起動
```
cd ${your_work_directory}

git clone https://github.com/sogaoh/containers.git
cd containers/snipe-it

docker-compose up -d
```

Laravel の Application key 生成

```
docker exec -it snipe-it_snipe-it_1 bash

(into container)

# php artisan key:generate

-> set generated Application key to .env `APP_KEY` section.
   (example:) APP_KEY=base64:9PwYYEeGfOblQZ9CWA2P11CfI6ZDaLx6CxBXk+YkpSA=
   then exit container.
```


再度、起動（２回目以降はここから）

``` 
docker-compose up -d
```

Call http://localhost:3051 , then start setup wizard.


## refs

- https://snipe-it.readme.io/docs/docker
