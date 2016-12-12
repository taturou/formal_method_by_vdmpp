# 第4章 練習問題

## 4.1

0以上105未満のある整数があり、それを3、5、7で割った余りをそれぞれa、b、cとする。
このとき、a、b、cから元の数を求める関数を `calculate` とする。
ここで、3、5、7の最小公倍数が105であることから、条件を満たす数は必ず1つだけ存在する。

---

### (a)

関数本体の定義を `is not yet speified` とした形で、関数 `calculate` の陰定義を与えよ。
事後条件によって、戻り値が一意に定まるように必要十分な条件を与えるようにせよ。
また、事前条件も必要と考えたならば含めるようにせよ。

#### 解答

```vdm
public calculate: nat * nat * nat -> nat
calculate(a, b, c) == is not yet specified
pre
  a < 3
  and b < 5
  and c < 7
post
  RESULT < 105
  and RESULT mod 3 = a
  and RESULT mod 5 = b
  and RESULT mod 7 = c
```

「0以上」を表現するとき、`nat`型で強制することもできるし、`int`型と事前/事後条件を組み合わせて強制することもできる。
VDM++のコードを設計書として考えたとき、どういう情報を残したいかによって決定できる。

#### 余談

事前/事後条件が不十分だと、誤った陽定義（実装）でもテストに合格する例として、ソート関数が良く挙げられる。
ソート関数の事後条件として「値が昇順に並んでいること」を定義した場合、入力と出力が別の数字の集合でも「仕様どおり」とみなされる。

---

### (b)

この「数当て」は百五減算と呼ばれており、`70 * a + 21 * b + 15 * c` を計算し、105を何回か引いて0以上105未満になるようにすれば元の数が得られることが知られている。
つまり `70 * a + 21 * b + 15 * c` を `105` で割った余りが求める数である。
関数 `calculate` の要定義を与えよ。

#### 解答

```vdm
public calculate: nat * nat * nat -> nat
calculate(a, b, c) ==
  return (70 * a + 21 * b + 15 * c) mod 105
pre
  a < 3
  and b < 5
  and c < 7
post
  RESULT < 105
  and RESULT mod 3 = a
  and RESULT mod 5 = b
  and RESULT mod 7 = c
```
