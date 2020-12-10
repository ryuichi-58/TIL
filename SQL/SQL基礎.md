### dockerでSQLに接続する方法
-h :host名
-u :user名
-D :datebase名（大文字なので注意！）
-p :pass 入力時に表示されないのでセキュア
```
docker-compose exec app mysql -h db -u book_log -D book_log -p
```
### TABLEを初期化したい。（既にあるテーブルを削除して新規作成する）
```
DROP TABLE IF EXISTS companies; // IF　EXISTS記載で同名のテーブルを削除できる

CREATE TABLE companies (
    id INTEGER NOT NULL AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255),
    establishment_date DATE,
    founder VARCHAR(255),
    created_at TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP
) DEFAULT CHARACTER SET=utf8mb4;
```

### PHPからMySQLへ接続するためにやっておく重要なこと
無事に接続できた場合とそうでない場合の処理を両方記載し、
どちらの処理も実行して正常に動作するかテストする。

```
<?php

$link = mysqli_connect('db', 'book_log', 'pass', 'book_log');

if (!$link) {
    echo 'Error: データベースに接続できませんでした' . PHP_EOL;
    echo 'Debugging error:' . mysqli_connect_error() . PHP_EOL;
    exit;
}

echo 'データベースに接続できました' . PHP_EOL;
mysqli_close($link);
echo 'データベースに切断しました' . PHP_EOL;
```
### 横並び一列ずつテーブルを表示させる方法
コードの末尾を「；」で終わらずに「\G」で終わらせる。
```
//コード  
SELECT * FROM companies\G   

//実行結果  
                id: 1
              name: mercari inc
establishment_date: 2013-02-01
           founder: Shintaro Yamada
        created_at: 2020-11-19 02:48:02
```
### OR条件使用時の注意
```OR```と```AND```を組み合わせる場合はORを（）で囲む必要がある。
例えば・・  
```SELECT * FORM my_items WHERE id=1 OR id=3 AND price<150 AND keyword LIKE '%甘い%'```  
これでは必ずid=1がヒットしてしまうので、 **(id=1 OR id=3)** と囲むと正常に動作する。

### WHERE句でリレーションを張る際の注意
同じカラム名がなくても、  
```AND makers.id=my_items.maker_id;```
と毎回記述する癖をつけた方が良い。  

### テーブル名のショートカット
```SELECT * FROM makers m, my_items i WHERE i . id = 1 AND m . id = i . maker_id;```  
・```makers```   →　```m```  
・```my_items``` →　```i```  
など、自由に決めて短縮することができる。
