# k8s-wordpress
Wordpressをkubernetes上で展開するサンプルです。
[Docker Desktop for Mac](https://hub.docker.com/editions/community/docker-ce-desktop-mac)のkubernetes環境でのみ動作確認をしています。

# 実行方法
リポジトリをcloneします。

```shell
$ git clone https://github.com/moreyhat/k8s-wordpress.git
```

wordpressを展開します。

```shell
$ kubectl apply -f manifest/
```

Port Fowordしてローカル環境からwordpressに接続できるか確認します。
ローカル環境のポート番号は任意のものを指定してください。
ここでは`9000`を指定しています。

```shell
$ kubectl port-forward service/wordpress-service 9000:80
```

ブラウザ等から`http://localhost:9000`にアクセスしてWordpressに接続できることを確認してください。