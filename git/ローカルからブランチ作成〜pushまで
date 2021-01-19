1. ブランチを作成したいディレクトリに移動する  
  　git cd 〇〇  
    
2. 自分がどのブランチにいるか確認  
  　git branch (-aをつけるとリモート追跡ブランチも出力できる)
  　git checkout main <- mainにいない時だけ実行してしてmainに移動する。  
    
3. 変更等ないか確認  
  　git status  
  　※変更があれば  
  　git add 〇〇 ->git commit -v ->git push -u origin mainを実行  
    
4. mainが最新の状態か確認  
　　git pull origin mainを実行(実行して更新されなければ今の状態が最新の状態)
  
5. 新規ブランチを作成し、新規ブランチに移動する  
   git checkout -b 〇〇（新規ブランチを命名する） 
   
6. エディタに移動し、ファイルに変更を追記。  
   ファイル内容を変更しpushできるような状態にする
　　git add index.html <- index.htmlに追記したと想定 
    
7. 変更をコミットする
   git commit -v (エディタが開くと思うので変更内容を確認してコメントを記載)
   ※vscodeの場合、ここでエディターに遷移しなければ⌘＋shift＋pでshell commandを検索してインストールする  
     
8. 変更をプッシュする(pushすることでgithub上に新規ブランチが作成されている)　　
　　git push -u origin 〇〇（〇〇は5で命名したブランチ名を入力）　　
    
以上がローカルからブランチ作成〜pushまでの流れ。
