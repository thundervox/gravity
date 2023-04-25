[![Build Status](https://travis-ci.com/marcobambini/gravity.svg?branch=master)](https://travis-ci.com/marcobambini/gravity)

<p align="center" >
<img src="https://raw.githubusercontent.com/marcobambini/gravity/master/docs/assets/images/logo-gravity.png" height="74px" alt="Gravity Programming Language" title="Gravity Programming Language">
</p>

<p>with 日本語化プロジェクト</p>

**Gravity** はパワフル、動的型付け、軽量、組み込み可能なプログラミング言語です。Ｃ言語で記述されていますが外部依存性はありません (stdlib を除く)。 <a href="https://github.com/apple/swift">Swift</a> 風の現代的なシンタックスを採用したクラスベースの並列スクリプト言語です

**Gravity** は手続き型プログラミング、オブジェクト指向プログラミング、関数型プログラミング、およびデータ駆動プログラミングをサポートしています。
特別な組み込みメソッドにより、プロトタイプベースのプログラミング言語としても使えます。

**Gravity** has been developed from scratch for the <a href="http://creolabs.com" target="_blank">Creo</a> project in order to offer an easy way to write portable code for the iOS and Android platforms. It is written in portable C code that can be compiled on any platform using a C99 compiler. The VM code is about 4K lines long, the multipass compiler code is about 7K lines and the shared code is about 3K lines long. The compiler and virtual machine combined add less than 200KB to the executable on a 64-bit system.

## Gravity コードの様相

```swift
class Vector {
	// インスタンス変数
	var x = 0;
	var y = 0;
	var z = 0;

	// コンストラクタ
	func init (a = 0, b = 0, c = 0) {
		x = a; y = b; z = c;
	}

	// インスタンスメソッド (組み込み演算子のオーバーライド)
	func + (v) {
		if (v is Int) return Vector(x+v, y+v, z+v);
		else if (v is Vector) return Vector(x+v.x, y+v.y, z+v.z);
		return null;
	}

	// インスタンスメソッド (組み込み String 変換のオーバーライド)
	func String() {
	        // 文字列補間のサポート
		return "[\(x),\(y),\(z)]";
	}
}

func main() {
	// 新規 vector オブジェクトの初期化
	var v1 = Vector(1,2,3);
	
	// 新規 vector オブジェクトの初期化
	var v2 = Vector(4,5,6);
	
	// cvector オブジェクトで + 関数の呼び出し
	var v3 = v1 + v2;
	
	// 文字列 "[1,2,3] + [4,5,6] = [5,7,9]" を返す
    	return "\(v1) + \(v2) = \(v3)";
 }
 ```

## 主要機能
* マルチパスコンパイラ
* 動的型付け
* クラスと継承
* 高階関数とクラス
* レキシカルスコープ
* コルーチン (via fibers)
* 入れ子クラス
* クロージャ
* ガベージコレクション
* 演算子のオーバーライド
* パワフルな組み込み API
* 組み込みユニットテスト
* 組み込み JSON シリアライザとデシリアライザ
* **セミコロンの省略可能**

## Special thanks
Gravity was supported by a couple of open-source projects. The inspiration for closures comes from the elegant <a href="http://www.lua.org" target="_blank">Lua</a> programming language; specifically from the document <a href="http://www.cs.tufts.edu/~nr/cs257/archive/roberto-ierusalimschy/closures-draft.pdf">Closures in Lua</a>. For fibers, upvalues handling and some parts of the garbage collector, my gratitude goes to <a href="http://journal.stuffwithstuff.com" target="_blank">Bob Nystrom</a> and his excellent <a href="https://github.com/munificent/wren">Wren</a> programming language. A very special thanks should also go to my friend **Andrea Donetti** who helped me debugging and testing various aspects of the language.

## 取扱説明書
The <a href="https://marcobambini.github.io/gravity/#/README">Getting Started</a> page is a guide for downloading and compiling the language. There is also a more extensive <a href="http://gravity-lang.org">language documentation</a>. Official [wiki](https://github.com/marcobambini/gravity/wiki) is used to collect related projects and tools.

## Gravity の採用事例
* Gravity is the core language built into Creo (https://creolabs.com)
* Gravity is the scripting language for the Untold game engine (https://youtu.be/OGrWq8jpK14?t=58)

## コミュニティ
Seems like a good idea to make a group chat for people to discuss Gravity.<br> [![Join the chat at https://gitter.im/gravity-lang/](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/gravity-lang/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

## Contributing
Contributions to Gravity are welcomed and encouraged!<br>
More information is available in the official [CONTRIBUTING](CONTRIBUTING.md) file.
* <a href="https://github.com/marcobambini/gravity/issues/new">Open an issue</a>:
	* if you need help
	* バグを見つけたとき
	* if you have a feature request
	* to ask a general question
* <a href="https://github.com/marcobambini/gravity/pulls">Submit a pull request</a>:
	* if you want to contribute

## ライセンス
Gravity is available under the permissive MIT license.
