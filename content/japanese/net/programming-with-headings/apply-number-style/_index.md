---
title: PDF ファイルに数値スタイルを適用する
linktitle: PDF ファイルに数値スタイルを適用する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルの見出しに番号付けスタイルを適用する方法を学びます。ステップバイステップのガイド。
type: docs
weight: 10
url: /ja/net/programming-with-headings/apply-number-style/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルに番号付けスタイルを適用するための次の C# ソース コードを段階的に説明します。

始める前に、Aspose.PDF ライブラリをインストールし、開発環境をセットアップしていることを確認してください。 C# プログラミングの基本的な知識も必要です。

### ステップ 1: ドキュメント ディレクトリのセットアップ

提供されたソース コードでは、生成された PDF ファイルを保存するディレクトリを指定する必要があります。 「dataDir」変数を目的のディレクトリに変更します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### ステップ 2: PDF ドキュメントの作成

指定された寸法と余白を使用して新しい PDF ドキュメントを作成します。

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

### ステップ 3: ページとフローティング コンテナの作成

ドキュメントにページを追加し、コンテンツを整理するためのフローティング コンテナを作成します。

```csharp
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
```

### ステップ 4: 番号付きの見出しを追加する

指定された番号を持つヘッダーを作成し、それらをフローティング コンテナーに追加します。

```csharp
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading. IsInList = true;
heading. StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading. IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);

Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "Listing 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);

Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "The value, at the effective date of the plan, of the assets to be distributed under the plan

";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
```

### ステップ 5: PDF ドキュメントを保存する

生成された PDF ドキュメントを指定されたディレクトリに保存します。

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style successfully applied to headers.\nFile saved as: " + dataDir);
```

### Aspose.PDF for .NET を使用した数値スタイルの適用のサンプル ソース コード 
```csharp

//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
TextFragment textFragment = new TextFragment();
TextSegment segment = new TextSegment();
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading.IsInList = true;
heading.StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "List 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "the value, as of the effective date of the plan, of property to be distributed under the plan onaccount of each allowed";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumber style applied successfully in headings.\nFile saved at " + dataDir);  
          
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントの見出しに番号付けスタイルを適用する方法を説明しました。この知識を利用して、見出しにカスタムの番号を付けた PDF ドキュメントを作成できるようになりました。

### PDF ファイルに数値スタイルを適用するための FAQ

#### Q: PDF ドキュメントの番号付けスタイルとは何ですか?

A: 番号付けスタイルとは、PDF ドキュメント内の見出しまたはセクションに番号を付ける形式を指します。階層構造を提供するために、数字、文字、またはその他の文字を含めることができます。

#### Q: PDF ドキュメントの見出しに番号付けスタイルを適用する必要があるのはなぜですか?

A: 番号付けスタイルを見出しに適用すると、PDF ドキュメントの読みやすさと構成が向上します。これは、読者がコンテンツの階層構造を簡単にナビゲートして理解するのに役立ちます。

#### Q: Aspose.PDF for .NET とは何ですか?

A: Aspose.PDF for .NET は、開発者が .NET アプリケーションでプログラム的に PDF ファイルを操作できるようにするライブラリです。 PDF ドキュメントを作成、編集、変換、操作するための幅広い機能を提供します。

#### Q: C# プロジェクトに必要なライブラリをインポートするにはどうすればよいですか?

A: C# プロジェクトに必要なライブラリをインポートするには、次のインポート ディレクティブを含めます。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

これらのディレクティブを使用すると、PDF ドキュメントを操作し、番号付けスタイルを適用するために必要なクラスとメソッドにアクセスできるようになります。

#### Q: 生成された PDF ファイルを保存するディレクトリを指定するにはどうすればよいですか?

A: 提供されたソース コードで、「dataDir」変数を変更して、生成された PDF ファイルを保存するディレクトリを指定します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

交換する`"YOUR DOCUMENTS DIRECTORY"`実際のディレクトリパスを使用します。

#### Q: 寸法と余白を指定した PDF ドキュメントを作成するにはどうすればよいですか?

A: 寸法と余白を指定して PDF ドキュメントを作成するには、次のコードを使用します。

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

#### Q: 番号付けスタイルの見出しを PDF ドキュメントに追加するにはどうすればよいですか?

A: 番号付けスタイルを持つ見出しを PDF ドキュメントに追加するには、提供されているコード サンプルを使用して見出しを作成し、番号付けスタイルをカスタマイズします。必要に応じて、テキスト、番号付けスタイル、開始番号、自動シーケンスなどのプロパティを調整します。

#### Q: 生成された PDF ドキュメントを保存するにはどうすればよいですか?

 A: 生成された PDF ドキュメントを保存するには、`Save`の方法`pdfDoc`物体：

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style applied to headers.\nFile saved as: " + dataDir);
```

#### Q: 番号付けスタイルが適用されていることを確認するにはどうすればよいですか?

A: 生成された PDF ファイルを開いて、指定された番号付けスタイルが見出しに適用されていることを確認します。

#### Q: 番号付けスタイルをさらにカスタマイズできますか?

 A: はい、プロパティを調整することで、番号付けスタイルをさらにカスタマイズできます。`Heading`番号付けスタイル タイプ、開始番号、自動シーケンスなどのオブジェクト。

#### Q: 文書の異なるセクションに異なる番号付けスタイルを適用できますか?

A: はい、複数のセクションを作成することで、文書の異なるセクションに異なる番号付けスタイルを適用できます。`Heading`さまざまなスタイルとシーケンスを持つオブジェクト。