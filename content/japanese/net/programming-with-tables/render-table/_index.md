---
title: PDF ドキュメントで表をレンダリングする
linktitle: PDF ドキュメントで表をレンダリングする
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ドキュメントにテーブルを表示する方法を学習します。
type: docs
weight: 170
url: /ja/net/programming-with-tables/render-table/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントにテーブルを表示する方法を段階的に説明します。提供されている C# ソース コードについて説明し、実装方法を示します。

## ステップ1: ドキュメントの作成
まず、新しい PDF ドキュメントを作成します。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//新しいドキュメントを作成する
Document doc = new Document();
```

## ステップ2: ページの余白と向きを設定する
次に、ページの余白を設定し、向きを横向きに設定します。

```csharp
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo. Left = 37;
marginInfo. Right = 37;
marginInfo. Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;
```

## ステップ3: テーブルと列の作成
次に、テーブルを作成し、列の幅を設定しましょう。

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "50 100";
```

## ステップ4: 表に行とセルを追加する
次に、ループを使用してテーブルに行とセルを追加します。

```csharp
for (int i = 1; i <= 120; i++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. FixedRowHeight = 15;
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("Content 1"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
```

## ステップ5: ページにテーブルを追加する
次に、ドキュメント ページにテーブルを追加してみましょう。

```csharp
Page curPage = doc.Pages.Add();
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs. Add(table);
```

## ステップ6: 新しいページにテーブルを表示する
次に、新しいテーブルを作成し、「IsInNewPage」プロパティを「true」に設定して、新しいページにテーブルを表示します。

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table. ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
     Aspose.Pdf.Row row = table1.Rows.Add();
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
paragraphs. Add(table1);
```

## ステップ7: PDFを保存する
最後に、PDF ドキュメントを保存します。

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable displayed successfully on a page.\nFile saved at location: " + dataDir);
```

### Aspose.PDF for .NET を使用してテーブルをレンダリングするためのサンプル ソース コード

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo.Left = 37;
marginInfo.Right = 37;
marginInfo.Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "50 100";
//ページを追加しました。
Page curPage = doc.Pages.Add();
for (int i = 1; i <= 120; i++)
{
	Aspose.Pdf.Row row = table.Rows.Add();
	row.FixedRowHeight = 15;
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("Content 1"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs.Add(table);
/********************************************/
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table.ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
	Aspose.Pdf.Row row = table1.Rows.Add();
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
//表 1 を次のページに残しておきたいのですが...
paragraphs.Add(table1);
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable render successfully on a page.\nFile saved at " + dataDir);
```

## 結論
おめでとうございます。これで、Aspose.PDF for .NET を使用して PDF ドキュメントに表を表示する方法を学習しました。このステップ バイ ステップ ガイドでは、ドキュメントの作成、ページの余白と方向の設定、表の追加、新しいページでの表の表示方法について説明しました。これで、この知識を自分のプロジェクトに適用できます。

### PDF ドキュメントのレンダリング テーブルに関する FAQ

#### Q: セルの色を変更したり、境界線を追加したりするなど、テーブルの外観を変更するにはどうすればよいですか?

 A: テーブルの外観を変更するには、`Aspose.Pdf.Table`およびそのセルを設定します。たとえば、`BackgroundColor`セルのプロパティを設定すると背景色を変更できます。`Border`表または個々のセルのプロパティを変更して境界線を追加できます。さらに、表のコンテンツのフォント、テキストの色、配置をカスタマイズするには、`TextState`の`TextFragment`セルに追加されたオブジェクト。

#### Q: 表にヘッダーやフッターを追加できますか?

A: はい、表の先頭または末尾に追加の行を作成し、セルに適切なコンテンツを設定することで、表にヘッダーまたはフッターを追加できます。これらの特定の行に異なるスタイルまたはコンテンツを追加することで、表の残りのコンテンツとは独立してヘッダーまたはフッターをカスタマイズできます。

#### Q: ページ上のテーブルの位置を制御するにはどうすればよいですか?

A: ページ上の表の位置を制御するには、`MarginInfo`の`PageInfo`オブジェクト。`MarginInfo`ページの左、右、上、下の余白を設定することができ、表に使用できるスペースに影響します。`PositioningType`の財産`Aspose.Pdf.Table`ページのコンテンツ領域内での水平方向と垂直方向の配置を制御します。

#### Q: テーブルを Excel や CSV などの別のファイル形式でエクスポートできますか?

A: Aspose.PDF for .NET は、主に PDF ドキュメントの操作用に設計されています。PDF ドキュメントを画像または XPS としてエクスポートすることはできますが、Excel や CSV などの形式へのテーブルのエクスポートは直接サポートされていません。テーブル データを別のファイル形式にエクスポートするには、追加のライブラリまたはメソッドを使用して PDF コンテンツを目的の形式に変換する必要がある場合があります。

#### Q: 表のセルにハイパーリンクを追加するにはどうすればよいですか?

 A: 表のセルにハイパーリンクを追加するには、`Aspose.Pdf.WebHyperlink`クラスを使用してハイパーリンクを作成し、それをアンカーとして追加します`TextFragment`セル内。これにより、URL またはリンク ターゲットをセル内の特定のテキストまたはコンテンツに関連付け、クリック可能なハイパーリンクを作成できます。