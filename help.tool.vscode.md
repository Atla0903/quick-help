#<span id='top'> Visual Studio Code に関するメモ</span>

## 目次
* [ワークスペースとは](#jump1)
* [設定ファイルでエンコード指定（settings.json）](#jump2)

***
## <a id='jump1' href='top'>ワークスペースとは</a>

2019/06/28 21:20

### 概要
ワークスペースは、複数ルートのフォルダーを同時に開く機能です。イメージとしては、Visual Studioのソリューション内で複数のプロジェクトを開けるのと同じです。アプリケーションを複数のルートフォルダーに分割していたり、テストを別ルートフォルダーに分けていたりした方には便利だと思います。もちろんルートフォルダーは、それぞれ異なるパスに配置してあっても問題ありません。

> 自分用メモとか共通ライブラリ出しとくと便利そう

### 参考
* [VS Codeのワークスペース](https://qiita.com/YuichiNukiyama/items/ef16a0219f46ea03a045)

***
## <a id='jump2' href='#top'>設定ファイルでエンコード指定（settings.json）</a>

2019/07/01 23:23

### 概要
VisualStudioCodeであるフォルダ以下のファイルを全てShift-JISで開きたい

Visual Studio Code は ワークスペースって概念があって、そのワークスペース毎に設定を記述できる。 （概念って書いてるけど、単にフォルダ毎に設定書けるってはなし）

`.vscode\settings.json`に`"files.encoding": "shiftjis"`

### その他
"files.autoGuessEncoding": true　を設定して、自動エンコーディングを設定してたけど、思うようなエンコーディングにならない場合もあるので、上記設定にすると確実に変更可能。公式もそのように案内している。


[参考サイト](http://k6i.hateblo.jp/entry/2017/07/24/194033)

***