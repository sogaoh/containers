# portainer

## これは何？
個人的に portainer を動かしてみる意図の環境起動用ファイル一式です

## Pre-requirements
- Docker
- docker-compose


## 起動方法

起動
```
cd ${your_work_directory}

git clone https://github.com/sogaoh/containers.git
cd containers/portainer

docker-compose up -d
```

Call http://localhost:9000 , then decide `admin` user password.


## refs

- https://portainer.readthedocs.io/en/latest/deployment.html#deploy-portainer-via-docker-compose
