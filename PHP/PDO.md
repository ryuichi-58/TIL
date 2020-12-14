
### PHPからデータベースを操作する手順  
①データベースに接続する。  
②実行したいSQL文をセットする。  
③SQLに対してパラメーターをセットする。【任意】  
④実際にSQLを実行する。  
⑤結果を取得する。【任意】  
⑥データーベースから切断する。  

変動値がない場合：「query」を実行するだけで②③④を一気に処理する。  
変動値がある場合：②「prepare」⇒③「bindValue」⇒④「execute」  
**殆どの場合、変動値があるので処理は「prepare」を使うと良さそう**

### prepare：　値をエスケープする
危険性が高いキーワードをサニタイズ（無害化）処理を行う。  
フォームで使用している場合、受け取った内容をしている箇所は「？」を記述する。  
prepareメソッドを実行すると「PDO Statement」という形式のオブジェクトを取得でき  
その中には「execute」メソッドが備わっている。  
**->executeは文字列しか渡せない（bindParamは第三引数で「型」を指定できるので、エラーを避けるならbindParamを使う??）**
```
$statement = $db->prepare('INSERT INTO memos SET memo=?, created_at=NOW()');
$statement->execute(array($_POST['memo']));
```
