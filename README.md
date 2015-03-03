lodash 3.3.0 メソッド 日本語まとめ

#Array 配列


##chunk

**グルーピング**

```
_.chunk(array, [size]);
```

配列を第2引数の数値で指定した要素数ごとにグルーピングした配列を返す

```_.chunk()

var array = [1, 2, 3, 4, 5, 6, 7];

_.chunk(array, 3);
// [[1, 2, 3], [4, 5, 6], [7]]

```
　



##compact

**無効値削除**

```
_.compact(array);
```

配列から以下の値を削除した配列を返す

> false、null、""（空の値）、0、undefined、NaN

```_.compact()

var array = [1, false, 2, null, 3, 0, 4, '', 5, undefined, 6, NaN, 7];

_.compact(array);
// [1, 2, 3, 4, 5, 6, 7]

```
　



##difference

**差分**

```
_.difference(array, [values]);
```

配列から第2引数と比較して等しくないものを抽出した配列を返す

```_.difference()

var array = [1, 2, 3, 4, 5, 6, 7];

_.difference(array, [1, 3, 5, 6]);
// [2, 4, 7]

```
　



##drop

**部分削除**

```
_.drop(array, [n=1]);
```

配列の先頭から第2引数nの個数分の要素を削除した配列を返す

nの初期値は「1」であり、第2引数nを省略すると1個削除される

```_.drop()


// 

```
　



##dropRight

**後方部分削除**

```
_.dropRight(array, [n=1]);
```

配列の最後尾から第2引数nの個数分の要素を削除した配列を返す

nの初期値は「1」であり、第2引数nを省略すると1個削除される

```_.dropRight()


// 

```
　



##dropWhile

**条件削除**

```
_.dropWhile(array, [predicate=_.identity], [thisArg]);
```

配列の先頭から第2引数の条件に合致する要素を削除した配列を返す

```_.dropWhile()


// 

```
　



##dropRightWhile

**後方条件削除**

```
_.dropRightWhile(array, [predicate=_.identity], [thisArg]);
```

配列の最後尾から第2引数の条件に合致する要素を削除した配列を返す

```_.dropRightWhile()


// 

```
　



##findIndex

**インデックス検索**

```
_.findIndex(array, [predicate=_.identity], [thisArg]);
```

配列の中から第2引数の条件に最初に合致する要素のindexを返す

配列の最初の要素の場合は「0」、見つからない場合は「-1」を返す

```_.findIndex()


// 

```
　



##findLastIndex

**後方インデックス検索**

```
_.findLastIndex(array, [predicate=_.identity], [thisArg]);
```

配列の中から第2引数の条件に最後尾側から最初に合致する要素の先頭からのindexを返す

配列の最初の要素の場合は「0」、見つからない場合は「-1」を返す

```_.findLastIndex()


// 

```
　



##first

**先頭要素**

```
_.first(array);
```

配列の最初の要素の内容を返す

空の配列の場合は「undefined」を返す

↔ last

```_.first()


// 

```
　



##flatten

**階層結合**

```
_.flatten(array, [isDeep]);
```

配列のネストを均す

[isDeep]オプションがtrueの場合は1階層構造になるまで均した配列を返す

[isDeep]オプションがfalseまたは省略された場合は1階層分だけ均す

```_.flatten()


// 

```
　



##flattenDeep

**全階層結合**

```
_.flattenDeep(array);
```

配列のネストを完全に1階層になるまで均した配列を返す

_.flatten(array, true)と同じ結果を返す

```_.flattenDeep()


// 

```
　



##indexOf

**検索**

```
_.indexOf(array, value, [fromIndex=0]);
```

配列から第2引数の値と等しい値の要素を先頭から順に検索しその要素の先頭からのindexを返す

第3引数に数値を入力するとその要素が検索の開始地点となる

第3引数に「true」を入力するとバイナリーサーチを実行する

見つからない場合は「-1」を返す

```_.indexOf()


// 

```
　



##initial

**最後尾削除**

```
_.initial(array);
```

最後尾の要素を削除した配列を返す

要素数が1つ以下の配列では空の配列を返す

↔ rest

```_.initial()


// 

```
　



##intersection

**共通部分**

```
_.intersection(array);
```

複数配列のすべてに共通に存在する値で構成された配列を返す

↔ xor

→ union

```_.intersection()


// 

```
　



##last

**最後尾要素**

```
_.last(array);
```

配列の最後尾の要素の内容を返す

空の配列の場合は「undefined」を返す

↔ first

```_.last()


// 

```
　



##lastIndexOf

**後方検索**

```
_.lastIndexOf(array, value, [fromIndex=0]);
```

配列から第2引数の値と等しい値の要素を最後尾側から順に検索しその要素の先頭からのindexを返す

第3引数に数値を入力するとその要素が検索の開始地点となる

第3引数に「true」を入力するとバイナリーサーチを実行する

見つからない場合は「-1」を返す

```_.lastIndexOf()


// 

```
　



##pull

**値削除**　　`　破壊的メソッド　`

```
_.pull(array, [values]);
```

配列から[values]に指定された値を削除した残りの配列を返す

すべて削除された場合は空の配列を返す

このメソッドは引用元の値を破壊する

同じく削除系のメソッドで破壊を伴わないメソッドに_.withoutがある

→ without

```_.pull()


// 

```
　



##pullAt

**位置削除**　　`　破壊的メソッド　`

```
_.pullAt(array, [indexes]);
```

配列から[indexes]に指定された位置の要素を選抜した配列を返すとともに、引用元の配列の指定された位置の要素を削除する

配列に存在しない[indexes]を指定した場合undefinedを含んだ配列を返す

すべて削除された場合は空の配列を返す

このメソッドは引用元の値を破壊する

```_.pullAt()


// 

```
　



##remove

**条件削除**　　`　破壊的メソッド　`

```
_.remove(array, [predicate=_.identity], [thisArg]);
```

配列から第2引数の条件に合致する要素を選抜した配列を返すとともに、引用元の配列の指定された条件の要素を削除する

配列に存在しない条件を指定した場合は空の配列を返す

すべて削除された場合は空の配列を返す

このメソッドは引用元の値を破壊する

```_.remove()


// 

```
　



##rest

**先頭削除**

```
_.rest(array);
```

配列から第1要素を取り除いた残りの配列を返す

要素数が1つ以下の配列では空の配列を返す

↔ initial

```_.rest()


// 

```
　



##slice

**部分選択**

```
_.slice(array, [start=0], [end=array.length]);
```

配列から第2引数と第3引数の間の要素を抜き出した配列を返す

[start]の初期値は「0」で、[end]の初期値は配列の要素数である

[start]、[end]に負数が設定された場合、配列の最後尾を起点とする位置が設定される

```_.slice()


// 

```
　



##sortedIndex

**ソート済配列検索**

```
_.sortedIndex(array, value, [iteratee=_.identity], [thisArg]);
```

ソート済みの配列において、valueに指定された値が挿入されるべき位置のindexを返す

valueと値が一致し、かつ複数存在する場合はそのうち最も小さいindexを返す

このメソッドは参照元の配列がソートされているか否かを判別せず、非ソート配列を参照しても値を返す

```_.sortedIndex()


// 

```
　



##sortedLastIndex

**ソート済配列後方検索**

```
_.sortedLastIndex(array, value, [iteratee=_.identity], [thisArg]);
```

ソート済みの配列において、valueに指定された値が挿入されるべき位置を配列の最後尾から検索したindexを返す

valueと値が一致し、かつ複数存在する場合はそのうち最も大きいindexを返す

このメソッドは参照元の配列がソートされているか否かを判別せず、非ソート配列を参照しても値を返す

```_.sortedLastIndex()


// 

```
　



##take

**先頭部分選択**

```
_.take(array, [n=1]);
```

配列の最初から第2引数で指定したインデックスまでの部分を抜き出した配列を返す

第2引数に0以下の値が指定された場合は空の配列を返す

_.slice(array, 0, [end=n])と同じ結果を返す

```_.take()


// 

```
　



##takeRight

**後方部分選択**

```
_.takeRight(array, [n=1]);
```

配列の第2引数で指定したインデックスから最後尾までの部分を抜き出した配列を返す

第2引数に0以下の値が指定された場合は空の配列を返す

_.slice(array, [start=n])と同じ結果を返す

```_.takeRight()


// 

```
　



##takeWhile

**先頭条件選択**

```
_.takeWhile(array, [predicate=_.identity], [thisArg]);
```

配列の最初から第2引数で指定した条件に合致する値までの部分を抜き出した配列を返す

第2引数の条件に合致する値が存在しない場合は空の配列を返す

```_.takeWhile()


// 

```
　



##takeRightWhile

**後方条件選択**

```
_.takeRightWhile(array, [predicate=_.identity], [thisArg]);
```

配列の最後尾から第2引数で指定した条件に合致する値までの部分を抜き出した配列を返す

第2引数の条件に合致する値が存在しない場合は空の配列を返す

```_.takeRightWhile()


// 

```
　



##union

**非重複選択**

```
_.union([arrays]);
```

複数の配列のすべての要素を重複なく格納した配列を返す

→ intersection、xor

```_.union()


// 

```
　



##uniq

**一意選択**

```
_.uniq(array, [isSorted], [iteratee], [thisArg]);
```

配列からユニークな値だけを抜き出した配列を返す

第2引数には、参照する配列がソートされていればtrueを、されていなければfalseを指定する

第3引数に指定した条件をもとにユニーク判定を行うこともできる

```_.uniq()


// 

```
　



##zip

**配列結合**

```
_.zip([arrays]);
```

複数の配列から各配列の第n要素を抜き出してグループ化した配列を返す

↔ unzip

→ zipObject

```_.zip()


// 

```
　



##unzip

**解凍する**

```
_.unzip(array);
```

zipメソッドの逆処理によって生成した複数配列を要素にもつ1つの配列を返す

↔ zip

→ zipObject

```_.unzip()


// 

```
　



##zipObject

**配列オブジェクト化**

```
_.zipObject(props, [values=[]]);
```

複数の配列から各配列の第n要素を抜き出してグループ化したオブジェクトを返す

→ zip、unzip

```_.zipObject()


// 

```
　



##without

**非破壊的値削除**

```
_.without(array, [values]);
```

配列から[values]に指定した値を取り除いた配列を返す

すべて削除された場合は空の配列を返す

_.withoutは_.pullと異なり参照した配列を破壊しない

→ pull

```_.without()


// 

```
　



##xor

**排他的論理和**

```
_.xor([arrays]);
```

複数の配列から1つの配列のみに属する値を抜き出した配列を返す

↔ intersection
→ union

```_.xor()


// 

```
　







　
　
　
　
　
　
　
　
　
　
　
　
　
