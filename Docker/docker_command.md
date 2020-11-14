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
