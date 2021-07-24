## 　　Lesson3.　選択中のテキストを{query}にする
#### 開発メモ
ワークフロー
<br><img width="600" alt="lesson3" src="https://user-images.githubusercontent.com/40127279/126853884-380f4324-51d5-4dc3-908d-4c647407b38c.png">

### 1.検索結果のURLを解析する
　URLのオプションとしてキーワードと=で指定されている場合がありますが、
<br>　基本的にFeaturesのweb searchのカスタマイズで簡単に設定できます
<br>　今回は選択したテキストからの検索なのでワークフローを利用しています
<br>　さて、トリップアドバイザーで検索すると以下のオプションがあるようです
<br>　　Search?q=
<br>　　&searchSessionId=
<br>　　&sid=
<br>　　&blockRedirect=　
<br>
<br>　Search?q=の後に検索文字列を日本語で指定していますので
<br>　ここを適当に置き換えればOKそうです
<br>　アドレスバーのURLを直接変えてテストしてみましょう
<br>　他のオプションは一旦無視（削除）します
<br>　URLを作ったらenter。うまく表示されるようですね
### 2.選択した文字列で検索させる
　ワークフローの起点はいくつかありますが、今回はHOTKEYを利用します。
<br>　HOTKEYの設定タブにArgumentという項目がありSelection in macOSを選択します
<br>　実はこの設定だけで選択中の文字列をAlfredに受け渡すことができます
<br>　あとは、後続アクションのOpenURLで、URLに下記の記述をすればOKです
<br>
<br>　`https://www.tripadvisor.jp/Search?q={query}`
<br>
<br>　実行時に{query}が、選択した文字列に置き換わってURLにアクセスします
<br>　なおHOTKEYのArgumentは、選択アイテム以外に、クリップボード、ペイストボード、
<br>　固定テキスト、引数なしが指定可能
<br>
<br>　OpenURL
<br>　<img width="600" alt="OpenURL" src="https://user-images.githubusercontent.com/40127279/126853922-007a54a0-3627-4492-a7a5-c978643f7714.png">
<br>
<br>　おまけとして、選択したテキストをクリップボードに格納しておきました
<br>　ワークフローを二股にして並行処理とすることができます
<br>　CopyToClipboard
<br>　<img width="600" alt="clipbaord" src="https://user-images.githubusercontent.com/40127279/126853973-5478e756-1a0e-4c3c-882c-8e70cffaf047.png">


#### 背景
　トリップアドバイザーはサイトでの検索は漢字変換がうまく作動しません。
<br>　かなりもどかしく、このツールを思いつきました
<br>　実際に検索のURLを見てみると日本語がそのまま表示されていたので、
<br>　単にワークフローでブラウザにつなげたらできちゃいましたという感じ
<br>　アルフっておそるべし。
#### 取扱説明
### 機能:
　トリップアドバイザーを検索する
### インストール:
　1.[alfredworkflow](https://github.com/KitanoTamotsu/tripadvisor/releases/download/1.0/TripAdvisor.alfredworkflow.zip)をダウンロード 
<br>　2.ファイルをダブルクリックしてワークフローに登録
### 使い方:
　Macで文字列を選択してHOTKEY起動(HOTKEYはご自身での設定が必要です)
<br>
<br>
[トップページに戻る](https://kitanotamotsu.github.io/)

