## 前提
AWS SDK for Python(Boto3)には、AWSのリソースを操作するAPIが下記2つ用意されている。
- Client API 
- Resource API

本記事では、それぞれの特徴と違いについて確認する。

## 結論
### Client API
AWSのREST APIと1対1で対応した作りになっている。

Client APIでは、情報を得たい対象のリソースIDを引数に与えてメソッドを実行します。 
実行結果は「辞書型」で得られるため、そこから階層を辿って必要な情報を取り出すことになります。

### Resource API
AWSリソースをオブジェクト指向で取り扱えるようになっている。

Resource APIでは、まず対象のリソースを「オブジェクト」として取得してから、
オブジェクトの持つ「属性」を参照して情報を取り出すという手順になります。

## 参考サイト
- https://dev.classmethod.jp/articles/boto3-client-api-and-resource-api/
