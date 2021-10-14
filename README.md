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
Dockerfileを作成する
```
FROM python:3.6

# 作業ディレクトリ
WORKDIR /app

# カレントディレクトリをコンテナの/appにコピー
ADD . /app

# requirmentsをインストール
RUN pip install --trusted-host pypi.python.org -r requirements.txt

# 80番ポート待ち受け
EXPOSE 80

# image中の環境変数
ENV NAME world

# コンテナが起動した時に実行される命令
CMD ["python", "app.py"]
```
requirement
```
Flask
```
app.py
```
from flask import Flask
import os
import socket

app = Flask(__name__)

@app.route("/")
def hello():
	html = "<h3>Hello world</h3>"
	return html.format()

if __name__ == "__main__";
	app.run(host='0.0.0.0', port=80)
```
### docker
$ sudo docker build -t hello-world .
$ sudo docker run -d -p 4000:80 hello-world     
