# Clean Architecture 学習用アプリ

Ruby on Rails を使ってクリーンアーキテクチャを学ぶための土台です。
Docker Compose 上で動かします（ホストに Ruby/Rails のインストールは不要です）。

## セットアップ

```bash
docker compose build
docker compose run --rm web bin/rails db:prepare
```

## 起動

```bash
docker compose up
```

http://localhost:3001 でアクセスできます（ホストの 3000 番ポートが別プロジェクトで
使用中のため、3001 にマッピングしています）。

## コンテナ内でコマンドを実行する

```bash
docker compose run --rm web bin/rails console
docker compose run --rm web bin/rails generate model Book title:string
docker compose run --rm web bin/rails test
```

## 構成

* `db` サービス: PostgreSQL 16
* `web` サービス: Rails 7.2 (Ruby 3.2)
