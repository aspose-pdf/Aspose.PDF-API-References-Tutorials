---
title: 複数列の PDF を作成する
linktitle: 複数列の PDF を作成する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して複数列の PDF を作成する方法を学習します。
type: docs
weight: 110
url: /ja/net/programming-with-text/create-multi-column-pdf/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して複数列の PDF を作成する手順を説明します。提供されている C# ソース コードで必要な手順を示します。

## 要件
始める前に、次のものがあることを確認してください。

- マシンにインストールされている Visual Studio またはその他の C# コンパイラ。
- Aspose.PDF for .NET ライブラリ。公式 Aspose Web サイトからダウンロードするか、NuGet などのパッケージ マネージャーを使用してインストールできます。

## ステップ1: プロジェクトを設定する
1. 好みの開発環境で新しい C# プロジェクトを作成します。
2. Aspose.PDF for .NET ライブラリへの参照を追加します。

## ステップ2: 必要な名前空間をインポートする
複数列の PDF を作成するコード ファイルで、ファイルの先頭に次の using ディレクティブを追加します。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## ステップ3: ドキュメントディレクトリを設定する
コード内で、次の行を見つけます。`string dataDir = "YOUR DOCUMENT DIRECTORY";`置き換えて`"YOUR DOCUMENT DIRECTORY"`ドキュメントが保存されているディレクトリへのパスを指定します。

## ステップ4: 新しいドキュメントインスタンスを作成する
新しいインスタンスを作成する`Document`次のコード行を追加してオブジェクトを作成します。

```csharp
Document doc = new Document();
```

## ステップ5: ページの余白を設定する
PDFファイルの左余白と右余白情報を指定するには、`PageInfo.Margin`の財産`Document`.

```csharp
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;
```

## ステップ6: ドキュメントにページを追加する
ドキュメントに新しいページを追加するには、`Add`方法の`Pages`コレクション。提供されたコードでは、新しいページが変数に割り当てられます`page`.

```csharp
Page page = doc.Pages.Add();
```

## ステップ7: グラフオブジェクトを作成し、線を追加する
新規作成`Graph`特定の寸法のオブジェクトを作成し、それに線を追加します。次に、`Graph`に反対する`Paragraphs`ページのコレクション。

```csharp
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
float[] backPos = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
page.Paragraphs.Add(graph1);
```

## ステップ8: HTML形式で見出しテキストを追加する
作成する`HtmlFragment`オブジェクトを作成し、その内容を希望のHTMLテキストに設定します。次に、フラグメントを`Paragraphs`ページのコレクション。

```csharp
string s = "<font face=\"Times New Roman\" size=4>" +
     "<strong>How to Steer Clear of money scams</<strong>" +
     "</font>";
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
```

## ステップ9: 複数の列を持つフローティングボックスを作成する
作成する`FloatingBox`オブジェクトを作成し、列数と列間隔を設定します。次に、テキストフラグメントと線を追加します。`Paragraphs`コレクションの`FloatingBox`.

```csharp
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
box. ColumnInfo. ColumnCount = 2;
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";

TextFragment text1 = new TextFragment("By A Googling (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);

TextFragment text2 = new TextFragment("Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam...");
box.Paragraphs.Add(text2);

Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
box.Paragraphs.Add(graph2);

page.Paragraphs.Add(box);
```

## ステップ10: PDF文書を保存する
PDF文書を保存するには、`Save`方法の`Document`物体。

```csharp
doc.Save(dataDir);
```

### Aspose.PDF for .NET を使用して複数列の PDF を作成するためのサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
//PDFファイルの左余白情報を指定します
doc.PageInfo.Margin.Left = 40;
//PDFファイルの右余白情報を指定します
doc.PageInfo.Margin.Right = 40;
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
//セクションオブジェクトのパラグラフコレクションに行を追加します
page.Paragraphs.Add(graph1);
//線の座標を指定する
float[] posArr = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
//HTMLタグを含むテキストで文字列変数を作成する
string s = "<font face=\"Times New Roman\" size=4>" +
"<strong> How to Steer Clear of money scams</<strong> "
+ "</font>";
//HTMLテキストを含むテキスト段落を作成する
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
//セクションに4つの列を追加します
box.ColumnInfo.ColumnCount = 2;
//列間の間隔を設定する
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";
TextFragment text1 = new TextFragment("By A Googler (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);
text1.TextState.FontSize = 10;
text1.TextState.FontStyle = FontStyles.Italic;
//線を描くグラフオブジェクトを作成する
Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
//線の座標を指定する
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
//セクションオブジェクトの段落コレクションに行を追加します
box.Paragraphs.Add(graph2);
TextFragment text2 = new TextFragment(@"Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam. Pellentesque sit amet elit. Vestibulum interdum pellentesque augue. Cras mollis arcu sit amet purus. Donec augue. Nam mollis tortor a elit. Nulla viverra nisl vel mauris. Vivamus sapien. nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et,nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.");
box.Paragraphs.Add(text2);
page.Paragraphs.Add(box);
dataDir = dataDir + "CreateMultiColumnPdf_out.pdf";
//PDFファイルを保存
doc.Save(dataDir);
Console.WriteLine("\nMulti column pdf file created successfully.\nFile saved at " + dataDir);
```

## 結論
Aspose.PDF for .NET を使用して複数列の PDF を正常に作成しました。結果の PDF ファイルは、指定した出力ファイル パスにあります。

### よくある質問

#### Q: このチュートリアルの焦点は何ですか?

このチュートリアルでは、Aspose.PDF for .NET ライブラリを使用して複数列の PDF を作成する手順を説明します。提供されている C# ソース コードは、これを実現するために必要な手順を示しています。

#### Q: このチュートリアルではどの名前空間をインポートすればよいですか?

A: 複数列の PDF を作成するコード ファイルで、ファイルの先頭に次の名前空間をインポートします。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### Q: ドキュメントディレクトリを指定するにはどうすればよいですか?

 A: コード内で次の行を見つけてください`string dataDir = "YOUR DOCUMENT DIRECTORY";`置き換えて`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。

#### Q: 新しい Document インスタンスを作成するにはどうすればよいですか?

 A: ステップ4では、新しいインスタンスを作成します。`Document`提供されたコードを使用してオブジェクトを作成します。

#### Q: ページの余白を設定するにはどうすればよいですか?

 A: ステップ5では、`PageInfo.Margin`の財産`Document` PDF ファイルの左余白と右余白の情報を指定します。

#### Q: ドキュメントにページを追加するにはどうすればよいですか?

 A: ステップ6では、`Add`方法の`Pages`コレクション。

#### Q: グラフ オブジェクトを作成して線を追加するにはどうすればよいですか?

 A: ステップ7では、新しい`Graph`オブジェクトに線を追加し、`Graph`に反対する`Paragraphs`ページのコレクション。

#### Q: HTML 形式で見出しテキストを追加するにはどうすればよいですか?

 A: ステップ8では、`HtmlFragment`オブジェクトを作成し、その内容を目的のHTMLテキストに設定してから、フラグメントを`Paragraphs`ページのコレクション。

#### Q: 複数の列を持つ FloatingBox を作成するにはどうすればよいですか?

 A: ステップ9では、`FloatingBox`複数の列と列間隔を持つオブジェクトを作成し、テキストフラグメントと線を追加します。`Paragraphs`コレクションの`FloatingBox`.

#### Q: PDF ドキュメントを保存するにはどうすればよいですか?

 A: ステップ10では、`Save`方法の`Document`物体。

#### Q: このチュートリアルから得られる主な教訓は何ですか?

A: このチュートリアルでは、Aspose.PDF for .NET を使用して複数列の PDF ドキュメントを作成する方法を学習しました。これは、構造化され整理されたレイアウトでコンテンツを表示する場合に便利です。