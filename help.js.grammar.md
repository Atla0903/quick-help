# JavaScript 文法に関するメモ

## ’use strict’ 宣言


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

### 参考
[Qiita 【JavasScript】use strictとは](https://qiita.com/miri4ech/items/ffcebaf593f5baa1c112)


2019/06/23  7:09
***  


