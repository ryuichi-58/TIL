### ログアウト処理とは？
下記の２つの処理を行うこと　＝　ログアウト
  -セッションを破棄する   
  -ログイン情報を記憶しているCookieを削除する  
  
  公式より  
  session_destroy() を呼ぶ必要はなくセッションデータを破棄するよりも、  
  $_SESSION 配列をクリーンアップする。
