# learning-docker: Dockerの練習

## ミニレポート

### Q1-1: 同じ `docker container run` コマンドを2回実行すると、1回目と2回目で違いはありますか？どう違いますか？

1回目は時間がかかり、2回目はすぐに'Hello World'と表示された。

### Q1-2: なぜ違いますか？

1回目はUbuntuのイメージのダウンロードからはじめていたから。

### Q1-3: `docker container ls` と `docker container ls -a` はどう違いますか？

実行中のコンテナが無かったため'docker container ls'はテーブルのヘッダーだけ表示されたのに対して、
'docker container ls -a'では過去に実行したものが全てテーブル形式で表示された。

### Q1-4: `docker image ls` と `docker container ls -a` はどう違いますか？（間違ってもいいので、自分の考えを述べてください）

'docker image ls' では実行時までに取得しているイメージが表示され、
'docker container ls -a'ではコンテナを識別するためのID、起動する際に使用したイメージなどが細かく表示された。

### Q1-5: `ubuntu` イメージでの `cat /etc/issue` の結果をペーストしてください

Ubuntu 18.04.3 LTS \n \l

### Q1-6: `docker image ls` と `docker container ls -a` はどう変化しましたか？

'docker image ls'には特に変化が見られなかったが、
'docker container ls -a'ではBashにログインした事が
他のコンテナ情報と同じく記録されていた。

### Q2-1: `-d` (デタッチド・モード) でコンテナを起動すると、どのような状態になりましたか？

'docker container ls'で実行中である事が分かった。
他の'docker container run' コマンドを実行させることもでき、バックグラウンドで実行できている事が確認できる。

### Q2-2: http://localhost/ をブラウザで開くと、何が表示されましたか？

nginxの初期画面が表示された。

### Q2-3: コンテナの起動時と終了時で、docker container ls -a はどのように変化しましたか？

コンテナ起動時はSTATUSに「Up ○○ minutes」 と起動中である事が確認できたが、
コンテナ終了後に確認すると、「Exited (0) ○○ minutes ago」と表示され終了している事が確認できた。

### Q3-1: `docker build -t sample-image .` 実行時に表示されている `building...` は、Dockerfileのどの行から実行されましたか？

COPY ./sample.rb /usr/src/sample.rb

### Q3-2: `docker run sample-image` を実行すると、どうなりましたか？

「Hello, from Docker container!」とsample.rbに記述した内容が表示された。
