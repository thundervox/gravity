## ENV
ENV は環境変数との連携を可能にするクラスです。

### クラスメソッド
```swift
// 環境変数の読み取り
var value = ENV.get("VAR_NAME")

// 環境変数の書き込み
ENV.set("VAR_KEY", "VAR_VALUE")

// 環境変数全体のリストを取得
var list = ENV.keys()
```

### クラス定数
```swift
var max_arg = ENV.argc - 1 
var my_arg = ENV.argv[max_arg]
```
