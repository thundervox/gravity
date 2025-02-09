<p align="center" >
<img src="https://raw.githubusercontent.com/marcobambini/gravity/master/docs/assets/images/logo-gravity.png" height="74px" alt="Gravity プログラミング言語" title="Gravity プログラミング言語">
</p>

<p>with 日本語化プロジェクト</p>

**Gravity** はパワフル、動的型付け、軽量、組み込み可能なプログラミング言語です。Ｃ言語で記述されていますが外部ライブラリの依存性はありません (stdlib を除く)。 <a href="https://github.com/apple/swift">Swift</a> 風の現代的なシンタックスを採用したクラスベースの並列スクリプト言語です

**Gravity** は手続き型プログラミング、オブジェクト指向プログラミング、関数型プログラミング、およびデータ駆動プログラミングをサポートしています。
特別な組み込みメソッドにより、プロトタイプベースのプログラミング言語としても使えます。

**Gravity** は <a href="http://creolabs.com" target="_blank">Creo</a> プロジェクトにおいて iOS および Android プラットフォームで移植性のあるコードを気軽に書く手段として白紙段階から開発しました。

移植性のあるＣ言語コードで記述してあるため C99 コンパイラが動作するプラットフォームでコンパイルできます。仮想マシン (VM) コードのステップ数は 4,000 行、マルチパスコンパイラ は 7,000 行、共有コードは 3,000 行です。コンパイラと仮想マシンを合わせても 64-bit システム用の実行可能ファイルの増加サイズは 200KB 以下です。

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
* 動的型付け (マニュフェスト型付けは近日実装予定)
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
