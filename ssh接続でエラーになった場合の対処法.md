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

#### 参考サイト
- https://qiita.com/hanlio/items/c8a89244be67b1ec5b63
- https://umebius.com/dev/permissions-0644-for-xxx-key-are-too-open-%E6%A8%A9%E9%99%90%E3%82%92%E3%81%A9%E3%81%86%E3%81%99%E3%82%8C%E3%81%B0%E3%81%84%E3%81%84%EF%BC%9F/
