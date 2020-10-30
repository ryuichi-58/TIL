## 基本の流れ
worktree→staging→ローカルリポジトリ→リモートリポジトリ  
リモートリポジ 以外ローカル環境なのでミスれる範囲。  
init（worktreeへ）→add（stagingへ）→commit（ローカルリポジへ）→push（リモートリポジへ）  

## 頻出コマンド
git status →　addしたか確認  
git diff   →　変更を見る  
git log    →　commitメッセージ確認  
git log -p →　変更内容確認　Qで終了できる  

## 基礎テクニック　　
プッシュする前に'git push -u origin master'をやっておくと
次回から'git push'だけでよくなる。  
