## 入門講座

### インストール
Gravity をインストールするには、以下のコマンドを実行するだけです。これにより、コンパイラ本体である **gravity** とユニットテストランナーである **unittest** の実行可能ファイルが作成されます。
```bash
	git clone https://github.com/marcobambini/gravity.git
	cd gravity
	make
```

> システム全体で Gravity コンパイラを起動可能にしたいなら **PATH** を通してください。なお、 **Xcode** プロジェクトを使用しても gravity と unittest の実行可能ファイルを作成できます。

### コードエディタの設定
Programming is way more enjoyable when you have the right tools. That's why we've equipped several code editors with Gravity support. Just click on your favourite editor and configure it accordingly:
* [Visual Studio Code](https://github.com/Dohxis/vscode-gravity)
* [Atom](https://github.com/Tribex/atom-language-gravity)
* [vim](https://github.com/hallzy/gravity.vim)
* [BBEdit](https://github.com/marcobambini/bbedit-gravity)

### コマンドライン
利用できるフラグを表示するには以下のコマンドを実行します。
```bash
	./gravity --help
```

gravity 形式のソースファイルを json 形式の実行可能ファイルへコンパイルするには、 
```bash
	./gravity -c myfile.gravity -o exec.json
```

コンパイル済みの json 形式の実行可能ファイルを実行するには、
```bash
	./gravity -x exec.json
```

gravity 形式のままファイルを実行するには (json 形式への初回シリアライゼーション処理をしない)、
```bash
	./gravity myfile.gravity
```
### ユニットテスト
[ユニットテスト](unittest.md)はテストファイル一式があるフォルダのパスを指定することで実行できます。
```bash
	./gravity -t path_to_test_folder
```
これにより、以下のような処理結果となります。
	<img src="assets/images/unittest.png" width="666px" height="466px">

			
### Hello World
Gravity において単純な <strong>Hello World</strong> のコードは以下のとおりです。
```swift
	func main() {
		System.print("Hello World!")
	}
```
