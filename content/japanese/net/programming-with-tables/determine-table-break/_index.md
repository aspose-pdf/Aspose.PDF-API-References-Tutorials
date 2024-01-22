---
title: PDF ファイル内のテーブル ブレークを決定する
linktitle: PDF ファイル内のテーブル ブレークを決定する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内のテーブル区切りを判断する方法を学びます。
type: docs
weight: 60
url: /ja/net/programming-with-tables/determine-table-break/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイル内のテーブル区切りを決定する方法を学びます。 C#のソースコードをステップバイステップで解説していきます。このチュートリアルの最後には、表がページ余白を超えているかどうかを判断する方法がわかります。はじめましょう！

## ステップ 1: 環境をセットアップする
まず、Aspose.PDF for .NET を使用して C# 開発環境をセットアップしていることを確認します。参照をライブラリに追加し、必要な名前空間をインポートします。

## ステップ 2: PDF ドキュメントの作成
このステップでは、新しい`Document`PDF ドキュメントを表すオブジェクト。

```csharp
pdf-Document = new Document();
```

このドキュメントはセクションとテーブルを追加するために使用されます。

## ステップ 3: セクションとテーブルを追加する
次に、PDF ドキュメントにセクションを追加し、このセクション内にテーブルを作成します。

```csharp
Page page = pdf.Pages.Add();
Table table1 = new Table();
table1. Margin. Top = 300;
page.Paragraphs.Add(table1);
```

また、テーブルの上マージンを 300 ポイントに指定します。必要に応じてこの値を調整できます。

## ステップ 4: テーブルのセットアップ
このステップでは、列の幅や境界線などのテーブルのプロパティを構成します。

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

ここでは、テーブルの列の幅とセルの境界線を定義します。これらの値は好みに応じて調整できます。

## ステップ 5: テーブルに行とセルを追加する
次に、ループを使用してテーブルに行とセルを作成します。

```csharp
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
     Row row1 = table1.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
```

ここでは、テーブルに 17 行を作成し、各行に 3 つのセルを追加します。必要に応じてバックルを調整できます。

## ステップ 6: テーブル ブレークの決定
次に、ページの高さと表内のオブジェクトの合計の高さを比較して、表がページ余白を超えているかどうかを判断します。

```csharp
float PageHeight = (float)pdf.PageInfo.Height;
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

if ((PageHeight - TotalObjectsHeight) <= 10)
     Console.WriteLine("The height of the page - Height of objects < 10, the table will be truncated");
```

余白を考慮して、ページの高さとオブジェクトの合計の高さを計算します。差が 10 以下の場合、表はページ余白を超えています。

## ステップ 7: PDF ドキュメントを保存する
最後に、結果を含む PDF ドキュメントを保存します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
dataDir = dataDir + "DetermineTableBreak_out.pdf";
pdf.Save(dataDir);
Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

必ず正しいドキュメント ディレクトリを指定してください。結果の PDF ファイルは、決定されたテーブル区切りとともに保存されます。

### Aspose.PDF for .NET を使用したテーブル ブレークの決定のソース コード例

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//オブジェクト PDF クラスをインスタンス化する
Document pdf = new Document();
//PDF ドキュメント セクション コレクションにセクションを追加する
Aspose.Pdf.Page page = pdf.Pages.Add();
//テーブルオブジェクトをインスタンス化する
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.Margin.Top = 300;
//目的のセクションの段落コレクションに表を追加します
page.Paragraphs.Add(table1);
//テーブルの列幅で設定します
table1.ColumnWidths = "100 100 100";
//BorderInfo オブジェクトを使用してデフォルトのセル境界線を設定する
table1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
//別のカスタマイズされた BorderInfo オブジェクトを使用してテーブルの境界線を設定する
table1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
//MarginInfo オブジェクトを作成し、その左、下、右、上マージンを設定します。
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
//デフォルトのセルパディングを MarginInfo オブジェクトに設定します。
table1.DefaultCellPadding = margin;
//カウンタを 17 に増やすとテーブルが壊れます
//このページではこれ以上収容できないため
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
	//テーブルに行を作成し、その行にセルを作成します。
	Aspose.Pdf.Row row1 = table1.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
//ページの高さ情報を取得する
float PageHeight = (float)pdf.PageInfo.Height;
//ページの上下余白の合計高さ情報を取得し、
//テーブルの上のマージンとテーブルの高さ。
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

//ページの高さ、表の高さ、表の上のマージンおよびページの上部を表示します。
//そして下マージン情報
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

//ページ上部マージン + ページ下部マージンの合計を差し引くかどうかを確認します。
// + ページの高さからテーブルの上のマージンとテーブルの高さを差し引いた値
//10 より大きい (平均行は 10 より大きくなる可能性があります)
if ((PageHeight - TotalObjectsHeight) <= 10)
	//値が 10 未満の場合は、メッセージを表示します。
	//これは、別の行を配置できないことを示しており、新しい行を追加すると
	//列、テーブルが壊れます。それは行の高さの値によって異なります。
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
// PDF ドキュメントを保存する
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## 結論
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内のテーブル区切りを決定する方法を学びました。このステップバイステップ ガイドを使用して、独自の C# プロジェクトでテーブルがページ余白を超えているかどうかを確認できます。

### PDF ファイル内のテーブル区切りを決定するための FAQ

#### Q: PDF ドキュメント内の表の区切りを決定する目的は何ですか?

A: PDF 文書内の表の区切りを決定する目的は、表がページ余白を超えているかどうかを確認することです。これにより、テーブルのコンテンツが利用可能なページ スペース内に正しく表示されるようになります。テーブルの区切りを検出することで、コンテンツのオーバーフローを処理し、それに応じてテーブルのレイアウトを調整できます。

#### Q: テーブルの上マージンを調整するにはどうすればよいですか?

 A: 提供されている C# ソース コードでは、`table1.Margin.Top`財産。必要に応じて値を増減して、テーブルの上マージンを設定します。

#### Q: セルの色やフォント サイズなど、表の外観をカスタマイズできますか?

A: はい、Aspose.PDF for .NET が提供するさまざまなプロパティとメソッドを使用して、テーブルとそのセルの外観をカスタマイズできます。たとえば、セルの背景色、フォント サイズ、フォント ファミリー、テキストの配置などを変更できます。テーブルの外観をカスタマイズする方法の詳細については、公式ドキュメントを参照してください。

#### Q: 表がページ余白を超えるとどうなりますか?

A: 表がページの余白を超えると、コンテンツが切り詰められたり重なったりして、PDF ドキュメントが読みにくくなり、整理されなくなる可能性があります。テーブルの区切りを検出し、オーバーフローを処理することにより、コンテンツが利用可能なページ領域内に適切に表示されたままであることを保証できます。

#### Q: 同じ PDF ドキュメント内の複数の表の表の区切りを決定できますか?

A: はい、同じ PDF ドキュメント内の複数の表の表の区切りを決定できます。分析したいテーブルごとに手順を繰り返し、コンテンツのオーバーフローを防ぐために必要に応じてテーブルのレイアウトを調整します。