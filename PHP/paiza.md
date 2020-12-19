### 単一行に複数値がある場合
```
// 入力の取り出し
$input = trim(fgets(STDIN));  

// 値を半角で分解
$inputs = explode(' ', $input);　
```

### 複数行の場合
```
// 標準入力を一行ずつ配列に代入
while ($line = trim(fgets(STDIN))) {
    $tmp[] = $line;
}

// 配列の各要素をさらに分解
foreach ($tmp as $value) {
    $inputs[] = explode(' ', $value);
}

// 出力
var_dump($inputs);
```
