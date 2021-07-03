#### Google timeline.alfredworkflowのメモ
[トップページに戻る](https://kitanotamotsu.github.io/tripadvisor)


#### 開発メモ：

1.検索結果のURLを解析する

　URLのオプションとしてキーワードと=で指定されている場合がありますが、Featuresのweb searchのカスタマイズで簡単に設定できます。今回は選択したテキストからの検索なのでワークフローを利用しています。

　さて、トリップアドバイザーで検索すると以下のオプションがあるようです。
　Search?q=
　&searchSessionId=
　&sid=
　&blockRedirect=　

　Search?q=の後に検索文字列を日本語で指定していますので、ここを適当に置き換えればOKそうです。
　アドレスバーのURLを直接変えてテストしてみましょう。他のオプションは一旦無視（削除）します。URLを作ったらenter。うまく表示されるようですね。



2.選択した文字列で検索させる

　ワークフローの起点はいくつかありますが、今回はHOTKEYを利用します。
　HOTKEYの設定タブにArgumentという項目がありSelection in macOSを選択します。
　後続のアクションはOpenURLとして、URLに下記の記述をします。

　`https://www.tripadvisor.jp/Search?q={query}`

　実行時に{query}が、選択した文字列に置き換わってURLにアクセスします。
　なおHOTKEYのArgumentは、選択アイテム以外に、クリップボード、ペイストボード、固定テキスト、引数なしが指定可能


<br><br><br><br><br>
#### 機能：

  選択した文字列で、トリップアドバイザーを検索する

  
<br><br><br><br><br>
#### インストール：

  1.[alfredworkflow](https://https://github.com/KitanoTamotsu/tripadvisor/releases/download/1.0/TripAdvisor.alfredworkflow.zip)をダウンロード

  2.ファイルをダブルクリックしてワークフローに登録


<br><br><br><br><br>
#### 使い方：

　Macで文字列を選択してHOTKEY起動(HOTKEYは自分で設定が必要です)


<br><br><br><br><br>
#### 背景：

　トリップアドバイザーはよく利用するサイトですが、サイトでは検索する際の漢字変換がうまく作動しません。
　かなりもどかしく、このツールを思いつきました。
　実際に検索のURLを見てみると日本語がそのまま表示されていたので、
　単にワークフローでブラウザにつなげたらできちゃいました。
　アルフっておそるべし。

