# Algorithms

## Function

`strcmp(string, string)`

引数のstringを比較できるfunction

比較した文字が同じ場合は0を返す

## 構造体

オリジナルのデータ型の作成

<例>person型の作成

```c
typedef struct
{
    string name;
    string number;
}
person;
```

mainの外側でデータ型を定義するのは一般的によく用いられる

多くのfunctionで使用されることが想定されるため

## Big O (ビッグO)

各実行時間を記述するより正式な方法として、ビッグO表記を使用する

アルゴリズムのステップ数の下限の場合

Ω(n)ビッグオメガ

を使用することもある

## アルゴリズム

上限と下限を出しアルゴリズムの価値を比較する

### 選択ソート

<擬似コード>

```c
For i from 0 to n–1
    Find smallest item between i'th item and last item
    Swap smallest item with i'th item
```

n+(n–1)+(n–2)+…+1

自然数の和の公式

$n(n+1)/2$

[https://math.nakaken88.com/textbook/basic-sum-of-n/](https://math.nakaken88.com/textbook/basic-sum-of-n/)

をここで使用すると

n(n+1)/2

(n^2+n)/2

n^2/2+n/2

最大次数は2になるので

O(n^2)

選択ソートの上限はO (n^2)

### バブルソート

i番目の要素とi+1番目の要素を比較するので、iのn-2までの値を指定するだけです。次に、2つの要素が故障している場合は、それらを交換する。

<擬似コード>

```c
Repeat until sorted
    For i from 0 to n–2
        If i'th and i+1'th elements out of order
            Swap them
```

ソートが終了していたらその時点で処理をストップできる。

[https://brilliant.org/wiki/bubble-sort/](https://brilliant.org/wiki/bubble-sort/)

### マージソート

<擬似コード>

```c
If only one number
  Return
Else
    Sort left half of number
    Sort right half of number
    Merge sorted halves
```

かかる合計実行時間はO (log n)となる

それぞれの実行時間を比較

```c
O(n^2)
	選択ソート、バブルソート
O(n log n)
	マージソート
O(n)
	線形検索
O(log n)
	バイナリ検索
O(1)
```

Ωの場合でも上記と同様となる

マージソートは選択ソートやバブルソートよりも高速になる可能性があるが、マージされたリストを各段階で一時的に保管するためにより多くのメモリが必要となる。

より高速なソートのために、より高いコスト、つまりメモリ内の別の配列が必要であるというトレードオフに直面するので、実行環境に応じてアルゴリズムを使い分ける必要がある。