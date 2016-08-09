# zabbix-agent：設定方法検証

## zabbix-agentを導入してサーバ監視を自働化する

### 自動登録を使い監視対象及びグループへの追加を自動で行う  
CPU数はローレベルディスカバリを用いて動的な変更に自動対処する
#### 課題：HostnameItem と Hostname の使い分けについて調査する
HostnameItemではsystem.hostnameが使えるのでagent.confを全サーバで使いまわせる  
Hostnameではsystem.hostnameが使えないので配布時にホスト名を書き込む必要がある  
自動化を考えるとHostnameItem一択だが、  
アクティブチェックを使用する際はHostnameの方を使わなければならないかもしれない
#### 課題結果：どちらでも問題なくアクティブチェックは使える
HostnameItemで問題なく利用できた。但しログ監視を行う際はroot権限で実行できる様、  
AllowRoot=1の設定が必要  

#####関係ないけど、マークダウンの確認はatom上でやってます。

