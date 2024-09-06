---
title: PDFページサイズを取得する
linktitle: PDFページサイズを取得する
second_title: Aspose.PDF for .NET API リファレンス
description: このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ページのサイズを取得し、操作を実行する方法について説明します。プロセス全体をガイドする詳細な手順が提供されます。
type: docs
weight: 60
url: /ja/net/programming-with-pdf-pages/get-dimensions/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルのページ寸法を取得するプロセスを段階的に説明します。バンドルされている C# ソース コードについて説明し、この機能を理解して独自のプロジェクトに実装するのに役立つ包括的なガイドを提供します。このチュートリアルの最後には、Aspose.PDF for .NET を使用して PDF ファイルのページ寸法を取得する方法がわかります。

## 前提条件
始める前に、次のものがあることを確認してください。

- C#プログラミング言語の基礎知識
- 開発環境に Aspose.PDF for .NET がインストールされている

## ステップ1: ドキュメントディレクトリを定義する
まず、ドキュメント ディレクトリへのパスを設定する必要があります。これは、PDF ファイルが保存されている場所です。「YOUR DOCUMENTS DIRECTORY」を適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: PDF文書を開く
その後、PDFファイルを開くには、`Document` Aspose.PDF のクラス。PDF ファイルへの正しいパスを必ず指定してください。

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## ステップ3: 空白ページを追加する（必要な場合）
 PDF文書にすでにページが含まれている場合は、インデックスを使用して既存のページにジャンプできます。`1` (最初のページのインデックスは 1 です)。それ以外の場合は、ドキュメントに新しいページを追加できます。

```csharp
Page page = pdfDocument.Pages.Count > 0? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

## ステップ4: ページのサイズを取得する
ページサイズを取得するには、`GetPageRect()`方法の`Page`オブジェクトを返します。このメソッドは`Rectangle`ページのサイズを含むオブジェクト。幅と高さにアクセスするには、`Width`そして`Height`プロパティ。

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

## ステップ5: ページを回転する
ページを回転させたい場合は、`Rotate`の財産`Page`オブジェクト。この例では、ページは 90 度回転します。

```csharp
page. Rotate = Rotate. on90;
```

## ステップ6: ページサイズを再度取得する
ページを回転した後、`GetPageRect()`方法。

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

### Aspose.PDF for .NET を使用してディメンションを取得するためのサンプル ソース コード 

```csharp

//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントを開く
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
//PDF文書に空白ページを追加します
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
//ページの高さと幅の情報を取得する
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
//ページを90度回転する
page.Rotate = Rotation.on90;
//ページの高さと幅の情報を取得する
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);

```

## 結論
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルのページのサイズを取得する方法を学習しました。提供されている手順に従うことで、ページのサイズを簡単に抽出し、その他の PDF 操作を実行できます。Aspose.PDF for .NET は PDF ファイルの操作に優れた柔軟性を提供し、強力でカスタマイズされたソリューションを開発できます。

Aspose.PDF のドキュメントをさらに詳しく調べて、このライブラリが提供するすべての機能を確認してください。

### PDF ページ寸法の取得に関する FAQ

#### Q: PDF ファイル内の特定のページのサイズを取得するにはどうすればよいですか?

A: PDFファイル内の特定のページのサイズを取得するには、`GetPageRect()`方法の`Page` Aspose.PDF for .NETのオブジェクト。このメソッドは`Rectangle`ページの寸法 (幅と高さ) を含むオブジェクト。

####  Q:`GetPageRect(true)` method do in the provided C# source code?

 A:`GetPageRect(true)`提供されている C# ソース コードのメソッドは、回転を適用した後のページの寸法を返します。ページが回転されている場合、メソッドは回転したページの寸法を返しますが、これは元の寸法とは異なる場合があります。

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメント内のすべてのページのサイズを取得できますか?

 A: はい、PDF文書内のすべてのページの寸法を取得するには、`Pages`コレクションの`Document`オブジェクトと使用`GetPageRect(true)`各ページのメソッド。

#### Q: ページの寸法に基づいてページの向き (縦向きまたは横向き) を判断するにはどうすればよいですか?

A: ページの寸法に基づいてページの向きを判断するには、ページの幅と高さを比較します。幅が高さより大きい場合、ページは横向きであり、高さが幅より大きい場合、ページは縦向きです。

#### Q: Aspose.PDF for .NET を使用してページのサイズを変更できますか?

 A: はい、Aspose.PDF for .NETでページのサイズを変更することができます。`Rectangle`ページのサイズを表すオブジェクトを使用すると、必要に応じて幅と高さを調整し、変更をページに適用できます。