---
title: PDF ドキュメントに繰り返し列を追加
linktitle: PDF ドキュメントに繰り返し列を追加
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ドキュメントに繰り返し列を追加する方法を学びます。
type: docs
weight: 20
url: /ja/net/programming-with-tables/add-repeating-column/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントに繰り返し列を追加する方法を学習します。 C#のソースコードをステップバイステップで解説していきます。このチュートリアルの最後には、PDF ドキュメント内に繰り返し列を含む表を作成する方法がわかります。はじめましょう！

## ステップ 1: 環境をセットアップする
まず、Aspose.PDF for .NET を使用して C# 開発環境をセットアップしていることを確認します。参照をライブラリに追加し、必要な名前空間をインポートします。

## ステップ 2: PDF ドキュメントの作成
このステップでは、新しい PDF ドキュメントを作成します。

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

コンテンツを追加できる空の PDF ドキュメントを作成しました。

## ステップ 3: テーブルの作成
このステップでは、メインテーブル (`outerTable`) とネストされたテーブル (`mytable`) この列で繰り返されます。

```csharp
Table outerTable = new Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

Table mytable = new Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

列幅やネストしたテーブルのブレーク モードなどのテーブル プロパティを指定しました。

## ステップ 4: ドキュメントに表を追加する
次に、作成した表を PDF ドキュメントに追加します。

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);
```

まずメインテーブルを追加します(`outerTable`) PDF ドキュメントに変換します。次に、ネストされたテーブルを追加します (`mytable` ) メインテーブルのセル内の段落として。また、繰り返される列の数も指定します。`mytable` (この例では 5 列)。

## ステップ 5: ヘッダーと行を追加する
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
     //他の列をここに追加します
}
```

まず、テーブルの最初の行にヘッダーを追加します (`headerRow`）。次に、ループからデータの行を追加します。この例では、6 行のデータを追加します。

## ステップ 6: PDF ドキュメントを保存する
最後に、PDF ドキュメントを指定したファイルに保存します。

```csharp
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
doc.Save(outFile);
```

出力 PDF ファイルを保存するには、正しいディレクトリとファイル名を指定してください。

### Aspose.PDF for .NET を使用して繰り返し列を追加するソース コードの例

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

string outFile = dataDir + "AddRepeatingColumn_out.pdf";
//新しいドキュメントを作成する
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();

//ページ全体を占める外部テーブルをインスタンス化します。
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

//同じページ内で分割される、outerTable 内にネストされるテーブル オブジェクトをインスタンス化します。
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;

// externalTable をページ段落に追加します。
// mytableをouterTableに追加
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
	//テーブルに行を作成し、その行にセルを作成します。
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
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントに繰り返し列を追加する方法を学びました。このステップバイステップ ガイドを使用して、独自の C# プロジェクトで繰り返し列を含むテーブルを作成できます。

### PDF 文書に繰り返し列を追加する場合の FAQ

#### Q: ネストされたテーブルで繰り返される列の数をカスタマイズできますか?

 A: はい、ネストしたテーブルで繰り返される列の数をカスタマイズできます。提供された例では、次のように設定します`mytable.RepeatingColumnsCount = 5;`これは、5 つの繰り返し列があることを意味します。この値は任意の数値に変更できます。

#### Q: ネストされたテーブルに動的に行を追加することは可能ですか?

A: はい、チュートリアルで示したのと同じ方法で、ネストされたテーブルに動的に行を追加できます。ループまたはその他のロジックを使用して、データに基づいて行を追加できます。

#### Q: テーブルとそのセルにスタイルと書式設定を適用できますか?

A: はい、Aspose.PDF for .NET を使用して、テーブルとそのセルにスタイルと書式設定を適用できます。このライブラリは、テーブルとその内容の外観をカスタマイズするためのさまざまなプロパティとメソッドを提供します。

#### Q: Aspose.PDF for .NET は .NET Core と互換性がありますか?

A: はい、Aspose.PDF for .NET は .NET Core と互換性があります。 .NET Framework アプリケーションと .NET Core アプリケーションの両方で使用できます。

#### Q: このアプローチを使用して、既存の PDF ドキュメントに繰り返し列を追加できますか?

A: はい、この方法を使用して、既存の PDF ドキュメントに繰り返し列を追加できます。 Aspose.PDF for .NET を使用して既存のドキュメントをロードし、同じ手順に従って繰り返し列を作成して追加するだけです。