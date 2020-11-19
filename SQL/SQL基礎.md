### TABLEを初期化したい。（既にあるテーブルを削除して新規作成する）
```
DROP TABLE IF EXISTS companies; <font color="Red">// IF　EXISTS記載で同名のテーブルを削除できる</font>

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
