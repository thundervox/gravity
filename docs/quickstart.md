## 入門講座

### インストール
Gravity をインストールするには、以下のコマンドを実行するだけです。これにより、コンパイラ本体である **gravity** とユニットテストランナーである **unittest** の実行可能ファイルが作成されます。
```bash
	git clone https://github.com/marcobambini/gravity.git
	cd gravity
	make
```

> If you want to access the gravity compiler globally just add it to your **PATH**.  
You can also use the **Xcode** project to create the gravity or unittest executables.

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

そのまま gravity 形式のファイルを実行するには (json 形式への初回シリアライゼーション処理をしない)、
```bash
	./gravity myfile.gravity
```
### ユニットテスト
You can run [unit tests](unittest.md) by providing a path to a folder containing all test files:
```bash
	./gravity -t path_to_test_folder
```
This should produce output like:
	<img src="assets/images/unittest.png" width="666px" height="466px">

			
### Hello World
A simple <strong>Hello World</strong> code in Gravity looks like:
```swift
	func main() {
		System.print("Hello World!")
	}
```
