### 要点  
- HTMLの本質を反映させるなら、サイトの構成とタグの意味をリンクさせることを意識する。  
- 意味を考えて極力divは使わずに、main→section→article｜asideを上手く代用していこう。
  
### OGP(Open Graph Protocol)とは  
OGPとは「Open Graph Protcol」の略で、FacebookやTwitterなどのSNSでシェアした際に、  
設定したWEBページのタイトルやイメージ画像、詳細などを正しく伝えるためのhtml要素。大切なので頭の片隅に記憶する。
  
### テクニック
- class命名の際はハイフンではなく、アンダーバーで区切る。  
そうすることで、一括で編集でき効率がよくなる。
  
- form内で、入力必須指定したい場合は**required**を使う。
  
- positon: absolute / fixedとかで高さ関係（z軸）が被ったり、潜ったりヘンになったら、z-index: 10; とかで順位調整。
  
- **wrapper** vs **container**  
  - container → 複数の要素を含むことができる。  
  - wrapper   → 単一の要素を包む。  
用語の命名は制作者にとって最も基本的で、重要なものの1つ。コードをより読みやすく、予測可能にするので慎重に定義すべし。
  
### テキストの先頭にアイコンを設置するアイデア。
<pre>
hoge::before {
  content: "";
  display: inline-block;
  width: 22px;
  height: 22px;
  margin: -3px 10px 0 0;
  background: url(fuga);
  background-size: contain;
  vertical-align: middle;
}
</pre>
  
### めっちゃ便利なセレクタ指定方法  
class^="hoge" 　hogeで始まるクラスを指定  
class$="hoge"　 hogeで終わるクラスを指定  
class*="hoge"　 hogeを含むクラスを指定  
  
### CSS命名規則：BEM  
- B /  Block  
header, menu, search, footerなどのパーツで構成されている。  
- E /  Element  
Bを構成する部品的要素。input, submit, bady, bth  
- M / Modifier  
同じBlockであっても、カレント状態であったり、通常の状態とエラー状態などで異なる装飾を設定する。current, fixed  
  
### width均等割り早見表  
: 2分割 width: 50%  
: 3分割 width: 33.3333%  
: 4分割 width: 25%  
: 5分割 width: 20%  
: 6分割 width: 16.6667%  
  
### 縦方向中央寄せ
<pre>
.base{
	position: relative;//親要素に必須
}
.child{//実際に真ん中にもってきたい要素に指定
	position: absolute;
	top: 50%;
	transform: translateY(-50%);
}
</pre>  

### headerを固定した時に生じる要素の重なりを解消  
<pre>
header {
 z-index: 10;  
{ 
</pre>  

z-indexの数値は他に設定していなければ  
1以上で最上位にヘッダーを配置できる。
  
### 画像イメージのクロップ調整に使える一行救世主！！  
<pre>
img {
  width: 250px;
  height: 250px;
  object-fit: cover; /* この一行を追加するだけ！ */
}
</pre>  
  
