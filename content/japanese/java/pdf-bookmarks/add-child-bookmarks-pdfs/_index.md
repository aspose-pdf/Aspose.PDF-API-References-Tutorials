---
title: PDF に子ブックマークを追加する
linktitle: PDF に子ブックマークを追加する
second_title: Aspose.PDF Java PDF 処理 API
description: Aspose.PDF for Java を使用して、子ブックマークを使用して PDF ドキュメントを強化する方法を学びます。ナビゲーションと構成を改善するためのコード例を含むステップバイステップのガイド。
type: docs
weight: 11
url: /ja/java/pdf-bookmarks/add-child-bookmarks-pdfs/
---

## PDF への子ブックマークの追加の概要

この記事では、Aspose.PDF for Java を使用して PDF ドキュメントに子ブックマークを追加する方法を説明します。子ブックマークは、PDF ドキュメントのコンテンツを整理して移動するための便利な方法であり、ユーザーがドキュメント内の特定のセクションやトピックを見つけやすくなります。

## 前提条件

実装に入る前に、次の前提条件が満たされていることを確認してください。

- Java 開発環境がシステムにインストールされていること。
-  Java ライブラリ用の Aspose.PDF。からダウンロードできます[ここ](https://releases.aspose.com/pdf/java/).

## 環境のセットアップ

1. 提供されたリンクから Aspose.PDF for Java ライブラリをダウンロードします。
2. ライブラリを Java プロジェクトに追加します。

それでは、新しい PDF ドキュメントを作成し、それに子ブックマークを段階的に追加することから始めましょう。

## 新しい PDF ドキュメントの作成

まず、PDF ドキュメントを初期化し、それにページを追加する必要があります。開始するためのコード スニペットは次のとおりです。

```java
// PDFドキュメントを初期化する
Document pdfDocument = new Document();

//PDF にページを追加する
pdfDocument.getPages().add();
pdfDocument.getPages().add();
```

この例では、新しい PDF ドキュメントを作成し、それに 2 ページを追加しました。

## 親ブックマークの追加

親ブックマークは、PDF ドキュメントの主要なセクションまたはカテゴリとして機能します。いくつかの親ブックマークを作成してみましょう。

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

「親ブックマーク 1」と「親ブックマーク 2」という 2 つの親ブックマークを追加しました。

## 子ブックマークの追加

次に、前に作成した親ブックマークに子ブックマークを追加します。子ブックマークは、各親ブックマーク内の特定のトピックまたはサブセクションを表します。その方法は次のとおりです。

```java
//子ブックマークを親ブックマーク 1 に追加する
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//子ブックマークを親ブックマーク 2 に追加する
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);
```

「親ブックマーク 1」と「親ブックマーク 2」の両方に子ブックマークを追加しました。

## ブックマークの外観のカスタマイズ

ブックマークのテキストとスタイルを変更することで、ブックマークの外観をカスタマイズできます。さらに、視覚的にわかりやすくするためにブックマークにアイコンを追加できます。その方法の例を次に示します。

```java
//ブックマークの外観をカスタマイズする
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());
```

この例では、親ブックマークを斜体にし、子ブックマークのテキストの色を緑色に変更し、斜体のアイコンを子ブックマークに追加しました。

## イベントの処理

ブックマークにはアクションを関連付けることもできます。たとえば、ユーザーがブックマークをクリックしたときにトリガーされるアクションを追加できます。ブックマークのクリック イベントを処理する方法は次のとおりです。

```java
//アクションをブックマークに追加する
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);
```

このコードでは、クリックすると PDF の 2 ページ目に移動する「GoTo」アクションを子ブックマークに追加しました。

## PDFを保存する

必要なブックマークをすべて追加し、その外観とアクションをカスタマイズしたら、変更した PDF ドキュメントを保存できます。

```java
// PDF ドキュメントを保存する
pdfDocument.save("output.pdf");
```

これで、子ブックマークを含む PDF ドキュメントの準備が整いました。

## 完全なソースコード

Aspose.PDF for Java を使用して PDF ドキュメントに子ブックマークを追加するための完全なソース コードを次に示します。

```java
// PDFドキュメントを初期化する
Document pdfDocument = new Document();

//PDF にページを追加する
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

//子ブックマークを親ブックマーク 1 に追加する
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//子ブックマークを親ブックマーク 2 に追加する
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);

//ブックマークの外観をカスタマイズする
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());

//アクションをブックマークに追加する
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);

// PDF ドキュメントを保存する
pdfDocument.save("output.pdf");
```

## 結論

Aspose.PDF for Java を使用して PDF に子ブックマークを追加することは、ドキュメントのナビゲーションと整理を強化する強力な機能です。この記事で説明する手順に従うことで、親子ブックマークを含む適切に構造化された PDF を作成したり、外観をカスタマイズしたり、ユーザー エクスペリエンスを向上させるアクションを追加したりすることができます。

## よくある質問

### Java 用の Aspose.PDF をダウンロードするにはどうすればよいですか?

 Java 用 Aspose.PDF は Web サイトからダウンロードできます。[ここ](https://releases.aspose.com/pdf/java/).

### 子ブックマークはすべての PDF ビューアでサポートされていますか?

はい、子ブックマークはほとんどの最新の PDF ビューアでサポートされており、PDF ドキュメント内を移動するための強化されたユーザー エクスペリエンスを提供します。

### ブックマークの外観をさらにカスタマイズできますか?

はい、文書のデザインに合わせてテキスト スタイル、色、アイコンを調整することで、ブックマークの外観をカスタマイズできます。

### 他にどのようなアクションをブックマークに追加できますか?

「GoTo」アクションのほかに、Web リンクを開く「URI」アクションや、ブックマークがクリックされたときにカスタム スクリプトを実行する「JavaScript」アクションなどのアクションを追加できます。

### Aspose.PDF for Java は商用プロジェクトに適していますか?

はい、Aspose.PDF for Java は個人プロジェクトと商業プロジェクトの両方に適しており、PDF の操作と生成のための幅広い機能を提供します。