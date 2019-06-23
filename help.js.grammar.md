# JavaScript 文法に関するメモ

## 目次
* ’use strict’ 宣言  
* プロトタイプ(prototype)の使い方
* var ,let ,const 違い

***
## ’use strict’ 宣言 

2019/06/23  7:09

### 概要
JavaScript(以下、JS）内でuse strictを宣言すると、コードがstrict（厳格）モードで実行されるようになる。  
strictモードでは、より的確なエラーチェックが行われる。  
これまでエラーにならなかったような曖昧な実装がエラー扱いになります。

何が厳格になったの？  
1. withの使用の禁止
2. eval内で宣言された変数のスコープ
3. 単純名の削除の禁止
4. いくつかの識別子を予約語に
5. arguments の単純化
6. セキュアな JavaScript 作成の容易化
7. 8進数表記の禁止 etc..

### 書き方
>'use strict';

### 参考
[Qiita 【JavasScript】use strictとは](https://qiita.com/miri4ech/items/ffcebaf593f5baa1c112)


***  

## プロトタイプ(prototype)の使い方

2019/06/23  7:30

### 概要
「継承」を実現する仕組み。JSではすべてのオブジェクトは「プロトタイプ」をベースとしている。  

### 「prototype」の使い方
クラスと分けて書く。  
アンチパターンとして、クラスに内包すると
同様の内容を持つことになって、メモリの無駄になる。

```
// プロパティ
var User = function(name, age) {
    this.name = name;
    this.age = age;
} 

// メソッド
User.prototype = {
    getName: function() {
        return this.name;
    },
 
    getAge: function() {
        return this.age;
    }
}
```

### 「prototype」による継承
「継承」の仕組みで重要なのが「プロトタイプチェーン」です。
>「プロトタイプチェーン」の仕組み  

各オブジェクトが持っている「プロトタイプ」をチェーンのように連結してお互いを参照できる仕組みになります。

>書き方

各プロトタイプには連結させたいオブジェクトのインスタンスを代入することで継承できる。

```
var User = function() {};
var Member = function() {};
 
User.prototype.hello = function() {
    return 'こんにちは！';
}
 
Member.prototype = new User();
 
var taro = new User();
var hanako = new Member();
 
console.log( taro.hello() );
console.log( hanako.hello() );
```

****

## var ,let ,const 違い

2019/06/23 11:47

### まとめ

var は 関数スコープ `function(){}`

let は ブロックスコープ `{}`

const は 再代入不可(定数)

巻き上げは起こるらしい。（内部的に最初に実行されるやつ）

結論は、const 使って、変更が必要なやつは、letを使う

***