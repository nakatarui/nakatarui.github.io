+++
date = '2024-12-21T19:23:22+09:00'
draft = false
title = 'LinuxでDNSを変更する'
+++
## DNSを変更する
Linux では`/etc/resolv.conf`ファイルを使ってDNS の設定をします。  
`/etc/resolv.conf`はテキストファイルで、下の書式の通りに記述することで設定します。  
```
nameserver DNSのipアドレス
```
例えば、DNSをGoogleの`8.8.8.8`に設定したいときはこう記述します。  
```
nameserver 8.8.8.8
```
簡単ですね。  

また、複数のDNSを設定することもできます。  
複数設定することで、普段使っているDNSが使えなくなっても2番目、3番目のDNSへの接続をしてくれます。  
ファイルの上から順にそのDNSの優先順位が変わります。  
```
nameserver 0.0.0.1 # 一番優先順位の高いDNS(普段つかう)
nameserver 0.0.0.2 # ２番目(一番目のDNSが使えないときに使う)
nameserver 0.0.0.3 # ３番目(1番目、2番目のDNSが使えないときに使う)
```
## DNSの削除
をしたいときは`/etc/resolv.conf`を開いて削除したいDNSがある行を削除、またはその行の先頭に`#`を追加してコメントにすることができます。  
```
# nameserver 0.0.0.0 # この行は無視される。  
```