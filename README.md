[![Build Status](https://travis-ci.com/marcobambini/gravity.svg?branch=master)](https://travis-ci.com/marcobambini/gravity)

<p align="center" >
<img src="https://raw.githubusercontent.com/marcobambini/gravity/master/docs/assets/images/logo-gravity.png" height="74px" alt="Gravity Programming Language" title="Gravity Programming Language">
</p>

<p>with 日本語化プロジェクト</p>

**Gravity** はパワフル、動的型付け、軽量、組み込み可能なプログラミング言語です。Ｃ言語で記述されていますが外部ライブラリに関する依存性はありません (stdlib を除く)。 <a href="https://github.com/apple/swift">Swift</a> 風の現代的なシンタックスを採用したクラスベースの並列スクリプト言語です

**Gravity** は手続き型プログラミング、オブジェクト指向プログラミング、関数型プログラミング、およびデータ駆動プログラミングをサポートしています。
特別な組み込みメソッドにより、プロトタイプベースのプログラミング言語としても使えます。

**Gravity** は <a href="http://creolabs.com" target="_blank">Creo</a> プロジェクトにおいて iOS および Android プラットフォームで移植性のあるコードを簡単に書く手段として白紙段階から開発しました。
移植性のあるＣ言語コードで記述してあるため C99 コンパイラが動作するプラットフォームでコンパイルできます。仮想マシン (VM) コードのステップ数は 4,000 行、マルチパスコンパイラ は 7,000 行、共有コードは 3,000 行です。コンパイラと仮想マシンを組み合わせたとしても 64-bit システム用の実行可能ファイルの増加サイズは 200KB 以下です。

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
	
	// vector オブジェクトで + 関数の呼び出し
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
* コルーチン (ファイバーによる)
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
<a href="https://marcobambini.github.io/gravity/#/README">Getting Started</a> (入門講座) ページでは Gravity 言語に関するダウンロードとコンパイル方法について解説しています。より詳しい解説は<a href="http://gravity-lang.org/">言語仕様書</a>にあります。なお、公式 [wiki](https://github.com/marcobambini/gravity/wiki) の用途は関連プロジェクトとツールに関する情報収集です。

## Gravity の採用事例
* Gravity は Creo (https://creolabs.com) に組み込まれているコア言語です。
* Gravity は Untold ゲームエンジン (https://youtu.be/OGrWq8jpK14?t=58) のスクリプト言語です。

## コミュニティ
Gravity に関する議論を不特定多数が行う上でグループチャットを開設するのは良い発想であると思います。<br> [![Join the chat at https://gitter.im/gravity-lang/](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/gravity-lang/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

## 寄贈
Gravity 関連の寄贈ついて歓迎と奨励します！<br>
詳細情報は公式資料である [CONTRIBUTING](CONTRIBUTING.md) ファイルに記載されています。
* <a href="https://github.com/marcobambini/gravity/issues/new">議論をはじめる</a>:
	* 援助が必要なとき
	* バグを見つけたとき
	* 機能要望があるとき
	* 一般的な質問をするとき
* <a href="https://github.com/marcobambini/gravity/pulls">プルリクエストの申請</a>:
	* 寄贈したいとき

## ライセンス
Gravity は寛容な MIT ライセンスで利用可能です。
