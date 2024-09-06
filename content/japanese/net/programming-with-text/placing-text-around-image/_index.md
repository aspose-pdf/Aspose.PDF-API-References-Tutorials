---
title: PDF ファイル内の画像の周囲にテキストを配置する
linktitle: PDF ファイル内の画像の周囲にテキストを配置する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内の画像の周囲にテキストを配置する方法を学習します。
type: docs
weight: 260
url: /ja/net/programming-with-text/placing-text-around-image/
---
このチュートリアルでは、.NET 用の Aspose.PDF ライブラリを使用して PDF ファイル内の画像の周囲にテキストを配置する方法について説明します。提供されている C# ソース コードを使用して、表の作成、画像の追加、画像の周囲にテキストを配置するプロセスを段階的に説明します。

## 要件

始める前に、次のものがあることを確認してください。

- Aspose.PDF for .NET ライブラリがインストールされました。
- C# プログラミングの基本的な理解。

## ステップ1: ドキュメントディレクトリを設定する

まず、生成されたPDFファイルを保存するディレクトリへのパスを設定する必要があります。`"YOUR DOCUMENT DIRECTORY"`の`dataDir`目的のディレクトリへのパスを含む変数。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ2: ドキュメントとページを作成する

次に、`Document`オブジェクトを作成し、`Pages.Add()`方法。

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## ステップ3: テーブルを作成する

テーブルを作成するには、`Table`クラスを作成し、ページの段落コレクションに追加します。

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## ステップ4: 表の列幅と余白を設定する

テーブルの列幅を設定し、`MarginInfo`余白を設定するオブジェクト。

```csharp
table1. ColumnWidths = "120,270";
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;
table1. DefaultCellPadding = margin;
```

## ステップ5: テーブルに画像を追加する

私たちは`Image`オブジェクトを作成し、画像ファイルのパスを指定して、画像の固定の高さと幅を設定します。次に、画像をテーブル セルの段落コレクションに追加します。

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## ステップ6: 画像の周囲にテキストを追加する

HTML形式のテキストを含む文字列変数を作成し、`HtmlFragment`オブジェクト。次に、画像を含むテーブル セルに HTML テキストを追加します。

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## ステップ7: 追加テキストを追加する

私たちは別のものを作ります`HtmlFragment`追加の HTML 形式のテキストを含むオブジェクトを作成し、それを別のテーブル セルに追加します。

```csharp
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

## ステップ8: PDFドキュメントを保存する

最後に、PDF ドキュメントを指定された出力ファイルに保存します。

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

### Aspose.PDF for .NET を使用して画像の周囲にテキストを配置するためのサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントオブジェクトをインスタンス化する
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
//PDFにページを作成する
Aspose.Pdf.Page page = doc.Pages.Add();
//テーブルオブジェクトをインスタンス化する
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
//希望するセクションの段落コレクションに表を追加します
page.Paragraphs.Add(table1);
//テーブルの列幅を設定する
table1.ColumnWidths = "120 270";
//MarginInfoオブジェクトを作成し、左、下、右、上の余白を設定します。
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
//デフォルトのセルパディングをMarginInfoオブジェクトに設定する
table1.DefaultCellPadding = margin;
//表に行を作成し、行にセルを作成します
Aspose.Pdf.Row row1 = table1.Rows.Add();
//画像オブジェクトを作成する
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
//画像ファイルのパスを指定する
logo.File = dataDir + "aspose-logo.jpg";
//画像の固定高さを指定する
logo.FixHeight = 120;
//画像の固定幅を指定する
logo.FixWidth = 110;
row1.Cells.Add();
//表セルの段落コレクションに画像を追加する
row1.Cells[0].Paragraphs.Add(logo);
//HTMLタグを含むテキストで文字列変数を作成する
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
//画像の右側に追加するテキストオブジェクトを作成します
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
//HTMLテキストを含むテキスト段落をテーブルセルに追加します
row1.Cells[1].Paragraphs.Add(TitleText);
//行の内容の垂直方向の配置を上に設定します
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
//表に行を作成し、行にセルを作成します
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
//2行目の行スパン値を2に設定します。
SecondRow.Cells[0].ColSpan = 2;
// 2行目の垂直方向の配置を上に設定します
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
//HTMLテキストを含むテキスト段落をテーブルセルに追加します
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
//PDFファイルを保存する
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## 結論

このチュートリアルでは、.NET 用の Aspose.PDF ライブラリを使用して、PDF ドキュメント内の画像の周囲にテキストを配置する方法を学習しました。ステップ バイ ステップ ガイドに従って、提供されている C# コードを実行すると、PDF ドキュメント内で表を作成し、画像を追加し、画像の周囲にテキストを配置できます。

### よくある質問

#### Q: 「PDF ファイル内の画像の周囲にテキストを配置する」チュートリアルの目的は何ですか?

A: 「PDF ファイル内の画像の周囲にテキストを配置する」チュートリアルでは、.NET 用の Aspose.PDF ライブラリを使用して PDF ドキュメント内の画像の周囲にテキストを配置する方法を説明します。このチュートリアルでは、表の作成、画像の追加、画像の周囲にテキストを配置するためのステップバイステップのガイドと C# ソース コードが提供されます。

#### Q: PDF ドキュメント内の画像の周囲にテキストを配置する必要があるのはなぜですか?

A: 画像の周囲にテキストを配置すると、PDF ドキュメントの視覚的な表現が強化され、より魅力的で有益なものになります。この手法は、画像とテキストを美しく組み合わせたいドキュメント、パンフレット、レポート、その他の資料でよく使用されます。

#### Q: ドキュメント ディレクトリを設定するにはどうすればよいですか?

A: ドキュメントディレクトリを設定するには:

1. 交換する`"YOUR DOCUMENT DIRECTORY"`の`dataDir`生成された PDF ファイルを保存するディレクトリへのパスを持つ変数。

#### Q: テーブルを作成して画像を追加するにはどうすればよいですか?

 A: チュートリアルでは、`Table`クラスとテーブルに画像を追加するには、`Image`クラス。テーブル セルに追加する前に、画像ファイルのパス、高さ、幅を指定します。

#### Q: 画像の周囲にテキストを配置するにはどうすればよいですか?

 A: 画像の周囲にテキストを配置するには、`HtmlFragment`クラス。このテキストには、タイトルと本文の両方が含まれます。次に、この HTML テキストを画像セルに隣接するテーブル セルに追加します。

#### Q: テキストと画像の外観をカスタマイズできますか?

A: はい、HTML タグとプロパティを使用して、テキストと画像の外観をカスタマイズできます。たとえば、テキストのフォント サイズ、色、スタイル、配置を設定できます。さらに、画像のサイズと寸法を調整することもできます。

#### Q: PDF ドキュメントを保存するにはどうすればよいですか?

 A: 表に画像とテキストを追加したら、`Save`方法の`Document`クラス。出力ファイルのパスを引数として指定します。`Save`方法。

#### Q: このチュートリアルで期待される出力は何ですか?

A: チュートリアルに従って、提供されている C# コードを実行すると、画像の周囲にテキストを配置する方法を示す PDF ドキュメントが生成されます。出力ドキュメントには、画像とその周囲に配置されたテキストを含む表が含まれます。

#### Q: JPG 以外の画像形式を使用できますか?

 A: はい、PNG、BMP、GIFなど、Aspose.PDFライブラリでサポートされているさまざまな画像形式を使用できます。`Image`オブジェクトの場合は、目的の画像形式のファイル パスを指定します。

#### Q: このチュートリアルには有効な Aspose ライセンスが必要ですか?

A: はい、このチュートリアルを正しく動作させるには、有効な Aspose ライセンスが必要です。Aspose Web サイトからフル ライセンスを購入するか、30 日間の一時ライセンスを取得できます。