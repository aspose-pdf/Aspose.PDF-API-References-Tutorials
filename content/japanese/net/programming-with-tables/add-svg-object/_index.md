---
title: PDF ファイルに SVG オブジェクトを追加
linktitle: PDF ファイルに SVG オブジェクトを追加
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、PDF ファイルに SVG オブジェクトを簡単に追加します。
type: docs
weight: 30
url: /ja/net/programming-with-tables/add-svg-object/
---
このチュートリアルでは、Aspose.PDF for .NET ライブラリを使用して PDF ファイルに SVG オブジェクトを追加する方法を学びます。 SVG (Scalable Vector Graphics) は、品質を損なうことなく簡単に拡大縮小できるベクター グラフィックスの一般的な形式です。 Aspose.PDF を使用すると、SVG オブジェクトをプログラムで PDF ドキュメントに追加できます。

## 要件

始める前に、以下のものがあることを確認してください。

- Visual Studioがインストールされている
- Aspose.PDF for .NET ライブラリがインストールされている

## ステップ 1: 環境をセットアップする

まず、Visual Studio で新しい C# プロジェクトを作成して環境をセットアップしましょう。 Visual Studio を開き、次の手順に従います。

1. 「ファイル」>「新規」>「プロジェクト」をクリックして新しいプロジェクトを作成します。
2. 設定に応じて、「コンソール アプリ (.NET Framework)」または「コンソール アプリ (.NET Core)」テンプレートを選択します。
3. プロジェクトに適切な名前と場所を選択し、[作成] をクリックします。

## ステップ 2: ドキュメントおよび画像オブジェクトを作成する

このステップでは、PDF ドキュメントと SVG 画像に必要なオブジェクトを作成します。プロジェクトの C# ファイルを開き、次のコードを追加します。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//インスタントドキュメントオブジェクト
Document doc = new Document();
//イメージインスタンスを作成する
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```

## ステップ 3: 画像のプロパティを設定する

次に、SVG 画像のプロパティを設定します。ファイルの種類を SVG、SVG ファイルへのパス、画像のサイズを指定します。前の手順の後に次のコードを追加します。

```csharp
//画像タイプをSVGとして設定します
img.FileType = Aspose.Pdf.ImageFileType.Svg;
//ソースファイルのパス
img.File = dataDir + "SVGToPDF.svg";
//画像インスタンスの幅を設定する
img. FixWidth = 50;
//画像インスタンスの高さを設定する
img.FixHeight = 50;
```

## ステップ 4: テーブルの作成と構成

次に、テーブル オブジェクトを作成し、列幅を設定しましょう。それぞれの幅が 100 単位の 2 つの列を持つテーブルを作成します。次のコードを追加します。

```csharp
//インスタンステーブルの作成
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
//表のセルの幅を設定する
table. ColumnWidths = "100 100";
```

## ステップ 5: テーブルにセルを追加する

このステップでは、テーブルに行とセルを追加します。各行はテーブル内の水平行を表し、セルが行に追加されます。次のコードを追加します。

```csharp
//行オブジェクトを作成し、テーブルインスタンスに追加します。
Aspose.Pdf.Row row = table.Rows.Add();
//セルオブジェクトを作成し、行インスタンスに追加します。
Aspose.Pdf.Cell cell = row.Cells.Add();
```

## ステップ 6: セルにテキストと画像を追加する

次に、表のセルにテキストと SVG 画像を追加しましょう。最初のセルに「最初のセル」というテキストを追加し、2 番目のセルに SVG 画像を追加します。次のコードを追加します。

```csharp
//セルオブジェクトの段落コレクションにテキストフラグメントを追加します。
cell.Paragraphs.Add(new TextFragment("First cell"));
//行オブジェクトに別のセルを追加
cell = row. Cells. Add();
//最近追加されたセル インスタンスの段落コレクションに SVG 画像を追加します
cell.Paragraphs.Add(img);
```

## ステップ 7: ページを作成してドキュメントに追加する

次に、ページ オブジェクトを作成してドキュメントに追加しましょう。表がページの段落コレクションに追加されます。次のコードを追加します。

```csharp
//ページ オブジェクトを作成し、ドキュメント インスタンスのページ コレクションに追加します。
Page page = doc.Pages.Add();
//ページオブジェクトの段落コレクションにテーブルを追加します
page.Paragraphs.Add(table);
```

## ステップ 8: PDF ファイルを保存する

最後に、PDF ファイルを指定した場所に保存します。次のコードを追加します。

```csharp
dataDir = dataDir + "AddSVGObject_out.pdf";
//PDFファイルを保存する
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);
```

### Aspose.PDF for .NET を使用して SVG オブジェクトを追加するソース コードの例

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Documentオブジェクトをインスタンス化する
Document doc = new Document();
//イメージインスタンスを作成する
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
//画像タイプをSVGとして設定します
img.FileType = Aspose.Pdf.ImageFileType.Svg;
//ソースファイルのパス
img.File = dataDir + "SVGToPDF.svg";
//画像インスタンスの幅を設定する
img.FixWidth = 50;
//画像インスタンスの高さを設定する
img.FixHeight = 50;
//テーブルインスタンスの作成
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
//表のセルの幅を設定する
table.ColumnWidths = "100 100";
//行オブジェクトを作成し、テーブルインスタンスに追加します。
Aspose.Pdf.Row row = table.Rows.Add();
//セルオブジェクトを作成し、行インスタンスに追加します。
Aspose.Pdf.Cell cell = row.Cells.Add();
//セルオブジェクトの段落コレクションにテキストフラグメントを追加します。
cell.Paragraphs.Add(new TextFragment("First cell"));
//行オブジェクトに別のセルを追加
cell = row.Cells.Add();
//最近追加されたセル インスタンスの段落コレクションに SVG 画像を追加します
cell.Paragraphs.Add(img);
//ページ オブジェクトを作成し、ドキュメント インスタンスのページ コレクションに追加します。
Page page = doc.Pages.Add();
//ページオブジェクトの段落コレクションにテーブルを追加します
page.Paragraphs.Add(table);

dataDir = dataDir + "AddSVGObject_out.pdf";
//PDFファイルを保存する
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);            
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET ライブラリを使用して SVG オブジェクトを PDF ファイルに追加する方法を学習しました。ドキュメントの作成、環境のセットアップ、表のセルへの SVG 画像の追加、PDF ファイルの保存という段階的なプロセスについて説明しました。 SVG オブジェクトをプログラムで PDF ドキュメントに組み込むことができるようになりました。

### PDF ファイルに SVG オブジェクトを追加するための FAQ

#### Q: 複数の SVG オブジェクトを PDF ドキュメントに追加できますか?

 A: はい、複数の SVG オブジェクトを PDF ドキュメントに追加できます。追加の作成と構成を行うだけです`Aspose.Pdf.Image`追加する各 SVG 画像のインスタンスを作成し、PDF ドキュメント内の目的の表のセルまたは段落に追加します。

#### Q: 表のセル内の SVG 画像のサイズと位置を調整するにはどうすればよいですか?

 A: 表のセル内の SVG 画像のサイズと位置を調整するには、`FixWidth`そして`FixHeight`のプロパティ`Aspose.Pdf.Image`実例。次のような他のプロパティを使用することもできます`HorizontalAlignment`そして`VerticalAlignment`表のセルの位置を制御します。

#### Q: 同じ表のセル内で SVG 画像の横にテキストを追加することはできますか?

 A: はい、同じ表のセル内で SVG 画像の横にテキストを追加することができます。使用できます`cell.Paragraphs.Add(new TextFragment("Your Text Here"));`SVG 画像とともにテキストをセルに追加するメソッド。

#### Q: SVG 画像にハイパーリンクを追加できますか?

 A: はい、次のコマンドを使用して SVG 画像にハイパーリンクを追加できます。`Hyperlink`の財産`Aspose.Pdf.Image`実例。画像をクリックできるようにするハイパーリンク URL またはアクションを設定します。

#### Q: Aspose.PDF for .NET は .NET Core 3.1 以降のバージョンと互換性がありますか?

A: はい、Aspose.PDF for .NET は .NET Core 3.1 以降のバージョンと互換性があります。 .NET Framework アプリケーションと .NET Core アプリケーションの両方で使用できます。