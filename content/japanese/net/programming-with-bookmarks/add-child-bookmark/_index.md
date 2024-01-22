---
title: PDF ファイルに子のブックマークを追加
linktitle: PDF ファイルに子のブックマークを追加
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用すると、PDF ファイルに子ブックマークを簡単に追加して、より整理された閲覧が可能になります。
type: docs
weight: 20
url: /ja/net/programming-with-bookmarks/add-child-bookmark/
---
PDF ファイルに子ブックマークを追加すると、より構造化された編成とナビゲーションが可能になります。 Aspose.PDF for .NET を使用すると、次のソース コードに従ってサブブックマークを簡単に追加できます。

## ステップ 1: 必要なライブラリをインポートする

始める前に、C# プロジェクトに必要なライブラリをインポートする必要があります。必要なインポートディレクティブは次のとおりです。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## ステップ 2: ドキュメントフォルダーへのパスを設定する

このステップでは、サブブックマークを追加する PDF ファイルが含まれるフォルダーへのパスを指定する必要があります。交換する`"YOUR DOCUMENT DIRECTORY"`次のコードでは、ドキュメント フォルダーへの実際のパスを指定します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 3: PDF ドキュメントを開く

次に、次のコードを使用して、サブブックマークを追加する PDF ドキュメントを開きます。

```csharp
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
```

## ステップ 4: 親ブックマーク オブジェクトを作成する

このステップでは、`OutlineItemCollection`クラスを作成し、タイトル、斜体属性、太字属性などのプロパティを設定します。対応するコードは次のとおりです。

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent bookmark";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
```

## ステップ 5: 子ブックマーク オブジェクトを作成する

このステップでは、次のコマンドを使用してサブブックマーク オブジェクトを再度作成します。`OutlineItemCollection`クラスを作成し、そのプロパティを設定します。対応するコードは次のとおりです。

```csharp
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Sub Bookmark";
pdfChildOutline. Italic = true;
pdfChildOutline. Bold = true;
```

## ステップ 6: 親ブックマークにサブブックマークを追加する

最後に、作成したサブブックマークを親ブックマークのサブブックマーク コレクションに追加します。`Add`親オブジェクトのメソッド。対応するコードは次のとおりです。

```csharp
pdfOutline.Add(pdfChildOutline);
```

## ステップ 7: 親ブックマークをドキュメントのブックマーク コレクションに追加する

最後に、親ブックマークをドキュメントのブックマーク コレクションに追加します。`Add`の方法`Outlines`財産。対応するコードは次のとおりです。

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Aspose.PDF for .NET を使用した子ブックマークの追加のサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開いた文書
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
//親ブックマークオブジェクトを作成する
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;      
//子ブックマークオブジェクトを作成する
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Child Outline";
pdfChildOutline.Italic = true;
pdfChildOutline.Bold = true;
//親ブックマークのコレクションに子ブックマークを追加する
pdfOutline.Add(pdfChildOutline);
//ドキュメントのアウトライン コレクションに親ブックマークを追加します。
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddChildBookmark_out.pdf";
//出力の保存
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmark added successfully.\nFile saved at " + dataDir);
```

## 結論

おめでとうございます！これで、Aspose.PDF for .NET でサブブックマークを追加するためのステップバイステップ ガイドが完成しました。このコードを使用して、PDF ドキュメント内のブックマークを整理および構造化できます。

高度なブックマーク操作機能の詳細については、公式の Aspose.PDF ドキュメントを必ずご確認ください。

### PDF ファイルに子ブックマークを追加する場合の FAQ

#### Q: PDF ファイルの子ブックマークとは何ですか?

A: 子ブックマークはサブブックマークとも呼ばれ、親ブックマークの下に階層構造になっている PDF ドキュメント内のナビゲーション要素です。これらは、ドキュメントのより整理された詳細な目次を作成する方法を提供します。

#### Q: C# プロジェクトに必要なライブラリをインポートするにはどうすればよいですか?

A: C# プロジェクトに必要なライブラリをインポートするには、次のインポート ディレクティブを使用できます。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

これらのライブラリは、PDF ドキュメントと対話型機能を操作するために必要なクラスと関数を提供します。

#### Q: ドキュメントフォルダーへのパスを指定するにはどうすればよいですか?

 A: 提供されているソース コードでは、次の部分を置き換える必要があります。`"YOUR DOCUMENT DIRECTORY"`作業する PDF ファイルが含まれるフォルダーへの実際のパスを置き換えます。これにより、コードがターゲット PDF ファイルを正しく見つけることができます。

#### Q: 複数レベルの子ブックマークを作成できますか?

A: はい、チュートリアルで説明されているプロセスを拡張することで、複数レベルの子ブックマークを作成できます。サブブックマークを含む親ブックマークを作成し、それらをさらにネストすることで、複雑な PDF ドキュメントのブックマークの階層構造を作成できます。

####  Q：その目的は何ですか？`OutlineItemCollection` class?

 A:`OutlineItemCollection` Aspose.PDF for .NET のクラスは、アウトライン (本質的には PDF ドキュメント内のブックマーク) を作成および管理するために使用されます。このクラスを使用すると、ブックマークのタイトル、フォント スタイル、アクションなどのプロパティを設定できます。

#### Q: 親ブックマークにサブブックマークを追加するにはどうすればよいですか?

 A: 親ブックマークにサブブックマークを追加するには、新しいブックマークを作成します。`OutlineItemCollection`サブブックマークのオブジェクトを取得し、そのプロパティを設定します。次に、`Add`親ブックマークのメソッド`OutlineItemCollection`をクリックして、親のコレクションにサブブックマークを追加します。

#### Q: 子ブックマークの外観をカスタマイズできますか?

A: はい、親ブックマークと同様に、タイトル、フォント スタイル、その他の属性などのプロパティを設定することで、子ブックマークの外観をカスタマイズできます。これにより、視覚的に特徴的で有益なブックマークを作成できます。

#### Q: Aspose.PDF for .NET は他のプログラミング言語と互換性がありますか?

A: Aspose.PDF for .NET は、C# および .NET 環境向けに特別に設計されています。ただし、Aspose は、Java や Android などの他のプログラミング言語に対しても、それぞれのプラットフォームに合わせて調整された同様のライブラリを提供しています。

#### Q: 子ブックマークは PDF のナビゲーションをどのように改善しますか?

A: 子ブックマークは、より構造化され、整理された目次を提供することで、PDF のナビゲーションを改善します。ユーザーは、階層ブックマーク構造を通じてドキュメントの特定のセクションにすばやくアクセスできます。