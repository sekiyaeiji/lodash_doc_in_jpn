lodash 3.3.1 メソッド 日本語まとめ

#Array 配列


##chunk

**グルーピング**

```
_.chunk (array, [size])
```

配列を第2引数の数値で指定した要素数ごとにグルーピングした配列を返す

```
var array = [1, 2, 3, 4, 5, 6, 7];

_.chunk (array, 3);
// [[1, 2, 3], [4, 5, 6], [7]]
```
　



##compact

**無効値削除**

```
_.compact (array)
```

配列から以下の値を削除した配列を返す

> false、null、""（空の値）、0、undefined、NaN

```
var array = [1, false, 2, null, 3, 0, 4, '', 5, undefined, 6, NaN, 7];

_.compact (array);
// [1, 2, 3, 4, 5, 6, 7]
```
　



##difference

**差分**

```
_.difference (array, [values])
```

配列から第2引数と比較して等しくないものを抽出した配列を返す

```
var array = [1, 2, 3, 4, 5, 6, 7];

_.difference (array, [1, 3, 5, 6]);
// [2, 4, 7]
```
　



##drop

**部分削除**

```
_.drop (array, [n=1])
```

配列の先頭から第2引数nの個数分の要素を削除した配列を返す

nの初期値は「1」であり、第2引数nを省略すると先頭の要素1個が削除される

```
var array = [1, 2, 3, 4, 5, 6, 7];

_.drop (array);
// [2, 3, 4, 5, 6, 7]

_.drop (array, 3);
// [4, 5, 6, 7]
```
　



##dropRight

**後方部分削除**

```
_.dropRight (array, [n=1])
```

配列の最後尾から第2引数nの個数分の要素を削除した配列を返す

nの初期値は「1」であり、第2引数nを省略すると1個削除される

```
var array = [1, 2, 3, 4, 5, 6, 7];

_.dropRight (array);
// [1, 2, 3, 4, 5, 6]

_.dropRight (array, 3);
// [1, 2, 3, 4]
```
　



##dropWhile

**条件削除**

```
_.dropWhile (array, [predicate=_.identity], [thisArg])
```

配列の先頭から第2引数の条件に合致する要素を削除した配列を返す

```
var array = [1, 2, 3, 4, 5, 6, 7];

_.dropWhile (array, function (n) {
  return n < 3;
});
// [3, 4, 5, 6, 7]
```
　



##dropRightWhile

**後方条件削除**

```
_.dropRightWhile (array, [predicate=_.identity], [thisArg])
```

配列の最後尾から第2引数の条件に合致する要素を削除した配列を返す

```
var array = [1, 2, 3, 4, 5, 6, 7];

_.dropRightWhile (array, function (n) {
  return n > 3;
});
// [1, 2, 3]
```
　



##fill

**部分埋込**　-　mutational(変化する) method

```
_.fill (array, value, [start=0], [end=array.length])
```

配列の、[start]によって指定した位置から[end]によって指定した位置までの値を、valueで指定した値に差し替えた配列を返す

このメソッドは引用元の値を変化させる

```
var array = [1, 2, 3, 4, 5, 6, 7];

_.fill (array, 9, 2, 5);
// [1, 2, 9, 9, 9, 9, 7]

array;
// [1, 2, 9, 9, 9, 9, 7]
```
　



##findIndex

**インデックス検索**

```
_.findIndex (array, [predicate=_.identity], [thisArg])
```

配列の中から第2引数の条件に最初に合致する要素のindexを返す

配列の最初の要素の場合は「0」、見つからない場合は「-1」を返す

```
var array = [1, 2, 3, 4, 5, 6, 7];

_.findIndex (array, function (n) {
  return n > 3;
});
// 3

_.findIndex (array, function (n) {
  return n === 8;
});
// -1

var array = [
  {'name': 1},
  {'name': 2},
  {'name': 3},
  {'name': 4},
  {'name': 5},
  {'name': 6},
  {'name': 7}
];

_.findIndex (array, function (n) {
  return n.name === 4;
});
// 3
```
　



##findLastIndex

**後方インデックス検索**

```
_.findLastIndex (array, [predicate=_.identity], [thisArg])
```

配列の中から第2引数の条件に最後尾側から最初に合致する要素の先頭からのindexを返す

配列の最初の要素の場合は「0」、見つからない場合は「-1」を返す

```
var array = [1, 2, 3, 4, 5, 6, 7];

_.findLastIndex (array, function (n) {
  return n < 5;
});
// 3

var array = [
  {'name': 1},
  {'name': 2},
  {'name': 3},
  {'name': 4},
  {'name': 5},
  {'name': 6},
  {'name': 7}
];

_.findLastIndex (array, function (n) {
  return n.name === 4;
});
// 3
```
　



##first

**先頭要素**

```
_.first (array)
```

配列の最初の要素の内容を返す

空の配列の場合は「undefined」を返す

↔ [last](#last)

```
var array = [1, 2, 3, 4, 5, 6, 7];

_.first (array);
// 1

var array = [
  {'name': 1},
  {'name': 2},
  {'name': 3},
  {'name': 4},
  {'name': 5},
  {'name': 6},
  {'name': 7}
];

_.first (array);
// {name: 1}

var array = [];

_.first (array);
// 'undefined'
```
　



##flatten

**階層結合**

```
_.flatten (array, [isDeep])
```

配列のネストを均す

[isDeep]オプションがtrueの場合は1階層構造になるまで均した配列を返す

[isDeep]オプションがfalseまたは省略された場合は1階層分だけ均す

→ [flattenDeep](#flattendeep)

```
var array = [1, 2, 3, 4, [5, [6, [7]]]];

_.flatten (array);
// [1, 2, 3, 4, 5, [6, [7]]]

_.flatten (array, true);
// [1, 2, 3, 4, 5, 6, 7]
```
　



##flattenDeep

**全階層結合**

```
_.flattenDeep (array)
```

配列のネストを完全に1階層になるまで均した配列を返す

```
_.flatten (array, true);
```

と同じ結果を返す

→ [flatten](#flatten)

```
var array = [1, 2, 3, 4, [5, [6, [7]]]];

_.flattenDeep (array, true);
// [1, 2, 3, 4, 5, 6, 7]
```
　



##indexOf

**検索**

```
_.indexOf (array, value, [fromIndex=0])
```

配列から第2引数の値と等しい値の要素を先頭から順に検索しその要素の先頭からのindexを返す

第3引数に数値を入力するとその要素が検索の開始地点となる

第3引数に「true」を入力するとバイナリーサーチを実行する

見つからない場合は「-1」を返す

```
var array = [5, 6, 7, 1, 2, 3, 4, 5, 6, 7];

_.indexOf (array, 6);
// 1

_.indexOf (array, 6, 3);
// 8
```
　



##initial

**最後尾削除**

```
_.initial (array)
```

最後尾の要素を削除した配列を返す

要素数が1つ以下の配列では空の配列を返す

↔ [rest](#rest)

```
var array = [1, 2, 3, 4, 5, 6, 7];

_.initial (array);
// [1, 2, 3, 4, 5, 6]

_.initial (array);
// [1, 2, 3, 4, 5, 6]

var array = [1];

_.initial (array);
// []

var array = [];

_.initial (array);
// []
```
　



##intersection

**共通部分**

```
_.intersection (array)
```

複数配列のすべてに共通に存在する値で構成された配列を返す

↔ [xor](#xor)

→ [union](#union)

```
var array1 = [1, 2, 3, 4];
var array2 = [2, 3, 4, 9];
var array3 = [1, 3, 4, 5];

_.intersection (array1, array2, array3);
// [3, 4]
```
　



##last

**最後尾要素**

```
_.last (array)
```

配列の最後尾の要素の内容を返す

空の配列の場合は「undefined」を返す

↔ [first](#first)

```
var array = [1, 2, 3, 4, 5, 6, 7];

_.last (array);
// 7

var array = [
  {'name': 1},
  {'name': 2},
  {'name': 3},
  {'name': 4},
  {'name': 5},
  {'name': 6},
  {'name': 7}
];

_.last (array);
// {name: 7}

var array = [];

_.last (array);
// 'undefined'
```
　



##lastIndexOf

**後方検索**

```
_.lastIndexOf (array, value, [fromIndex=0])
```

配列から第2引数の値と等しい値の要素を最後尾側から順に検索しその要素の先頭からのindexを返す

第3引数に数値を入力するとその要素が検索の開始地点となる

第3引数に「true」を入力するとバイナリーサーチを実行する

見つからない場合は「-1」を返す

```
var array = [5, 6, 7, 1, 2, 3, 4, 5, 6, 7];

_.lastIndexOf (array, 6);
// 8

_.lastIndexOf (array, 6, 3)
// 1
```
　



##pull

**値削除**　-　mutational(変化する) method

```
_.pull (array, [values])
```

配列から[values]に指定された値を削除した残りの配列を返す

すべて削除された場合は空の配列を返す

このメソッドは引用元の値を変化させる

同じく削除系のメソッドで破壊を伴わないメソッドに_.withoutがある

→ [without](#without)

```
var array = [1, 2, 3, 4, 5, 6, 7];

_.pull (array, 2, 4, 8);
// [1, 3, 5, 6, 7]

array;
// [1, 3, 5, 6, 7]

_.pull (array, 1, 2, 3, 4, 5, 6, 7);
// []

array;
// []
```
　



##pullAt

**位置削除**　-　mutational(変化する) method

```
_.pullAt (array, [indexes])
```

配列から[indexes]に指定された位置の要素を選抜した配列を返すとともに、引用元の配列の指定された位置の要素を削除する

配列に存在しない[indexes]を指定した場合undefinedを含んだ配列を返す

すべて削除された場合は空の配列を返す

このメソッドは引用元の値を変化させる

```
var array = [1, 2, 3, 4, 5, 6, 7];

_.pullAt (array, 0, 2, 5);
// [1, 3, 6]

array;
// [2, 4, 5, 7]

_.pullAt (array, 0, 1, 2, 3, 4, 5);
// [2, 4, 5, 7, undefined, undefined]

array;
// []
```
　



##remove

**条件削除**　-　mutational(変化する) method

```
_.remove (array, [predicate=_.identity], [thisArg])
```

配列から第2引数の条件に合致する要素を選抜した配列を返すとともに、引用元の配列の指定された条件の要素を削除する

配列に存在しない条件を指定した場合は空の配列を返す

すべて削除された場合は空の配列を返す

このメソッドは引用元の値を変化させる

```
var array = [1, 2, 3, 4, 5, 6, 7];

_.remove (array, function (n) {return n === 3;});
// [3]

array;
// [1, 2, 4, 5, 6, 7]

_.remove (array, function (n) {return n % 2 === 1;});
// [1, 5, 7]

array;
// [2, 4, 6]

_.remove (array, function (n) {return n % 2 === 0;});
// [2, 4, 6]

array;
// []
```
　



##rest

**先頭削除**

```
_.rest (array)
```

配列から第1要素を取り除いた残りの配列を返す

要素数が1つ以下の配列では空の配列を返す

↔ [initial](#initial)

```
var array = [1, 2, 3, 4, 5, 6, 7];

_.rest (array);
// [2, 3, 4, 5, 6, 7]

var array = [1];

_.rest (array);
// [2, 3, 4, 5, 6, 7]
```
　



##slice

**部分選択**

```
_.slice (array, [start=0], [end=array.length])
```

配列から第2引数と第3引数の間の要素を抜き出した配列を返す

[start]の初期値は「0」で、[end]の初期値は配列の要素数である

[start]、[end]に負数が設定された場合、配列の最後尾を起点とする位置が設定される

```
var array = [1, 2, 3, 4, 5, 6, 7];

_.slice (array, 0, 3);
// [1, 2, 3]

_.slice (array, 2, 15);
// [3, 4, 5, 6, 7]

_.slice (array, 5);
// [6, 7]

_.slice (array, -3);
// [5, 6, 7]

_.slice (array, -5, -2);
// [3, 4, 5]
```
　



##sortedIndex

**ソート済配列検索**

```
_.sortedIndex (array, value, [iteratee=_.identity], [thisArg])
```

ソート済みの配列において、valueに指定された値が存在する位置、あるいは挿入されるべき位置のindexを返す

valueに指定した値が複数存在する場合はそのうち最も小さいindexを返す

このメソッドは参照元の配列がソートされているか否かを判別せず、非ソート配列を参照しても値を返す

```
var array = [1, 3, 5, 7, 9, 11, 13];

_.sortedIndex (array, 6);
// 3

_.sortedIndex (array, 16);
// 7

var array = [1, 3, 5, 5, 5, 7, 9, 11, 13];

_.sortedIndex (array, 5);
// 2
```
　



##sortedLastIndex

**ソート済配列後方検索**

```
_.sortedLastIndex (array, value, [iteratee=_.identity], [thisArg])
```

ソート済みの配列において、valueに指定された値が存在する位置、あるいは挿入されるべき位置を最後尾から検索し、先頭からの位置のindexを返す

valueに指定した値が複数存在する場合はそのうち最も大きいindexを返す

このメソッドは参照元の配列がソートされているか否かを判別せず、非ソート配列を参照しても値を返す

```
var array = [1, 3, 5, 7, 9, 11, 13];

_.sortedLastIndex (array, 6);
// 3

_.sortedLastIndex (array, 16);
// 7

var array = [1, 3, 5, 5, 5, 7, 9, 11, 13];

_.sortedLastIndex (array, 5);
// 4
```
　



##take

**先頭部分選択**

```
_.take (array, [n=1])
```

配列の最初から第2引数で指定したインデックスまでの部分を抜き出した配列を返す

第2引数に0以下の値が指定された場合は空の配列を返す

_.slice (array, 0, [end=n])と同じ結果を返す

```
var array = [1, 2, 3, 4, 5, 6, 7];

_.take (array);
// [1]

_.take (array, 5);
// [1, 2, 3, 4, 5]

_.take (array, 15);
// [1, 2, 3, 4, 5, 6, 7]

_.take (array, 0);
// []
```
　



##takeRight

**後方部分選択**

```
_.takeRight (array, [n=1])
```

配列の第2引数で指定したインデックスから最後尾までの部分を抜き出した配列を返す

第2引数に0以下の値が指定された場合は空の配列を返す

_.slice (array, [start=n])と同じ結果を返す

```
var array = [1, 2, 3, 4, 5, 6, 7];

_.takeRight (array);
// [7]

_.takeRight (array, 5);
// [3, 4, 5, 6, 7]

_.takeRight (array, 15);
// [1, 2, 3, 4, 5, 6, 7]

_.takeRight (array, 0);
// []
```
　



##takeWhile

**先頭条件選択**

```
_.takeWhile (array, [predicate=_.identity], [thisArg])
```

配列の最初から第2引数で指定した条件に合致する値までの部分を抜き出した配列を返す

第2引数の条件に合致する値が存在しない場合は空の配列を返す

```
var array = [1, 2, 3, 4, 5, 6, 7];

_.takeWhile (array, function (n) {
  return n < 4;
});
// [1, 2, 3]

_.takeWhile (array, function (n) {
  return n < 19;
});
// [1, 2, 3, 4, 5, 6, 7]

_.takeWhile (array, function (n) {
  return n < 1;
});
// []
```
　



##takeRightWhile

**後方条件選択**

```
_.takeRightWhile (array, [predicate=_.identity], [thisArg])
```

配列の最後尾から第2引数で指定した条件に合致する値までの部分を抜き出した配列を返す

第2引数の条件に合致する値が存在しない場合は空の配列を返す

```
var array = [1, 2, 3, 4, 5, 6, 7];

_.takeRightWhile (array, function (n) {
  return n > 4;
});
// [5, 6, 7]

_.takeRightWhile (array, function (n) {
  return n > -5;
});
// [1, 2, 3, 4, 5, 6, 7]

_.takeRightWhile (array, function (n) {
  return n > 23;
});
// []
```
　



##union

**非重複選択**

```
_.union([arrays])
```

複数の配列のすべての要素を重複なく格納した配列を返す

→ [intersection](#intersection)、[xor](#xor)

```
var array1 = [1, 2, 3, 4];
var array2 = [3, 4, 9, 2];
var array3 = [1, 3, 4, 5];

_.union (array1, array2, array3);
// [1, 2, 3, 4, 9, 5]
```
　



##uniq

**一意選択**

```
_.uniq (array, [isSorted], [iteratee], [thisArg])
```

配列からユニークな値だけを抜き出した配列を返す

第2引数には、参照する配列がソートされていればtrueを、されていなければfalseを指定する

第3引数に指定した条件をもとにユニーク判定を行うこともできる

```
var array = [1, 2, 3, 4, 5, 6, 7, 1, 2, 3, 4, 5, 6, 7];

_.uniq (array);
// [1, 2, 3, 4, 5, 6, 7]

var array = [1, 1, 2, 2, 3, 4, 4, 5, 6, 6, 7, 7];

_.uniq (array, true);
// [1, 2, 3, 4, 5, 6, 7]

var array = [1, 2.5, 3, 3.5, 4, 5.5, 6, 6.5];

_.uniq (array, function (n) {
  return Math.floor(n);
});
// [1, 2.5, 3, 4, 5.5, 6]
```
　



##zip

**配列結合**

```
_.zip([arrays])
```

複数の配列から各配列の第n要素を抜き出してグループ化した配列を返す

↔ [unzip](#unzip)

→ [zipObject](#zipobject)

```
var array1 = ['one', 'two', 'three'];
var array2 = [1, 2, 3];

_.zip (array1, array2);
// [['one', 1], ['two', 2], ['three', 3]]
```
　



##zipObject

**配列オブジェクト化**

```
_.zipObject(props, [values=[]])
```

複数の配列から各配列の第n要素を抜き出してグループ化したオブジェクトを返す

→ [zip](#zip)、[unzip](#unzip)

```
var array1 = ['one', 'two', 'three'];
var array2 = [1, 2, 3];

_.zipObject (array1, array2);
// {'one': 1, 'two': 2, 'three': 3}
```
　



##unzip

**解凍する**

```
_.unzip (array)
```

zipメソッドの逆処理によって生成した複数配列を要素にもつ1つの配列を返す

↔ [zip](#zip)

→ [zipObject](#zipobject)

```
var array = [['one', 1], ['two', 2], ['three', 3]];

_.unzip (array);
// [['one', 'two', 'three'], [1, 2, 3]]
```
　



##without

**値削除（非変化性）**

```
_.without (array, [values])
```

配列から[values]に指定した値を取り除いた配列を返す

すべて削除された場合は空の配列を返す

_.withoutは_.pullと異なり参照した配列を破壊しない

→ [pull](#pull)

```
var array = [1, 2, 3, 4, 5, 6, 7];

_.without (array, 2, 4, 8);
// [1, 3, 5, 6, 7]

_.without (array, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10);
// []
```
　



##xor

**排他的論理和**

```
_.xor([arrays])
```

複数の配列から1つの配列のみに属する値を抜き出した配列を返す

↔ [intersection](#intersection)
→ [union](#union)

```
var array1 = [1, 2, 3, 4];
var array2 = [2, 4, 8, 9];
var array3 = [1, 6, 7, 9];

_.xor (array1, array2, array3);
// [3, 8, 6, 7]
```
　
　


#Chain チェーン


##_

**lodashオブジェクト化**

```
_(value)
```

lodashオブジェクト化する

```
var array = [1, 2, 3, 4, 5, 6, 7];

_(array);
// (lodash Object)

_(array).value();
// [1, 2, 3, 4, 5, 6, 7]
  
  
var array = ['a', 'b', '', 'c', 0, 'd', '', 'e', 'f', 'g'];
  
console.log(
  _(array)
  .compact()
  .slice(3)
  .first()
);
// d
```
　



##chain

**チェーン**

```
_.chain(value)
```

複数のメソッドを連結する

```
var array = ['a', 'b', '', 'c', 0, 'd', '', 'e', 'f', 'g'];

_.chain(array) // (lodash Object)
.compact()     // lodash Object(['a', 'b', 'c', 'd', 'e', 'f', 'g'])
.slice(3)      // lodash Object(['d', 'e', 'f', 'g'])
.first()       // lodash Object('d')
.value();
// 'd'
```
　



##tap

**関数挿入**

```
_.thru(value, interceptor, [thisArg])
```

チェーン内に関数を含める

```
var array = ['a', 'b', '', 'c', 0, ''];

_(array)
.compact()
.tap(function (array) {
  array.push('k');
})
.value();
// ['a', 'b', 'c', 'k']
```
　



##tap

**関数挿入**

```
_.prototype.chain()
```

チェーン内に関数を含める

```
var array = ['a', 'b', '', 'c', 0, ''];

_(array)
.compact()
.tap(function (array) {
  array.push('k');
})
.value();
// ['a', 'b', 'c', 'k']
```
　

























　
　
　
　
　
　
　
　
　
　
　
　
　
