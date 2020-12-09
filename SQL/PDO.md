### prepare：　値をエスケープする
危険性が高いキーワードをサニタイズ（無害化）処理を行う。  
フォームで使用している場合、受け取った内容をしている箇所は「？」を記述する。  
prepareメソッドを実行すると「PDO Statement」という形式のオブジェクトを取得でき  
その中には「execute」メソッドが備わっている。  
```
$statement = $db->prepare('INSERT INTO memos SET memo=?, created_at=NOW()');
$statement->execute(array($_POST['memo']));
```
