# 第3章 練習問題

## 3.3

以下は `int` 型の引数三つを受け取り、それらの最大値を返す関数 `max` の陽定義である。

```vdm
pub1ic max : int * int * int ->　int
max (a , b , c) ==
  [   ?   ];
```

関数の本体(`==` の後の部分)には.引数a、b、c を用いて戻り値を返す式が入る。
この部分に入る式を与えよ。

### 解答

```vdm
if a >= b then
  if a >= c then
    a
  else
    c
else
  if b >= c then
    b
else
  c
```

### 補足

* `if` は「if式」なので値を持つ (if true then A else Bの値はA)

* returnは書いても書かなくても良い

じゃあなぜreturnがあるか？？という疑問が飛んでいた。

* 式と文について、いろいろ考えさせられた。
  VDMとしてちょっと気を付けるべきなのは、以下

    ```vdm
    (
       opt(x);
       x = y+2;
    )
    ```

    だと、opt(x)後ろに制御が行かない

    ```vdm
    (
       ret = opt(x);
       x = y + 2
    )
    ```

    だと、制御を移す事ができる。

なので、ブロック式 ( .... )の中に不用意に文を並べた場合、値を持たないものなら良いが値を持つものが途中にあるだけで処理が中断する。

