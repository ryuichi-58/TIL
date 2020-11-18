### TABLEを初期化したい。（既にあるテーブルを削除して新規作成する）
```
DROP TABLE IF EXISTS companies; //IF　EXISTS記載で同名のテーブルを削除できる

CREATE TABLE companies (
    id INTEGER NOT NULL AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255),
    establishment_date DATE,
    founder VARCHAR(255),
    created_at TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP
) DEFAULT CHARACTER SET=utf8mb4;
```
