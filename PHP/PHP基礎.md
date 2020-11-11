### 配列  
連想配列：キーが整数以外  
添字配列：キーが整数  
  
array型:$array1 = array('Alex', 'Bob', 'Mike');  
短縮構文:$array = ['Alex', 'Bob', 'Mike'];　←シンプルに書ける。  
  
### 添字配列の追加  
array_push($members, 'Sam');  
$members[] = 'Sam';  
  
### 連想配列の追加  
$members = array_merge($members, ['Andy' => 39]);  
$members = $members + ['Tom' => 32];  
$members['Lucky'] = 21;	  

### 繰り返し処理
- while   ：回数が決まっていない繰り返し処理によく使われる。
- for     ：指定した回数だけ繰り返し処理が実行される。
- foreach ：配列とオブジェクト専用の繰り返し処理を実行する。
#### 条件分岐の注意点  
elseif switchは似てるけど、switchは判断処理が==なので、比較が「緩やか」。	  

###PHP_EOLとは？
実行環境のOSに対応する改行コードを出力する定数。
文字列と定数を結合させることで実行結果を改行した状態でコンソールに出力できる。
ただ、ブラウザ上ではHTMLと認識される為改行されないので<br>で改行する。
