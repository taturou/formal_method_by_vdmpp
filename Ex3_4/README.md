# 第3章 練習問題

## 3.4

以下は、`int` 型のインスタンス変数 `x`、`y`の大小を調べ `x` の方が小さい場合のみこれらの変数の他を入れ替える操作 `swaplf` の陽定義である。

```vdm
instance variables
x : int;
y : int;

operations
public swaplf : () ==> ()
swaplf () ==
  [  ?  ];
```

例えば `x = 3`、`y = 7` のときにこの操作 `swapIf` を実行すると、`x = 7`, `y = 3` となる。
`x = 7`, `y = 3` のときであれば、操作 `swapIf` を実行しでも `x = 7 `、`y = 3` のままである。
上記操作の本体 (`==` の後の部分) には変数 `x`、`y` の大小比較をし、`x` の方が小さい場合のみ値の入れ替えのための代入を行う文が入る。
この部分に入る文を与えよ。

### 解答

```vdm
if x < y then (
  dcl tmp : int := x;
  x := y;
  y := tmp
)
```

### 補足

defを使っても書ける

```vdm
if x < y then
  def t : int := x
  (
    x := y;
    y := t
  )
```

