---
title: PDF ファイルにブックマークを追加
linktitle: PDF ファイルにブックマークを追加
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用すると、PDF ファイルにブックマークを簡単に追加してナビゲーションを改善できます。
type: docs
weight: 10
url: /ja/net/programming-with-bookmarks/add-bookmark/
---
PDF ファイルにブックマークを追加すると、簡単かつ迅速なナビゲーションが可能になります。 Aspose.PDF for .NET を使用すると、次のソース コードに従って PDF ファイルにブックマークを簡単に追加できます。

## ステップ 1: 必要なライブラリをインポートする

始める前に、C# プロジェクトに必要なライブラリをインポートする必要があります。必要なインポートディレクティブは次のとおりです。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## ステップ 2: ドキュメントフォルダーへのパスを設定する

この手順では、ブックマークを追加する PDF ファイルが含まれるフォルダーへのパスを指定する必要があります。交換する`"YOUR DOCUMENT DIRECTORY"`次のコードでは、ドキュメント フォルダーへの実際のパスを指定します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 3: PDF ドキュメントを開く

次に、次のコードを使用して、ブックマークを追加する PDF ドキュメントを開きます。

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

## ステップ 4: ブックマーク オブジェクトを作成する

このステップでは、次を使用してブックマーク オブジェクトを作成します。`OutlineItemCollection`クラスを作成し、タイトル、斜体属性、太字属性、クリック時に実行するアクションなどのプロパティを設定します。対応するコードは次のとおりです。

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

## ステップ 5: ドキュメントにブックマークを追加する

最後に、作成したブックマークをドキュメントのブックマーク コレクションに追加します。`Add`の方法`Outlines`財産。対応するコードは次のとおりです。

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Aspose.PDF for .NET を使用したブックマークの追加のサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開いた文書
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
//ブックマークオブジェクトを作成する
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
//移動先のページ番号を設定します
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
//ドキュメントのアウトライン コレクションにブックマークを追加します。
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddBookmark_out.pdf";
//出力の保存
pdfDocument.Save(dataDir);
Console.WriteLine("\nBookmark added successfully.\nFile saved at " + dataDir);
```

## 結論

おめでとうございます！これで、Aspose.PDF for .NET を使用してブックマークを追加するためのステップバイステップのガイドが完成しました。このコードを使用すると、カスタム ブックマークを追加して PDF ドキュメント内のナビゲーションを改善できます。

高度なブックマーク操作機能の詳細については、公式の Aspose.PDF ドキュメントを必ずご確認ください。


### PDF ファイルへのブックマークの追加に関する FAQ

#### Q: PDF ファイルのブックマークとは何ですか?

A: ブックマークはアウトラインとも呼ばれ、PDF ドキュメント内でナビゲーションと構造を提供するインタラクティブな要素です。これにより、ユーザーは特定のセクションやページにすばやくジャンプできます。

#### Q: PDF ファイルにブックマークを追加する必要があるのはなぜですか?

A: PDF ファイルにブックマークを追加すると、ユーザー エクスペリエンスが向上し、読者がドキュメントのコンテンツ内を簡単に移動できるようになります。ブックマークは目次として機能したり、重要なセクションにすばやくアクセスしたりできます。

#### Q: C# プロジェクトに必要なライブラリをインポートするにはどうすればよいですか?

A: C# プロジェクトに必要なライブラリをインポートするには、次のインポート ディレクティブを含めます。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

これらのディレクティブを使用すると、PDF ドキュメントとブックマークを操作するために必要なクラスとメソッドにアクセスできます。

#### Q: ドキュメントフォルダーへのパスを指定するにはどうすればよいですか?

答え: 交換してください`"YOUR DOCUMENT DIRECTORY"`提供されたソース コード内で、ブックマークを追加する PDF ファイルを含むフォルダーへの実際のパスを指定します。

#### Q: PDF ドキュメントを開いてブックマークを追加するにはどうすればよいですか?

A: PDF ドキュメントを開いてブックマークを追加するには、次のコードを使用します。

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

交換する`"AddBookmark.pdf"`実際のファイル名を付けます。

#### Q: ブックマーク オブジェクトを作成するにはどうすればよいですか?

 A: ブックマーク オブジェクトを作成するには、`OutlineItemCollection`クラス。タイトル、斜体スタイル、太字スタイル、クリック時に実行するアクションなどのプロパティをカスタマイズします。

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

####  Q：その目的は何ですか？`Action` property in a bookmark?

 A:`Action`プロパティは、ブックマークをクリックしたときに実行されるアクションを指定します。この例では、`GoToAction`特定のページ (この場合はページ 2) に移動するクラス。

#### Q: ドキュメントにブックマークを追加するにはどうすればよいですか?

 A: を使用してください。`Add`の方法`Outlines`プロパティを使用して、作成したブックマークをドキュメントのブックマーク コレクションに追加します。

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

#### Q: この方法を使用して複数のブックマークを追加できますか?

A: はい、手順 4 ～ 8 を繰り返して、ドキュメントに複数のブックマークを追加できます。必要に応じて、各ブックマークのプロパティとアクションをカスタマイズします。

#### Q: 更新された PDF ファイルを保存するにはどうすればよいですか?

 A: 更新された PDF ファイルを保存するには、`Save`の方法`pdfDocument`物体：

```csharp
dataDir = dataDir + "AddBookmark_out.pdf";
pdfDocument.Save(dataDir);
```

#### Q: ブックマークが追加されたことを確認するにはどうすればよいですか?

A: 生成された PDF ファイルを開いて、指定したブックマークがドキュメントに追加されていることを確認します。

#### Q: 追加できるブックマークの数に制限はありますか?

A: 通常、追加できるブックマークの数に厳密な制限はありませんが、最適なパフォーマンスを得るにはドキュメントのサイズと複雑さを考慮してください。

#### Q: ブックマークの外観をカスタマイズできますか?

A: はい、Aspose.PDF 機能を使用して、ブックマークの外観、色、スタイル、その他の属性をさらにカスタマイズできます。