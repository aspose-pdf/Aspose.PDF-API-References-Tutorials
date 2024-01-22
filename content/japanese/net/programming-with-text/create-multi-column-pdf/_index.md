---
title: 複数列の PDF を作成する
linktitle: 複数列の PDF を作成する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して複数列の PDF を作成する方法を学びます。
type: docs
weight: 110
url: /ja/net/programming-with-text/create-multi-column-pdf/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して複数列の PDF を作成するプロセスを説明します。提供されている C# ソース コードは、必要な手順を示しています。

## 要件
始める前に、以下のものがあることを確認してください。

- マシンにインストールされている Visual Studio またはその他の C# コンパイラー。
- .NET ライブラリ用の Aspose.PDF。 Aspose の公式 Web サイトからダウンロードするか、NuGet などのパッケージ マネージャーを使用してインストールできます。

## ステップ 1: プロジェクトをセットアップする
1. 好みの開発環境で新しい C# プロジェクトを作成します。
2. Aspose.PDF for .NET ライブラリへの参照を追加します。

## ステップ 2: 必要な名前空間をインポートする
複数列の PDF を作成するコード ファイルで、ファイルの先頭に次の using ディレクティブを追加します。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## ステップ 3: ドキュメント ディレクトリを設定する
コード内で、次の行を見つけます。`string dataDir = "YOUR DOCUMENT DIRECTORY";`そして交換してください`"YOUR DOCUMENT DIRECTORY"`ドキュメントが保存されているディレクトリへのパスを置き換えます。

## ステップ 4: 新しい Document インスタンスを作成する
新しいインスタンスを作成する`Document`次のコード行を追加してオブジェクトを作成します。

```csharp
Document doc = new Document();
```

## ステップ 5: ページ余白を設定する
PDF ファイルの左右の余白情報を指定します。`PageInfo.Margin`の財産`Document`.

```csharp
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;
```

## ステップ 6: ドキュメントにページを追加する
を使用してドキュメントに新しいページを追加します。`Add`の方法`Pages`コレクション。提供されたコードでは、新しいページが変数に割り当てられます。`page`.

```csharp
Page page = doc.Pages.Add();
```

## ステップ 7: グラフ オブジェクトを作成し、線を追加する
新しいを作成します`Graph`特定の寸法のオブジェクトを作成し、それに線を追加します。次に、`Graph`に反対する`Paragraphs`ページのコレクション。

```csharp
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
float[] backPos = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
page.Paragraphs.Add(graph1);
```

## ステップ 8: HTML 形式で見出しテキストを追加する
を作成します`HtmlFragment`オブジェクトを作成し、そのコンテンツを目的の HTML テキストに設定します。次に、フラグメントを`Paragraphs`ページのコレクション。

```csharp
string s = "<font face=\"Times New Roman\" size=4>" +
     "<strong>How to Steer Clear of money scams</<strong>" +
     "</font>";
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
```

## ステップ 9: 複数の列を含む FloatingBox を作成する
を作成します`FloatingBox`オブジェクトを選択し、列数と列間隔を設定します。次に、テキストの断片と行を`Paragraphs`のコレクション`FloatingBox`.

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

## ステップ 10: PDF ドキュメントを保存する
PDF ドキュメントを保存するには、`Save`の方法`Document`物体。

```csharp
doc.Save(dataDir);
```

### Aspose.PDF for .NET を使用して複数列の PDF を作成するためのサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
//PDF ファイルの左余白情報を指定します
doc.PageInfo.Margin.Left = 40;
//PDF ファイルの右マージン情報を指定します
doc.PageInfo.Margin.Right = 40;
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
//セクションオブジェクトのパラフレーズコレクションに行を追加します
page.Paragraphs.Add(graph1);
//線の座標を指定します
float[] posArr = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
//HTMLタグを含むテキストを含む文字列変数を作成する
string s = "<font face=\"Times New Roman\" size=4>" +
"<strong> How to Steer Clear of money scams</<strong> "
+ "</font>";
//HTML テキストを含むテキスト段落を作成する
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
//セクションに 4 つの列を追加します
box.ColumnInfo.ColumnCount = 2;
//列間の間隔を設定します
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
//線の座標を指定します
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
//セクションオブジェクトの段落コレクションに行を追加します
box.Paragraphs.Add(graph2);
TextFragment text2 = new TextFragment(@"Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam. Pellentesque sit amet elit. Vestibulum interdum pellentesque augue. Cras mollis arcu sit amet purus. Donec augue. Nam mollis tortor a elit. Nulla viverra nisl vel mauris. Vivamus sapien. nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et,nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.");
box.Paragraphs.Add(text2);
page.Paragraphs.Add(box);
dataDir = dataDir + "CreateMultiColumnPdf_out.pdf";
//PDFファイルを保存する
doc.Save(dataDir);
Console.WriteLine("\nMulti column pdf file created successfully.\nFile saved at " + dataDir);
```

## 結論
Aspose.PDF for .NET を使用して複数列の PDF が正常に作成されました。作成された PDF ファイルは、指定した出力ファイル パスに表示されます。

### よくある質問

#### Q: このチュートリアルの焦点は何ですか?

このチュートリアルは、Aspose.PDF for .NET ライブラリを使用して複数列の PDF を作成するプロセスをガイドすることに重点を置いています。提供されている C# ソース コードは、これを実現するために必要な手順を示しています。

#### Q: このチュートリアルではどの名前空間をインポートする必要がありますか?

A: 複数列 PDF を作成するコード ファイルで、ファイルの先頭に次の名前空間をインポートします。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### Q: ドキュメント ディレクトリを指定するにはどうすればよいですか?

 A: コード内で次の行を見つけます。`string dataDir = "YOUR DOCUMENT DIRECTORY";`そして交換してください`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを置き換えます。

#### Q: 新しい Document インスタンスを作成するにはどうすればよいですか?

 A: ステップ 4 では、新しいインスタンスを作成します。`Document`提供されたコードを使用してオブジェクトを作成します。

#### Q: ページの余白はどのように設定すればよいですか?

 A: ステップ 5 では、`PageInfo.Margin`の財産`Document` PDF ファイルの左右の余白情報を指定します。

#### Q: ドキュメントにページを追加するにはどうすればよいですか?

 A: ステップ 6 では、`Add`の方法`Pages`コレクション。

#### Q: Graph オブジェクトを作成して線を追加するにはどうすればよいですか?

 A: ステップ 7 では、新しい`Graph`オブジェクトに行を追加し、`Graph`に反対する`Paragraphs`ページのコレクション。

#### Q: HTML 形式で見出しテキストを追加するにはどうすればよいですか?

 A: ステップ 8 で、`HtmlFragment`オブジェクトを作成し、そのコンテンツを目的の HTML テキストに設定してから、フラグメントを`Paragraphs`ページのコレクション。

#### Q: 複数の列を持つ FloatingBox を作成するにはどうすればよいですか?

 A: ステップ 9 で、`FloatingBox`複数の列と列間隔を持つオブジェクトを作成し、テキストの断片と行を追加します。`Paragraphs`のコレクション`FloatingBox`.

#### Q: PDF ドキュメントを保存するにはどうすればよいですか?

 A: ステップ 10 では、`Save`の方法`Document`物体。

#### Q: このチュートリアルの主なポイントは何ですか?

A: このチュートリアルに従うことで、Aspose.PDF for .NET を使用して複数列の PDF ドキュメントを作成する方法を学習しました。これは、構造化され整理されたレイアウトでコンテンツを表示する場合に役立ちます。