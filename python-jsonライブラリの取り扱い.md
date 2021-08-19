### JSONファイルの読み込み
```python
import json

json_file = open(jsonファイルのパス , 'r')
json      = json_load(json_file)
```

### JSON => 辞書型 に変換
文字列をPythonオブジェクト（辞書型とリストの組み合わせ）へ変換するには、`loads()`関数を使用する。

```python
import json

辞書型データ = json.loads(jsonデータ)
```

### 辞書型 => JSON に変換
```python 
import json

jsonデータ = json.dumps(辞書型データ)
```
