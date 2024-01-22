---
title: PDF ファイルの画像の周囲にテキストを配置する
linktitle: PDF ファイルの画像の周囲にテキストを配置する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内の画像の周囲にテキストを配置する方法を学びます。
type: docs
weight: 260
url: /ja/net/programming-with-text/placing-text-around-image/
---
このチュートリアルでは、.NET 用の Aspose.PDF ライブラリを使用して、PDF ファイル内の画像の周囲にテキストを配置する方法を説明します。提供されている C# ソース コードを使用して、テーブルの作成、画像の追加、画像の周囲にテキストを配置するというプロセスを段階的に説明します。

## 要件

始める前に、以下のものがあることを確認してください。

- Aspose.PDF for .NET ライブラリがインストールされています。
- C# プログラミングの基本的な理解。

## ステップ 1: ドキュメント ディレクトリを設定する

まず、生成された PDF ファイルを保存するディレクトリへのパスを設定する必要があります。交換する`"YOUR DOCUMENT DIRECTORY"`の中に`dataDir`変数を目的のディレクトリへのパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: ドキュメントとページを作成する

次に、`Document`オブジェクトを作成し、それに使用してページを追加します。`Pages.Add()`方法。

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## ステップ 3: テーブルを作成する

を使用してテーブルを作成します`Table`クラスを作成し、ページの段落コレクションに追加します。

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## ステップ 4: テーブルの列幅と余白を設定する

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

## ステップ 5: テーブルに画像を追加する

私たちは`Image`オブジェクトを指定し、画像ファイルのパスを指定し、画像の固定の高さと幅を設定します。次に、表のセルの段落コレクションに画像を追加します。

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## ステップ 6: 画像の周囲にテキストを追加する

HTML 形式のテキストを含む文字列変数を作成し、`HtmlFragment`物体。次に、画像を含む表のセルに HTML テキストを追加します。

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## ステップ 7: 追加のテキストを追加する

別のものを作成します`HtmlFragment`追加の HTML 形式のテキストを含むオブジェクトを作成し、それを別の表のセルに追加します。

```csharp
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

## ステップ 8: PDF ドキュメントを保存する

最後に、PDF ドキュメントを指定した出力ファイルに保存します。

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

### Aspose.PDF for .NET を使用して画像の周囲にテキストを配置するためのサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントオブジェクトをインスタンス化する
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
//PDF でページを作成する
Aspose.Pdf.Page page = doc.Pages.Add();
//テーブルオブジェクトをインスタンス化する
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
//目的のセクションの段落コレクションに表を追加します
page.Paragraphs.Add(table1);
//テーブルの列幅で設定します
table1.ColumnWidths = "120 270";
//MarginInfo オブジェクトを作成し、その左、下、右、上マージンを設定します。
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
//デフォルトのセルパディングを MarginInfo オブジェクトに設定します。
table1.DefaultCellPadding = margin;
//テーブルに行を作成し、その行にセルを作成します。
Aspose.Pdf.Row row1 = table1.Rows.Add();
//画像オブジェクトを作成する
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
//画像ファイルのパスを指定する
logo.File = dataDir + "aspose-logo.jpg";
//画像の固定高さを指定する
logo.FixHeight = 120;
//画像の固定幅を指定します
logo.FixWidth = 110;
row1.Cells.Add();
//表セルの段落コレクションに画像を追加します。
row1.Cells[0].Paragraphs.Add(logo);
// HTMLタグを含むテキストを含む文字列変数を作成する
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
//画像の右側に追加するテキストオブジェクトを作成します
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
//HTML テキストを含むテキスト段落を表のセルに追加します。
row1.Cells[1].Paragraphs.Add(TitleText);
//行の内容の垂直方向の配置を上に設定します。
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
//テーブルに行を作成し、その行にセルを作成します。
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
// 2 番目の行の行スパン値を 2 に設定します。
SecondRow.Cells[0].ColSpan = 2;
// 2 行目の垂直方向の配置を「上」に設定します。
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
//HTML テキストを含むテキスト段落を表のセルに追加します。
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
//PDF ファイルを保存する
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## 結論

このチュートリアルでは、.NET 用の Aspose.PDF ライブラリを使用して、PDF ドキュメント内の画像の周囲にテキストを配置する方法を学習しました。ステップバイステップのガイドに従って、提供されている C# コードを実行すると、PDF ドキュメント内で表を作成し、画像を追加し、画像の周囲にテキストを配置できます。

### よくある質問

#### Q: 「PDF ファイルの画像の周囲にテキストを配置する」チュートリアルの目的は何ですか?

A: 「PDF ファイル内の画像の周囲にテキストを配置する」チュートリアルでは、.NET 用の Aspose.PDF ライブラリを使用して、PDF ドキュメント内の画像の周囲にテキストを配置する方法を示します。このチュートリアルでは、テーブルの作成、画像の追加、画像の周囲にテキストの配置を行うためのステップバイステップ ガイドと C# ソース コードを提供します。

#### Q: PDF ドキュメント内の画像の周囲にテキストを配置したいのはなぜですか?

A: 画像の周囲にテキストを配置すると、PDF ドキュメントの視覚的なプレゼンテーションが強化され、より魅力的で有益なものになります。このテクニックは、文書、パンフレット、レポート、その他の画像とテキストを美しく組み合わせたい資料でよく使用されます。

#### Q: ドキュメント ディレクトリはどのように設定すればよいですか?

A: ドキュメント ディレクトリを設定するには:

1. 交換する`"YOUR DOCUMENT DIRECTORY"`の中に`dataDir`変数には、生成された PDF ファイルを保存するディレクトリへのパスを指定します。

#### Q: テーブルを作成し、そこに画像を追加するにはどうすればよいですか?

 A: このチュートリアルでは、`Table`クラスを作成し、を使用してテーブルに画像を追加します。`Image`クラス。画像ファイルのパス、高さ、幅を指定してから、表のセルに追加します。

#### Q: 画像の周囲にテキストを配置するにはどうすればよいですか?

 A: 画像の周囲にテキストを配置するには、`HtmlFragment`クラス。このテキストにはタイトルと本文の両方が含まれます。次に、この HTML テキストを画像セルに隣接する表のセルに追加します。

#### Q: テキストと画像の外観をカスタマイズできますか?

A: はい、HTML タグとプロパティを使用してテキストと画像の外観をカスタマイズできます。たとえば、テキストのフォント サイズ、色、スタイル、配置を設定できます。さらに、画像のサイズと寸法を調整することもできます。

#### Q: PDF ドキュメントを保存するにはどうすればよいですか?

 A: 画像とテキストを表に追加した後、次のコマンドを使用して PDF ドキュメントを保存できます。`Save`の方法`Document`クラス。必要な出力ファイルのパスを引数として指定します。`Save`方法。

#### Q: このチュートリアルで期待される成果は何ですか?

A: チュートリアルに従って、提供されている C# コードを実行すると、画像の周囲にテキストを配置する方法を示す PDF ドキュメントが生成されます。出力ドキュメントには、画像とテキストが周囲に配置された表が含まれます。

#### Q: JPG 以外の画像形式を使用できますか?

 A: はい、Aspose.PDF ライブラリでサポートされているさまざまな画像形式 (PNG、BMP、GIF など) を使用できます。を作成するときは、`Image`オブジェクトでは、目的の画像形式のファイル パスを指定します。

#### Q: このチュートリアルには有効な Aspose ライセンスが必要ですか?

A: はい、このチュートリアルが正しく動作するには、有効な Aspose ライセンスが必要です。 Aspose Web サイトから完全ライセンスを購入するか、30 日間の一時ライセンスを取得できます。