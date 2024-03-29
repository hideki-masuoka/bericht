# Kateのmdにtocする。その時、あなたは...

## こんにちは、有益情報です。

これは世界中で多くの人々に愛されるテキストエディタ、Kateについて書かれた文書です。

[Kate - Get an Edge in Editing](https://kate-editor.org/ja/)

今回はなんとKateでMarkdownファイルを編集するときに、編集中のファイルの目次(TOC: table of contents)を表示させたいとおもいます。

さっそく設定タブのプラグインマネージャで Symbol Viewer プラグインを有効にしましょう！

![プラグイン設定](https://github.com/hideki-masuoka/bericht/raw/main/assets/d20230402-kate-md-toc/Screenshot_20230402_170237.png)

すると、こうです。

Symbol Viewerプラグイン **「Sorry, not supported yet!」**

![NOT SUPPORTED YET](https://github.com/hideki-masuoka/bericht/raw/main/assets/d20230402-kate-md-toc/Screenshot_20230402_170021.png)

## その時、あなたは...

世の中には2種類の人間が居ると言われており、それはmakeする人とmakeしない人であるとされています。

### makeしてもいいよ

makeしてもいい方、こちらのプラグインをmakeしてみてはいかがでしょうか？

**KatePlugin-IndexView**

[loh-tar/KatePlugin-IndexView: A fork from Kate's plugin SymbolViewer with a couple of improvements](https://github.com/loh-tar/KatePlugin-IndexView)

これを、なんやかんやしてmakeしてインストールすると、プラグインマネージャに Index View プラグインの項目が追加されます。

![Index Viewが追加された様子](https://github.com/hideki-masuoka/bericht/raw/main/assets/d20230402-kate-md-toc/Screenshot_20230402_170342.png)

こうして有効にされたIndex Viewは、ツールビューのサイドバーに追加されIndex欄にTOCがドーーーン！！となります。

![目次が表示されている様子](https://github.com/hideki-masuoka/bericht/raw/main/assets/d20230402-kate-md-toc/Screenshot_20230402_165938.png)

どうぞお試し下さい。

### makeしないよ

makeしない方、こちらのLSP(language-server-protocol)をインストールしてみてはいかがでしょうか？

**marksman**

[artempyanykh/marksman: Write Markdown with code assist and intelligence in the comfort of your favourite editor.](https://github.com/artempyanykh/marksman)

これをHow to installしてインストールします。

無事インストールできたら、Kateの設定タブのLSP ClientのUser Server Settingsに、次の怪しいJSONコードを入力します。


```json
{
  "servers": {
    "markdown": {
      "command": ["marksman", "server"],
      "highlightingModeRegex": "^Markdown$"
    }
  }
}
```

![設定値入力例](https://github.com/hideki-masuoka/bericht/raw/main/assets/d20230402-kate-md-toc/Screenshot_20230402_170533.png)

そして、SaveしてKateを再起動してMarkdownファイルを開いたら、ほれどうじゃ！

![NOT SUPPORTED YET](https://github.com/hideki-masuoka/bericht/raw/main/assets/d20230402-kate-md-toc/Screenshot_20230402_170021.png)

普通LSPを経由してSymbol Viewerに表示されるとおもうじゃないですか？
でもよく見たら、Symbol Outlineの方に表示されていたので良かったです。

![Symbol Outline に目次が表示されている様子](https://github.com/hideki-masuoka/bericht/raw/main/assets/d20230402-kate-md-toc/Screenshot_20230402_171906.png)

あとはなんかファイル名の横にも目次が表示される機能も追加されます。

![ファイル名の横に目次が表示されている様子](https://github.com/hideki-masuoka/bericht/raw/main/assets/d20230402-kate-md-toc/Screenshot_20230402_171323.png)

## 終わりに

Atom〜　帰ってきてくれ〜

