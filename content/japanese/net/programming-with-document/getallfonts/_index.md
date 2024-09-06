---
title: PDF ファイル内のすべてのフォントを取得
linktitle: PDF ファイル内のすべてのフォントを取得
second_title: Aspose.PDF for .NET API リファレンス
description: このステップバイステップ ガイドとサンプル コードを使用して、Aspose.PDF for .NET を使用して PDF ファイルで使用されているすべてのフォントをプログラムで取得する方法を学習します。
type: docs
weight: 160
url: /ja/net/programming-with-document/getallfonts/
---
Aspose.PDF for .NET は、開発者がプログラムで PDF ファイルを操作できるようにする強力なライブラリです。このライブラリが提供する機能の 1 つは、PDF ファイルで使用されているすべてのフォントを取得する機能です。これは、PDF ファイル内のフォントをプログラムで分析または操作する必要がある場合に役立ちます。

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントで使用されているすべてのフォントを取得する方法について説明します。サンプル ソース コードとともに、これを行う方法についてのステップ バイ ステップ ガイドを提供します。

## ステップ 1: 新しい C# コンソール アプリケーションを作成する
まず、Visual Studio で新しい C# コンソール アプリケーションを作成します。任意の名前を付けることができます。プロジェクトを作成したら、Aspose.PDF for .NET ライブラリへの参照を追加する必要があります。

## ステップ2: Aspose.PDF名前空間をインポートする
Aspose.PDF 名前空間をインポートするには、C# ファイルの先頭に次のコード行を追加します。

```csharp
using Aspose.Pdf;
```

## ステップ3: PDFドキュメントを読み込む
フォントを取得する PDF ドキュメントを読み込みます。

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## ステップ4: すべてのフォントを入手する
PDF ドキュメントで使用されているすべてのフォントを取得します。

```csharp
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
```

## ステップ5: すべてのフォントを印刷する
PDF ドキュメントで使用されているすべてのフォントを印刷します。

```csharp
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

### Aspose.PDF for .NET を使用してすべてのフォントを取得するためのサンプル ソース コード
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

## 結論
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントで使用されているすべてのフォントを取得する方法について説明しました。PDF ドキュメントで使用されているすべてのフォントを取得することは、PDF ドキュメント内のフォントをプログラムで分析または操作する必要がある場合に役立ちます。Aspose.PDF for .NET は、PDF ドキュメントで使用されているすべてのフォントの取得など、PDF ドキュメントを操作するためのシンプルで使いやすい API を提供します。

### よくある質問

#### Q: PDF ドキュメントで使用されているすべてのフォントを取得する必要があるのはなぜですか?

A: PDF ドキュメントで使用されているすべてのフォントを取得すると、フォントの置換やフォントのカスタマイズなど、さまざまな目的でフォントをプログラムで分析または操作する必要がある場合に役立ちます。

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメントで使用されているすべてのフォントを取得するにはどうすればよいですか?

 A: Aspose.PDF for .NETを使用してPDF文書で使用されているすべてのフォントを取得するには、`GetAllFonts`方法の`FontUtilities`クラス。このメソッドは、`Aspose.Pdf.Text.Font` PDF ドキュメントで使用されるフォントを表すオブジェクト。

#### Q: 特定の基準に基づいてフォントをフィルタリングできますか?

A: はい、Aspose.PDF for .NET を使用して、特定の基準に基づいてフォントをフィルターできます。すべてのフォントを取得したら、プログラムでフォントを分析し、必要に応じてフィルター ロジックを適用できます。

#### Q: Aspose.PDF for .NET はさまざまなフォント形式と互換性がありますか?

A: はい、Aspose.PDF for .NET は、TrueType、OpenType、Type 1 フォントなど、さまざまなフォント形式と互換性があります。さまざまなフォント形式に対応し、PDF ドキュメントの操作中に処理できます。