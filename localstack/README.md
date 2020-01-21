# localstack

## これは何？
個人的に localstack を動かしてみる意図の環境起動用ファイル一式です


## Pre-requirements
- Docker
- docker-compose
- `aws` command  


## 起動方法

ダミーの AWS Credential 設定 
```
❯ aws configure --profile localstack
AWS Access Key ID [None]: ore-id        # たぶんなんでもよい
AWS Secret Access Key [None]: ore-key   # たぶんなんでもよい
Default region name [None]:
Default output format [None]: json
```

起動
```
cd ${your_work_directory}

git clone https://github.com/sogaoh/containers.git
cd containers/localstack

make up

# \cp -f .env.minimum .env
# TMPDIR=/private$TMPDIR docker-compose up -d
```

Then, try below.
```
❯ aws --endpoint-url http://localhost:4572 --profile localstack s3 ls s3://

❯ aws --endpoint-url http://localhost:4572 --profile localstack s3 mb s3://test

❯ aws --endpoint-url http://localhost:4572 --profile localstack s3 cp "$PWD/README.md"  s3://test

❯ aws --endpoint-url http://localhost:4572 --profile localstack s3 ls s3://test/

❯ aws --endpoint-url http://localhost:4572 --profile localstack s3 cp s3://test/README.md /path/to/out/
```

& Overview: http://localhost:7001/#!/infra 



## refs

- https://github.com/localstack/localstack
- https://hub.docker.com/r/localstack/localstack/
- [LocalStack がエラーで起動できない - Qiita](https://qiita.com/libra_lt/items/2e53ea1b523f8f9e089b)
- [AWS CLIでS3を操作するコマンド一覧 -Qiita](https://qiita.com/uhooi/items/48ef6ef2b34162988295)
