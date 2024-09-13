---
title: PDF ファイルに SVG オブジェクトを追加する
linktitle: PDF ファイルに SVG オブジェクトを追加する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、PDF ファイルに SVG オブジェクトを簡単に追加できます。
type: docs
weight: 30
url: /ja/net/programming-with-tables/add-svg-object/
---
このチュートリアルでは、Aspose.PDF for .NET ライブラリを使用して PDF ファイルに SVG オブジェクトを追加する方法を学習します。SVG (Scalable Vector Graphics) は、品質を損なうことなく簡単に拡大縮小できるベクター グラフィックスの一般的な形式です。Aspose.PDF を使用すると、プログラムによって PDF ドキュメントに SVG オブジェクトを追加できます。

## 要件

始める前に、以下のものを用意してください。

- Visual Studioがインストールされている
- Aspose.PDF for .NET ライブラリがインストールされている

## ステップ1: 環境を設定する

まず、Visual Studio で新しい C# プロジェクトを作成して環境を設定しましょう。Visual Studio を開き、次の手順に従います。

1. 「ファイル」>「新規」>「プロジェクト」をクリックして、新しいプロジェクトを作成します。
2. 設定に応じて、「コンソール アプリ (.NET Framework)」または「コンソール アプリ (.NET Core)」テンプレートを選択します。
3. プロジェクトに適切な名前と場所を選択し、「作成」をクリックします。

## ステップ2: ドキュメントと画像オブジェクトを作成する

このステップでは、PDF ドキュメントと SVG 画像に必要なオブジェクトを作成します。プロジェクトの C# ファイルを開き、次のコードを追加します。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//インスタントドキュメントオブジェクト
Document doc = new Document();
//イメージインスタンスを作成する
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```

## ステップ3: 画像のプロパティを設定する

次に、SVG 画像のプロパティを設定します。ファイルの種類を SVG、SVG ファイルへのパス、画像のサイズを指定します。前の手順の後に次のコードを追加します。

```csharp
//画像タイプをSVGに設定する
img.FileType = Aspose.Pdf.ImageFileType.Svg;
//ソースファイルのパス
img.File = dataDir + "SVGToPDF.svg";
//画像インスタンスの幅を設定する
img. FixWidth = 50;
//画像インスタンスの高さを設定する
img.FixHeight = 50;
```

## ステップ4: テーブルの作成と構成

次に、テーブル オブジェクトを作成し、列の幅を設定します。幅がそれぞれ 100 単位の 2 つの列を持つテーブルを作成します。次のコードを追加します。

```csharp
//インスタンステーブルを作成する
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
//表のセルの幅を設定する
table. ColumnWidths = "100 100";
```

## ステップ5: 表にセルを追加する

このステップでは、テーブルに行とセルを追加します。各行はテーブル内の水平行を表し、セルは行に追加されます。次のコードを追加します。

```csharp
//行オブジェクトを作成し、テーブルインスタンスに追加する
Aspose.Pdf.Row row = table.Rows.Add();
//セルオブジェクトを作成し、行インスタンスに追加する
Aspose.Pdf.Cell cell = row.Cells.Add();
```

## ステップ6: セルにテキストと画像を追加する

次に、テーブルのセルにテキストと SVG 画像を追加しましょう。最初のセルに「最初のセル」というテキストを追加し、2 番目のセルに SVG 画像を追加します。次のコードを追加します。

```csharp
//セルオブジェクトの段落コレクションにテキストフラグメントを追加する
cell.Paragraphs.Add(new TextFragment("First cell"));
//行オブジェクトに別のセルを追加する
cell = row. Cells. Add();
//最近追加されたセルインスタンスの段落コレクションに SVG 画像を追加します。
cell.Paragraphs.Add(img);
```

## ステップ7: ドキュメントにページを作成して追加する

次に、ページ オブジェクトを作成してドキュメントに追加します。表はページの段落コレクションに追加されます。次のコードを追加します。

```csharp
//ページオブジェクトを作成し、ドキュメントインスタンスのページコレクションに追加します。
Page page = doc.Pages.Add();
//ページオブジェクトの段落コレクションに表を追加する
page.Paragraphs.Add(table);
```

## ステップ8: PDFファイルを保存する

最後に、PDF ファイルを指定された場所に保存します。次のコードを追加します。

```csharp
dataDir = dataDir + "AddSVGObject_out.pdf";
// PDFファイルを保存
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);
```

### Aspose.PDF for .NET を使用して SVG オブジェクトを追加するためのサンプル ソース コード

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Documentオブジェクトをインスタンス化する
Document doc = new Document();
//イメージインスタンスを作成する
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
//画像タイプをSVGに設定する
img.FileType = Aspose.Pdf.ImageFileType.Svg;
//ソースファイルのパス
img.File = dataDir + "SVGToPDF.svg";
//画像インスタンスの幅を設定する
img.FixWidth = 50;
//画像インスタンスの高さを設定する
img.FixHeight = 50;
//テーブルインスタンスを作成する
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
//表のセルの幅を設定する
table.ColumnWidths = "100 100";
//行オブジェクトを作成し、テーブルインスタンスに追加する
Aspose.Pdf.Row row = table.Rows.Add();
//セルオブジェクトを作成し、行インスタンスに追加する
Aspose.Pdf.Cell cell = row.Cells.Add();
//セルオブジェクトの段落コレクションにテキストフラグメントを追加する
cell.Paragraphs.Add(new TextFragment("First cell"));
//行オブジェクトに別のセルを追加する
cell = row.Cells.Add();
//最近追加されたセルインスタンスの段落コレクションに SVG 画像を追加します。
cell.Paragraphs.Add(img);
//ページオブジェクトを作成し、ドキュメントインスタンスのページコレクションに追加します。
Page page = doc.Pages.Add();
//ページオブジェクトの段落コレクションに表を追加する
page.Paragraphs.Add(table);

dataDir = dataDir + "AddSVGObject_out.pdf";
// PDFファイルを保存
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);            
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET ライブラリを使用して SVG オブジェクトを PDF ファイルに追加する方法を学習しました。ドキュメントの作成、環境の設定、テーブル セルへの SVG 画像の追加、PDF ファイルの保存のプロセスをステップごとに説明しました。これで、プログラムによって SVG オブジェクトを PDF ドキュメントに組み込むことができます。

### PDF ファイルに SVG オブジェクトを追加する場合の FAQ

#### Q: PDF ドキュメントに複数の SVG オブジェクトを追加できますか?

 A: はい、PDF文書に複数のSVGオブジェクトを追加できます。追加オブジェクトを作成して設定するだけで、`Aspose.Pdf.Image`追加する SVG 画像ごとにインスタンスを作成し、それらを PDF ドキュメント内の目的の表セルまたは段落に追加します。

#### Q: テーブル セル内の SVG 画像のサイズと位置を調整するにはどうすればよいですか?

 A: 表のセル内のSVG画像のサイズと位置を調整するには、`FixWidth`そして`FixHeight`の特性`Aspose.Pdf.Image`インスタンス。他のプロパティも使用できます。`HorizontalAlignment`そして`VerticalAlignment`表セルの位置を制御します。

#### Q: 同じテーブルセル内の SVG 画像の横にテキストを追加することは可能ですか?

 A: はい、同じ表のセルにSVG画像と一緒にテキストを追加することができます。`cell.Paragraphs.Add(new TextFragment("Your Text Here"));` SVG 画像とともにセルにテキストを追加する方法。

#### Q: SVG 画像にハイパーリンクを追加できますか?

 A: はい、SVG画像にハイパーリンクを追加するには、`Hyperlink`の財産`Aspose.Pdf.Image`インスタンス。画像をクリック可能にするためのハイパーリンク URL またはアクションを設定します。

#### Q: Aspose.PDF for .NET は .NET Core 3.1 以降のバージョンと互換性がありますか?

A: はい、Aspose.PDF for .NET は .NET Core 3.1 以降のバージョンと互換性があります。.NET Framework アプリケーションと .NET Core アプリケーションの両方で使用できます。