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
### 一番小さい値
標準入力　横一の場合  
```
while ($line = trim(fgets(STDIN))) {
$tmp[] = $line;
}
$array = $tmp;
echo min($array);
```
### 文字の一致
標準入力　縦一  
```
while ($stdin = trim(fgets(STDIN))) {
    $stdin_array[] = $stdin;
}
    
$array = $stdin_array;
if($array[0] === $array[1]) {
    echo 'OK';
} else {
    echo 'NG';
}
```  
### Fizz Buzz
```
$input = fgets(STDIN);

for($i=1; $i <= $input; $i++) {
    
  if($i % 15 === 0):
      echo 'Fizz Buzz';
  elseif($i % 3 === 0):
      echo 'Fizz';
  elseif($i % 5 === 0):
      echo 'Buzz';
  else:
      echo $i;
  endif;
  
  echo PHP_EOL;
}
```
