+++
date = '2024-12-20T15:00:29+09:00'
draft = false
title = 'ls -l の出力を見やすくする'
+++

## ls -l とは
`ls -l` は`ls`コマンドでよく使われる形です。`-l`オプションをつけることでファイルやディレクトリの詳細な情報を出力することができます。  
以下は出力例です。  

```
$ ls -l
total 20
-rw-r--r-- 1 user user 2755 Dec 20 15:08 test1
-rw-r--r-- 1 user user 3158 Dec 20 15:08 test2
-rw-r--r-- 1 user user 2997 Dec 20 15:08 test3
-rw-r--r-- 1 user user 1203 Dec 20 15:08 test4
-rw-r--r-- 1 user user 2129 Dec 20 15:08 test5
```
各行、左から順に以下ような情報が出力されています。
- 一番左の`-`はファイルのタイプを示しています。(`-`はファイルを指す)  
- パーミッション
- ハードリンクの数(すべて`1`となっている)   
- 所有者名 (user)
- 所有グループ (user)
- ファイルのサイズ(バイト単位)
- 最終更新日時
- ファイル名  

しかし、ファイルサイズの表示がバイト単位だと見にくいですね。  そこで、
## -hオプションを使う
`ls -lh`とすることで人間が読みやすい(ヒューマンリーダブルな)出力をしてくれます。  
具体的には以下のように出力することができます。  
```
$ ls -lh
total 20K
-rw-r--r-- 1 user user 2.7K Dec 20 15:08 test1
-rw-r--r-- 1 user user 3.1K Dec 20 15:08 test2
-rw-r--r-- 1 user user 3.0K Dec 20 15:08 test3
-rw-r--r-- 1 user user 1.2K Dec 20 15:08 test4
-rw-r--r-- 1 user user 2.1K Dec 20 15:08 test5
```
バイト単位だったファイルサイズがキロバイト単位になりました。  
単位が少なくなる分、だいぶ見やすくなります。  
ファイルサイズを比較したいときなどに`-h`をつけると読みやすくて良いですよ。

### 参考
- man
