---
title: PDFに子ブックマークを追加する
linktitle: PDFに子ブックマークを追加する
second_title: Aspose.PDF Java PDF 処理 API
description: Aspose.PDF for Java を使用して子ブックマークで PDF ドキュメントを強化する方法を学びます。ナビゲーションと整理を改善するためのコード例を含むステップバイステップ ガイドです。
type: docs
weight: 11
url: /ja/java/pdf-bookmarks/add-child-bookmarks-pdfs/
---

## PDF に子ブックマークを追加する方法の紹介

この記事では、Aspose.PDF for Java を使用して PDF ドキュメントに子ブックマークを追加する方法について説明します。子ブックマークは、PDF ドキュメントのコンテンツを整理してナビゲートするのに便利な方法であり、ユーザーがドキュメント内の特定のセクションやトピックを見つけやすくなります。

## 前提条件

実装に進む前に、次の前提条件が満たされていることを確認してください。

- システムに Java 開発環境がインストールされています。
-  Aspose.PDF for Javaライブラリ。ここからダウンロードできます。[ここ](https://releases.aspose.com/pdf/java/).

## 環境の設定

1. 提供されたリンクから Aspose.PDF for Java ライブラリをダウンロードします。
2. ライブラリを Java プロジェクトに追加します。

それでは、まず新しい PDF ドキュメントを作成し、それに子ブックマークを段階的に追加してみましょう。

## 新しいPDFドキュメントの作成

まず、PDF ドキュメントを初期化し、ページを追加する必要があります。開始するためのコード スニペットは次のとおりです。

```java
// PDF文書を初期化する
Document pdfDocument = new Document();

//PDFにページを追加する
pdfDocument.getPages().add();
pdfDocument.getPages().add();
```

この例では、新しい PDF ドキュメントを作成し、それに 2 ページを追加しました。

## 親ブックマークの追加

親ブックマークは、PDF ドキュメントの主要なセクションまたはカテゴリとして機能します。親ブックマークをいくつか作成してみましょう。

```java
//親ブックマークを作成する
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);
```

「親ブックマーク 1」と「親ブックマーク 2」の 2 つの親ブックマークを追加しました。

## 子ブックマークの追加

ここで、先ほど作成した親ブックマークに子ブックマークを追加します。子ブックマークは、各親ブックマーク内の特定のトピックまたはサブセクションを表します。手順は次のとおりです。

```java
//親ブックマーク 1 に子ブックマークを追加する
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//親ブックマーク 2 に子ブックマークを追加する
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);
```

「親ブックマーク 1」と「親ブックマーク 2」の両方に子ブックマークを追加しました。

## ブックマークの外観をカスタマイズする

ブックマークのテキストとスタイルを変更することで、ブックマークの外観をカスタマイズできます。さらに、ブックマークにアイコンを追加して、視覚的にわかりやすくすることもできます。以下にその方法の例を示します。

```java
//ブックマークの外観をカスタマイズする
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());
```

この例では、親ブックマークを斜体にし、子ブックマークのテキストの色を緑に変更し、子ブックマークに斜体アイコンを追加しました。

## イベントの処理

ブックマークには、アクションを関連付けることもできます。たとえば、ユーザーがブックマークをクリックしたときにトリガーされるアクションを追加できます。ブックマークのクリック イベントを処理する方法は次のとおりです。

```java
//ブックマークにアクションを追加する
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);
```

このコードでは、子ブックマークに「GoTo」アクションを追加しました。このアクションをクリックすると、ユーザーは PDF の 2 ページ目に移動するようになります。

## PDFを保存する

必要なブックマークをすべて追加し、その外観とアクションをカスタマイズしたら、変更した PDF ドキュメントを保存できます。

```java
// PDF文書を保存する
pdfDocument.save("output.pdf");
```

子ブックマークを含む PDF ドキュメントが準備できました。

## 完全なソースコード

Aspose.PDF for Java を使用して PDF ドキュメントに子ブックマークを追加するための完全なソース コードは次のとおりです。

```java
// PDF文書を初期化する
Document pdfDocument = new Document();

//PDFにページを追加する
pdfDocument.getPages().add();
pdfDocument.getPages().add();

//親ブックマークを作成する
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);

//親ブックマーク 1 に子ブックマークを追加する
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//親ブックマーク 2 に子ブックマークを追加する
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);

//ブックマークの外観をカスタマイズする
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());

//ブックマークにアクションを追加する
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);

// PDF文書を保存する
pdfDocument.save("output.pdf");
```

## 結論

Aspose.PDF for Java を使用して PDF に子ブックマークを追加すると、ドキュメントのナビゲーションと整理が強化される強力な機能になります。この記事で説明する手順に従うことで、親ブックマークと子ブックマークを使用して適切に構造化された PDF を作成し、外観をカスタマイズし、さらにユーザー エクスペリエンスを強化するアクションを追加することもできます。

## よくある質問

### Aspose.PDF for Java をダウンロードするにはどうすればいいですか?

 Aspose.PDF for Javaはウェブサイトからダウンロードできます。[ここ](https://releases.aspose.com/pdf/java/).

### 子ブックマークはすべての PDF ビューアーでサポートされていますか?

はい、子ブックマークはほとんどの最新の PDF ビューアーでサポートされており、PDF ドキュメント内を移動する際、ユーザー エクスペリエンスが向上します。

### ブックマークの外観をさらにカスタマイズできますか?

はい、ドキュメントのデザインに合わせてテキストのスタイル、色、アイコンを調整することで、ブックマークの外観をカスタマイズできます。

### ブックマークに追加できる他のアクションは何ですか?

「GoTo」アクションの他に、Web リンクを開く「URI」アクションや、ブックマークがクリックされたときにカスタム スクリプトを実行する「JavaScript」アクションなどのアクションを追加できます。

### Aspose.PDF for Java は商用プロジェクトに適していますか?

はい、Aspose.PDF for Java は個人プロジェクトと商用プロジェクトの両方に適しており、PDF の操作と生成のための幅広い機能を提供します。