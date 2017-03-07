# 第4章 練習問題

## 4.2

### (a)

下記の定義を含む、平面図形を表す抽象クラス `Figure` を定義せよ。
各要素のアクセス修飾子は `public` とせよ。

* 正の実数を表す型 `PositiveReal` の定義
* `<Larger>`、`<Equal>`、`<Smaller>` の三つの値のみをとりうる型 `CompareResult` の定義
* 図形の周の長さおよび面積を得る抽象操作 `getPerimeter`、`getArea` の定義。
  それぞれ、引数はなく、戻り値は `PositiveReal` 型とする。
* 二つの `Figure` を引数として受け取り、それらの面積を比較する静的(statc)関数 `compareAreas` の要定義。
  この関数の戻り値は `CompareResult` 型とする。
  戻り値は以下のように定める。
  * 第一引数の図形の方が第二引数の図形よりも面積が大きい場合 `<Larger>`
  * 第一引数の図形の方が第二引数の図形よりも面積が小さい場合 `<Smaller>`
  * 第一引数の図形と第二引数の図形の面積が等しい場合 `<Equal>`

#### 回答

```vdm
class Figure

types
pblic PositiveReal = real
inv v == v > 0;

public CompareResult = <Larger> | <Equal> | <Smaller>;

operations
public getPerimeter : () ==> PositiveReal
getPerimeter() == is subclass responsibility;

pblic getArea : () ==> PositiveReal
getArea() == is subclass responsibility;

functions
...
(未実施)
```

#### 余談

型定義は `=` で行う。
関数定義は `:` で行う。

`inv v == v > 0;` の `==` はパターンマッチ。
