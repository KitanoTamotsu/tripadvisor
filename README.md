## 　　Lesson3.　選択中のテキストを{query}にする
#### 開発メモ
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
<br>　後続のアクションはOpenURLとして、URLに下記の記述をします
<br>
<br>　`https://www.tripadvisor.jp/Search?q={query}`
<br>
<br>　実行時に{query}が、選択した文字列に置き換わってURLにアクセスします
<br>　なおHOTKEYのArgumentは、選択アイテム以外に、クリップボード、ペイストボード、
<br>　固定テキスト、引数なしが指定可能
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

