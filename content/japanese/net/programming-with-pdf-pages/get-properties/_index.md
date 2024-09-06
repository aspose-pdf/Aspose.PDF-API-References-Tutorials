---
title: PDFプロパティを取得
linktitle: PDFプロパティを取得
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、ボックスの寸法や回転などの PDF プロパティを取得するためのステップバイステップ ガイド。
type: docs
weight: 100
url: /ja/net/programming-with-pdf-pages/get-properties/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF のプロパティを取得するプロセスを段階的に説明します。バンドルされている C# ソース コードについて説明し、この機能を理解して独自のプロジェクトに実装するのに役立つ包括的なガイドを提供します。このチュートリアルの最後には、Aspose.PDF for .NET を使用して、アート ボックス、クロップ ボックス、クロップ ボックスなどの PDF ページのさまざまなプロパティにアクセスする方法がわかります。

## 前提条件
始める前に、次のものがあることを確認してください。

- C#プログラミング言語の基礎知識
- 開発環境に Aspose.PDF for .NET がインストールされている

## ステップ1: ドキュメントディレクトリを設定する
まず、ドキュメント ディレクトリへのパスを設定する必要があります。これは、プロパティを取得する PDF ファイルの場所です。「YOUR DOCUMENTS DIRECTORY」を適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: PDF文書を開く
次に、PDF文書を`Document` Aspose.PDF のクラス。PDF ファイルへの正しいパスを必ず指定してください。

```csharp
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

## ステップ3: ページコレクションにアクセスする
これで、ドキュメントのページコレクションにアクセスできます。`Pages`の財産`pdfDocument`物体。

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## ステップ4: 特定のページに移動する
次に、コレクション内のページのインデックスを使用して、特定のページにジャンプできます。以下の例では、2 番目のページ (インデックス 1) にアクセスします。

```csharp
Page pdfPage = pageCollection[1];
```

## ステップ5: ページのプロパティを取得する
これで、アートボックス、クロップボックス、クロップボックスなど、PDFページのさまざまなプロパティを、対応するプロパティを使用して取得できるようになりました。`pdfPage`物体。

```csharp
Console.WriteLine("ArtBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
Console.WriteLine("BleedBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.BleedBox.Height, pdf

Page.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
Console.WriteLine("CropBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
Console.WriteLine("MediaBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
Console.WriteLine("TrimBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
Console.WriteLine("Rect: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
Console.WriteLine("Page number: {0}", pdfPage.Number);
Console.WriteLine("Rotate: {0}", pdfPage.Rotate);
```

### Aspose.PDF for .NET を使用してプロパティを取得するためのサンプル ソース コード 

```csharp

//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントを開く
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
//ページコレクションを取得
PageCollection pageCollection = pdfDocument.Pages;
//特定のページを取得する
Page pdfPage = pageCollection[1];
//ページのプロパティを取得する
System.Console.WriteLine("ArtBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
System.Console.WriteLine("BleedBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.BleedBox.Height, pdfPage.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
System.Console.WriteLine("CropBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
System.Console.WriteLine("MediaBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
System.Console.WriteLine("TrimBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
System.Console.WriteLine("Rect : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
System.Console.WriteLine("Page Number : {0}", pdfPage.Number);
System.Console.WriteLine("Rotate : {0}", pdfPage.Rotate);

```

## 結論
おめでとうございます。Aspose.PDF for .NET を使用して PDF のプロパティを取得できました。PDF ドキュメントを開き、特定のページに移動し、寸法ボックスや回転などのさまざまなページ プロパティを取得する方法を学習しました。この情報を使用して、プロパティに基づいて PDF ファイルの処理をカスタマイズできるようになりました。

高度な機能とカスタマイズの可能性の詳細については、Aspose.PDF for .NET の公式ドキュメントを必ず確認してください。

### よくある質問

#### Q: Aspose.PDF for .NET を使用して PDF のプロパティを取得するにはどうすればよいですか?

A: Aspose.PDF for .NET を使用して PDF のプロパティを取得するには、次の手順に従います。

1. プロパティを取得する PDF ファイルへのパスを指定して、ドキュメント ディレクトリを設定します。
2.  PDF文書を開くには、`Document` Aspose.PDF のクラス。PDF ファイルへの正しいパスを提供します。
3. ドキュメントのページコレクションにアクセスするには、`Pages`の財産`pdfDocument`物体。
4. コレクション内のページのインデックスを使用して特定のページにジャンプします (インデックスは 1 から始まります)。
5.  PDFページのさまざまなプロパティ（ArtBox、BleedBox、CropBox、MediaBox、TrimBox、Rect、Page Number、Rotationなど）を、対応するプロパティを使用して取得します。`pdfPage`物体。

#### Q: Aspose.PDF for .NET を使用して取得できる PDF ページのさまざまなプロパティは何ですか?

A: Aspose.PDF for .NET を使用すると、次のような PDF ページのさまざまなプロパティを取得できます。

- ArtBox: ページのアートワークの寸法を表します。
- BleedBox: ページのブリードの寸法を表します。
- CropBox: トリミング後のページの表示コンテンツのサイズを表します。
- MediaBox: ページの物理メディアの寸法を表します。
- TrimBox: ページのトリミングされたコンテンツの寸法を表します。
- Rect: ページの境界ボックスの寸法を表します。
- ページ番号: ドキュメント内のページ番号を表します。
- 回転: ページの回転角度を表します。

#### Q: PDF ドキュメント内の特定のページにアクセスしてそのプロパティを取得するにはどうすればよいですか?

 A: PDF文書内の特定のページにアクセスしてそのプロパティを取得するには、`Pages`の財産`pdfDocument`オブジェクトを使用してドキュメントのページコレクションにアクセスします。次に、コレクション内のページのインデックスを使用して目的のページにジャンプします。たとえば、2番目のページにアクセスするには、次のようにします。`pdfDocument.Pages[1]` (インデックスは 1 から始まります)。

#### Q: 取得したプロパティに対して、ページ ボックスの変更やサイズ変更などの操作を実行できますか?

A: はい、Aspose.PDF for .NET を使用して PDF ページのプロパティを取得したら、そのプロパティに対してさまざまな操作を実行できます。たとえば、ページ ボックスのサイズを変更したり、ページを回転したり、取得した情報を使用して PDF ドキュメントをカスタム処理および操作したりできます。

#### Q: Aspose.PDF for .NET は、暗号化またはパスワードで保護された PDF ファイルからのプロパティの抽出をサポートしていますか?

A: はい、Aspose.PDF for .NET は、暗号化またはパスワードで保護された PDF ファイルからのプロパティの抽出をサポートしています。PDF ドキュメントを開くために正しいパスワードを入力する限り、チュートリアルで説明したのと同じ方法を使用して、そのプロパティにアクセスして取得できます。