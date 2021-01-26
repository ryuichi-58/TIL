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
### 入力値が横一行かつそれぞれの値を分割させたい場合
```
// 例:98 75 -> 9 8 7 5に分割したい
$stdin = trim(fgets(STDIN));
$stdin_array = explode(' ', $stdin);
// $stdin_array = [98, 75];
//それぞれの値を変数 a,bに代入。

$first_num = $stdin_array[0];
// 98

$second_num = $stdin_array[1];
// 75
// それぞれの値を分割して、配列として代入する
// $first_numを分割 -> $first_num_array=[9,8]

$first_num_array = str_split($first_num);
// $second_numを分割 -> second_num_array=[7,5]

$second_num_array = str_split($second_num);
// only code 

$stdin_array = explode(' ', trim(fgets(STDIN)));
$first_num_array = str_split($stdin_array[0]);
$second_num_array = str_split($stdin_array[1]);
```
#課題
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
