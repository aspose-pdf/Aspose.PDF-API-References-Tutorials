---
title: PDF ドキュメントに繰り返し列を追加する
linktitle: PDF ドキュメントに繰り返し列を追加する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ドキュメントに繰り返し列を追加する方法を学習します。
type: docs
weight: 20
url: /ja/net/programming-with-tables/add-repeating-column/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントに繰り返し列を追加する方法を学習します。C# のソース コードをステップごとに説明します。このチュートリアルの最後には、PDF ドキュメントに繰り返し列を含むテーブルを作成する方法がわかります。さあ、始めましょう!

## ステップ1: 環境の設定
まず、Aspose.PDF for .NET を使用して C# 開発環境が設定されていることを確認します。ライブラリへの参照を追加し、必要な名前空間をインポートします。

## ステップ2: PDFドキュメントの作成
このステップでは、新しい PDF ドキュメントを作成します。

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

コンテンツを追加できる空の PDF ドキュメントを作成しました。

## ステップ3: テーブルの作成
このステップではメインテーブルを作成します（`outerTable`) とネストされたテーブル (`mytable`) が列内で繰り返されます。

```csharp
Table outerTable = new Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

Table mytable = new Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

列幅やネストされた表の区切りモードなどの表のプロパティを指定しました。

## ステップ4: ドキュメントに表を追加する
次に、作成した表を PDF ドキュメントに追加します。

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);
```

まずメインテーブルを追加します（`outerTable`) を PDF ドキュメントに追加します。次に、ネストされたテーブル (`mytable` ）をメインテーブルのセルに段落として表示します。また、繰り返し列の数も指定します。`mytable` (この例では 5 列)。

## ステップ5: ヘッダーと行を追加する
次に、テーブルにヘッダーと行を追加します。

```csharp
Row headerRow = mytable.Rows.Add();
headerRow.Cells.Add("header 1");
headerRow.Cells.Add("header 2");
headerRow.Cells.Add("header 3");
// ...
//ここに他のヘッダーを追加します

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
     Row row1 = mytable.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
     // ...
     //ここに他の列を追加します
}
```

まず、表の最初の行にヘッダーを追加します（`headerRow`）。次に、ループからのデータ行を追加します。この例では、6 行のデータを追加します。

## ステップ6: PDF文書を保存する
最後に、PDF ドキュメントを指定されたファイルに保存します。

```csharp
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
doc.Save(outFile);
```

出力 PDF ファイルを保存するには、正しいディレクトリとファイル名を指定してください。

### Aspose.PDF for .NET を使用して繰り返し列を追加するためのサンプル ソース コード

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

string outFile = dataDir + "AddRepeatingColumn_out.pdf";
//新しいドキュメントを作成する
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();

//ページ全体を占める外部テーブルをインスタンス化する
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

//同じページ内で改ページするouterTable内にネストされるテーブルオブジェクトをインスタンス化します。
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;

//ページの段落にouterTableを追加する
//mytableをouterTableに追加する
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);

//ヘッダー行を追加
Aspose.Pdf.Row row = mytable.Rows.Add();
row.Cells.Add("header 1");
row.Cells.Add("header 2");
row.Cells.Add("header 3");
row.Cells.Add("header 4");
row.Cells.Add("header 5");
row.Cells.Add("header 6");
row.Cells.Add("header 7");
row.Cells.Add("header 11");
row.Cells.Add("header 12");
row.Cells.Add("header 13");
row.Cells.Add("header 14");
row.Cells.Add("header 15");
row.Cells.Add("header 16");
row.Cells.Add("header 17");

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)

{
	//表に行を作成し、行にセルを作成します
	Aspose.Pdf.Row row1 = mytable.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 4");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 5");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 6");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 7");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 11");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 12");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 13");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 14");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 15");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 16");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 17");
}
doc.Save(outFile);
```

## 結論
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントに繰り返し列を追加する方法を学習しました。このステップ バイ ステップ ガイドを使用して、独自の C# プロジェクトで繰り返し列を含むテーブルを作成できます。

### PDF ドキュメントに繰り返し列を追加する方法に関する FAQ

#### Q: ネストされたテーブル内の繰り返し列の数をカスタマイズできますか?

 A: はい、ネストされたテーブル内の繰り返し列の数をカスタマイズできます。提供された例では、`mytable.RepeatingColumnsCount = 5;`つまり、5 つの列が繰り返されることになります。この値は任意の数値に変更できます。

#### Q: ネストされたテーブルに動的に行を追加することは可能ですか?

A: はい、チュートリアルで示したのと同じ方法で、ネストされたテーブルに動的に行を追加できます。ループやその他のロジックを使用して、データに基づいて行を追加できます。

#### Q: テーブルとそのセルにスタイルと書式を適用できますか?

A: はい、Aspose.PDF for .NET を使用して、テーブルとそのセルにスタイルと書式を適用できます。ライブラリには、テーブルとそのコンテンツの外観をカスタマイズするためのさまざまなプロパティとメソッドが用意されています。

#### Q: Aspose.PDF for .NET は .NET Core と互換性がありますか?

A: はい、Aspose.PDF for .NET は .NET Core と互換性があります。.NET Framework アプリケーションと .NET Core アプリケーションの両方で使用できます。

#### Q: この方法を使用して、既存の PDF ドキュメントに繰り返し列を追加できますか?

A: はい、この方法を使用して、既存の PDF ドキュメントに繰り返し列を追加できます。Aspose.PDF for .NET を使用して既存のドキュメントを読み込み、同じ手順に従って繰り返し列を作成して追加するだけです。