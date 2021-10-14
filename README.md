# docker
バージョン<br>
$ docker version

### imageの操作
alpine<br>
$ docker pull alpine<br>
$ docker run -it alpine bin/sh<br>
接続は-itオプション

Web server<br>
$ sudo docker run --name static-site -e AUTHOR="Docker" -d -p 80:80 seqvence/static-site

イメージの確認<br>
$ docker images<br>
$ docker images ls<br>
イメージ削除<br>
$ docker rmi hello-world

### コンテナ操作
hello worldコンテナの実行<br>
$ docker run hello-world<br>
起動中のコンテナ確認<br>
$ docker ps
停止中のコンテナ確認<br>
$ docker ps -a

stop<br>
$ docker stop d483da6aee04<br>
start<br>
$ docker start d483da6aee04<br>
attach<br>
$ docker attach d483da6aee04
コンテナ削除<bx
$ docker rm 822cff

### Webappの作成方法
1. Dockerfileを作成する
