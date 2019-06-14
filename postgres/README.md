# PostgreSQLのイメージ

* PostgreSQL 11 のDockerイメージ
* ログインの認証はdocker-compose.ymlを参照

# ビルド手順

$ docker build -t postgres11-jp .

# FAQ

## なぜビルドが必要か？

* DBセットアップ時に使用するロケールがen_US.UTF-8固定で決定されてしまうため、素のイメージでは日本ロケール ja_JP.UTF-8に変更することはできない。
* DockerfileでDBセットアップ前のコンテナで日本ロケールとする必要がある。

## なぜalpineを使用しない?

* alpineのベースイメージだとlocaledefが使えなくて、変更がめんどくさいから。

