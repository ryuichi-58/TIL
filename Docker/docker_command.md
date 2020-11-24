docker-compose.ymlにはコンテナの情報が記載されている

### 新コマンド
「コマンド」「サブコマンド」を使って  
「何を」「どうするか」を表現できるようになった。  
  
docker image build   :Dockerfileからイメージを構築  
docker image ls      :イメージを一覧で表示  
docker image rm	     :イメージを削除  
docker container run :新しいコンテナを起動  
docker container ls  :コンテナの一覧を表示  
docker container rm  :コンテナを削除  
  
FROM    :ベースイメージを指定する。  
RUN     :コマンドを実行し、その結果をDockerイメージにコミットする。  
WORKDIR :作業ディレクトリを指定。  
COPY    :Dockerビルドを実行するホスト上からファイルやディレクトリをコピー。  
CMD     :コンテナ実行時のデフォルトのコマンドを指定。  

build	  :サービスのimageをビルド
restart	:サービスを再起動
run	    :サービスを起動
up	    :サービスのimageをビルド＆起動
exec	  :サービスに対してコマンドを実行
logs	  :サービスのログを出力
stop	  :サービスを停止させる
kill    :サービスをkillする

docker-compose ps   コンテナ一覧表示
docker-compose up   プロジェクト内のコンテナすべて起動
docker-compose exec #{container} ${command}  コンテナに入る


