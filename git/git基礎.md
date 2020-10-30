## エイリアス備忘録
### `git config --global alias.ho hoge`
- ci commit  
- co checkout  
- br branch  
- st status  

## 基本の流れ
worktree→staging→ローカルリポジトリ→リモートリポジトリ  
リモートリポジ 以外ローカル環境なのでミスれる範囲。  
init（worktreeへ）→add（stagingへ）→commit（ローカルリポジへ）→push（リモートリポジへ）  

## 頻出コマンド
- git status →　addしたか確認  
- git diff   →　変更を見る  
- git log    →　commitメッセージ確認  
- git log -p →　変更内容確認　Qで終了できる  

## 基礎テクニック　　
- プッシュする前に'git push -u origin master'をやっておくと
次回から'git push'だけでよくなる。  

- **git pull**  
fetchとmergeを一編にできて便利、  
どのブランチに居てるか把握してからしないとファイルがめちゃくちゃになる・・。

- rebaseとmergeの違いと使い分け  
  ・親コミットが分岐しているかしていないか（rebaseは分岐なし）
  ・履歴をきれいにするか残すか（rebaseは履歴ごと消える）
  
  - **merge**
    - +: コンフリクト解決が簡単
    - -: マージコミットがあると履歴が複雑化する
    - 用途：pushした後、コンフリクトしそうな時。

  - **rebase:**
    - +: 履歴がきれいに保てる
    - -: コンフリクト解消が大変。（コミットそれぞれに解消が必要）
    - 用途：pushしてないローカルの変更。

- [ファイルの変更を取り消す]
git checkout --<ファイル名>  
git checkout --<ディレクトリ名>  
＃全変更を取り消す  
git checkout --.  

- [変更差分を確認する]
#git addする前  
git diff / git diff <ファイル名>  
#git addした後  
git diff --staged  

## 要注意
githubにプッシュしたコミットをrebaseするのはNG。  
理由:githubとローカルのデータが矛盾が生じて、githaub上のデータが優先されてしまいpushできなくなるから。  
git push -f (force) は絶対NG。  
