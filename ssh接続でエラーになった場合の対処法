## ssh接続でエラーになった場合の対処法

### ケース1 : パーミッション問題
---
#### 概要
ssh鍵のパーミッションが正しく振られていなかった場合に起きる

```
$ ssh -i aws-ssh-key.pem ユーザー名@ホスト名
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@         WARNING: UNPROTECTED PRIVATE KEY FILE!          @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
Permissions 0644 for 'aws-ssh-key.pem' are too open.
It is required that your private key files are NOT accessible by others.
This private key will be ignored.
Load key "aws-ssh-key.pem": bad permissions
ユーザー名@ホスト名: Permission denied (publickey,gssapi-keyex,gssapi-with-mic).
```

Google翻訳してみると...
```
'aws-ssh-key.pem'のパーミッション0644があまりにも開いています。
秘密鍵ファイルには他の人がアクセスできないようにする必要があります。
この秘密鍵は無視されます。
読み込みキー "aws-ssh-key.pem"：不正なアクセス許可
ec2-user@[IPアドレス]：許可が拒否されました（publickey、gssapi-keyex、gssapi-with-mic）。
```

つまり、 **秘密鍵は他のユーザーからアクセスできるような状態では使えない** ということ。

#### 対処法
ssh鍵に対して、読み書きの権限を与えてやる。
```
$ chmod 600 xxx.key
```
