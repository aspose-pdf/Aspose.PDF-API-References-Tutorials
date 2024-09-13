---
title: PDF ファイル内の表の区切りを決定する
linktitle: PDF ファイル内の表の区切りを決定する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内の表の区切りを決定する方法を学習します。
type: docs
weight: 60
url: /ja/net/programming-with-tables/determine-table-break/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイル内の表の区切りを決定する方法を学習します。C# のソース コードをステップごとに説明します。このチュートリアルの最後には、表がページ余白を超えているかどうかを判断する方法がわかります。さあ、始めましょう!

## ステップ1: 環境の設定
まず、Aspose.PDF for .NET を使用して C# 開発環境が設定されていることを確認します。ライブラリへの参照を追加し、必要な名前空間をインポートします。

## ステップ2: PDFドキュメントの作成
このステップでは、新しい`Document` PDF ドキュメントを表すオブジェクト。

```csharp
pdf-Document = new Document();
```

このドキュメントは、セクションと表を追加するために使用されます。

## ステップ3: セクションとテーブルを追加する
ここで、PDF ドキュメントにセクションを追加し、このセクション内に表を作成します。

```csharp
Page page = pdf.Pages.Add();
Table table1 = new Table();
table1. Margin. Top = 300;
page.Paragraphs.Add(table1);
```

また、テーブルの上部余白を 300 ポイントに指定します。この値は必要に応じて調整できます。

## ステップ4: テーブルの設定
この手順では、列の幅や境界線などの表のプロパティを構成します。

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

ここでは、表の列の幅とセルの境界線を定義します。これらの値は好みに応じて調整できます。

## ステップ5: 表に行とセルを追加する
ここで、ループを使用してテーブルに行とセルを作成します。

```csharp
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
     Row row1 = table1.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
```

ここでは、表に 17 行を作成し、各行に 3 つのセルを追加します。必要に応じてバックルを調整できます。

## ステップ6: テーブル区切りの決定
ここで、ページの高さと表内のオブジェクトの合計高さを比較して、表がページの余白を超えているかどうかを判断します。

```csharp
float PageHeight = (float)pdf.PageInfo.Height;
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

if ((PageHeight - TotalObjectsHeight) <= 10)
     Console.WriteLine("The height of the page - Height of objects < 10, the table will be truncated");
```

ページの高さとオブジェクトの合計の高さを余白を考慮して計算します。差が 10 以下の場合、表はページの余白を超えています。

## ステップ7: PDF文書を保存する
最後に、結果を PDF ドキュメントに保存します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
dataDir = dataDir + "DetermineTableBreak_out.pdf";
pdf.Save(dataDir);
Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

必ず正しいドキュメント ディレクトリを指定してください。結果の PDF ファイルは、決定された表区切りとともに保存されます。

### Aspose.PDF for .NET を使用して表の区切りを決定するためのサンプル ソース コード

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//オブジェクトPDFクラスをインスタンス化する
Document pdf = new Document();
//PDFドキュメントのセクションコレクションにセクションを追加する
Aspose.Pdf.Page page = pdf.Pages.Add();
//テーブルオブジェクトをインスタンス化する
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.Margin.Top = 300;
//希望するセクションの段落コレクションに表を追加します
page.Paragraphs.Add(table1);
//テーブルの列幅を設定する
table1.ColumnWidths = "100 100 100";
// BorderInfo オブジェクトを使用してデフォルトのセル境界線を設定する
table1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
//別のカスタマイズされたBorderInfoオブジェクトを使用して表の境界線を設定する
table1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
//MarginInfoオブジェクトを作成し、左、下、右、上の余白を設定します。
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
//デフォルトのセルパディングをMarginInfoオブジェクトに設定する
table1.DefaultCellPadding = margin;
//カウンターを17に増やすとテーブルが壊れます
//このページではこれ以上収容できないため
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
	//表に行を作成し、行にセルを作成します
	Aspose.Pdf.Row row1 = table1.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
//ページの高さ情報を取得する
float PageHeight = (float)pdf.PageInfo.Height;
//ページの上部と下部の余白の合計の高さ情報を取得します。
//テーブル上部の余白とテーブルの高さ。
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

//ページの高さ、表の高さ、表の上余白、ページの上部を表示します。
//下部余白情報
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

//ページ上部の余白とページ下部の余白の合計を差し引くかどうかを確認します
// テーブル上部の余白とテーブルの高さ（ページの高さから）
// 10 より多い (平均行は 10 より大きくなる場合があります)
if ((PageHeight - TotalObjectsHeight) <= 10)
	//値が 10 未満の場合は、メッセージを表示します。
	//これは、別の行を配置できないことを示し、新しい行を追加すると
	//行、テーブルは分割されます。行の高さの値によって異なります。
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
// PDF文書を保存する
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## 結論
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内の表の区切りを決定する方法を学習しました。このステップ バイ ステップ ガイドを使用して、独自の C# プロジェクトで表がページ余白を超えているかどうかを確認できます。

### PDF ファイル内の表の区切りを決定するための FAQ

#### Q: PDF ドキュメントで表の区切りを決定する目的は何ですか?

A: PDF ドキュメントで表の区切りを決定する目的は、表がページ余白を超えていないかどうかを確認することです。これにより、表の内容が使用可能なページ スペース内に正しく表示されるようになります。表の区切りを検出することで、コンテンツのオーバーフローを処理し、それに応じて表のレイアウトを調整できます。

#### Q: 表の上余白を調整するにはどうすればよいですか?

 A: 提供されているC#ソースコードでは、`table1.Margin.Top`プロパティ。必要に応じて値を増減して、テーブルの上余白を設定します。

#### Q: セルの色やフォント サイズなど、テーブルの外観をカスタマイズできますか?

A: はい、Aspose.PDF for .NET が提供するさまざまなプロパティとメソッドを使用して、テーブルとそのセルの外観をカスタマイズできます。たとえば、セルの背景色、フォント サイズ、フォント ファミリ、テキストの配置などを変更できます。テーブルの外観をカスタマイズする方法の詳細については、公式ドキュメントを参照してください。

#### Q: 表がページの余白を超えた場合はどうなりますか?

A: 表がページ余白を超えると、コンテンツが切り捨てられたり重なったりして、PDF ドキュメントの読みにくさと整理が悪くなる可能性があります。表の区切りを検出してオーバーフローを処理することで、使用可能なページ領域内にコンテンツが適切に表示されるようになります。

#### Q: 同じ PDF ドキュメント内の複数の表の表区切りを指定できますか?

A: はい、同じ PDF ドキュメント内の複数の表の表区切りを決定できます。分析する表ごとに手順を繰り返し、必要に応じて表のレイアウトを調整して、コンテンツのオーバーフローを防止します。