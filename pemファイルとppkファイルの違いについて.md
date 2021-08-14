## 1. pemファイルとppkファイルの違いについて
### 1-1. pemファイルとは？
---
pem ... Privacy Enhanced Mailの略。 
暗号化鍵や証明書を入れておく箱。

### 1-2. ppkファイルとは？
---

ppk ... PuTTY Private Key filesの略。
Windows限定で使用できるファイル。

### 1-3. ppk←→pemの変換
---
- Macの場合
```
//puttyをインストールする。
$ brew install putty

//ppk→pemに変換
$ puttygen ファイル名.ppk -O private-openssh -o ファイル名.pem
```

### 参考リンク
https://qiita.com/one_punch_man/items/2ad8b4664ed012bee5a7
