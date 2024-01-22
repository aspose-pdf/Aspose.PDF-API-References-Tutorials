---
title: PDF ドキュメントのテーブルをレンダリング
linktitle: PDF ドキュメントのテーブルをレンダリング
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ドキュメントに表を表示する方法を学びます。
type: docs
weight: 170
url: /ja/net/programming-with-tables/render-table/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントに表を表示する方法を段階的に説明します。提供されている C# ソース コードについて説明し、実装方法を示します。

## ステップ 1: ドキュメントの作成
まず、新しい PDF ドキュメントを作成します。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//新しいドキュメントを作成する
Document doc = new Document();
```

## ステップ 2: ページの余白と向きを構成する
次に、ページの余白を構成し、方向を横向きモードに設定します。

```csharp
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo. Left = 37;
marginInfo. Right = 37;
marginInfo. Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;
```

## ステップ 3: テーブルと列の作成
次に、テーブルを作成して列幅を設定しましょう。

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "50 100";
```

## ステップ 4: テーブルに行とセルを追加する
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

## ステップ 5: ページにテーブルを追加する
次に、テーブルをドキュメント ページに追加しましょう。

```csharp
Page curPage = doc.Pages.Add();
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs. Add(table);
```

## ステップ 6: 新しいページに表を表示する
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

## ステップ 7: PDF を保存する
最後に、PDF ドキュメントを保存します。

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable displayed successfully on a page.\nFile saved at location: " + dataDir);
```

### Aspose.PDF for .NET を使用したレンダー テーブルのソース コード例

```csharp
//ドキュメントディレクトリへのパス。
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
おめでとうございます！ Aspose.PDF for .NET を使用して PDF ドキュメント内に表を表示する方法を学習しました。このステップバイステップのガイドでは、ドキュメントの作成、ページの余白と方向の設定、表の追加、新しいページに表を表示する方法を説明しました。この知識を自分のプロジェクトに適用できるようになりました。

### PDF ドキュメントのレンダリング テーブルに関する FAQ

#### Q: セルの色の変更や枠線の追加など、表の外観を変更するにはどうすればよいですか?

A: テーブルの外観を変更するには、テーブルのさまざまなプロパティを設定します。`Aspose.Pdf.Table`そしてその細胞。たとえば、次のように設定できます。`BackgroundColor`セルのプロパティを使用して背景色を変更します。を設定することもできます`Border`テーブルまたは個々のセルのプロパティを使用して境界線を追加します。さらに、テーブルの内容のフォント、テキストの色、配置をカスタマイズできます。`TextState`の`TextFragment`オブジェクトがセルに追加されました。

#### Q: テーブルにヘッダーまたはフッターを追加できますか?

A: はい、テーブルの先頭または末尾に追加の行を作成し、セルに適切なコンテンツを設定することで、テーブルにヘッダーまたはフッターを追加できます。これらの特定の行にさまざまなスタイルやコンテンツを追加することで、ヘッダーまたはフッターをテーブルの残りのコンテンツとは別にカスタマイズできます。

#### Q: ページ上の表の位置を制御するにはどうすればよいですか?

 A: ページ上の表の位置を制御するには、`MarginInfo`の`PageInfo`物体。の`MarginInfo`ページの左、右、上、下の余白を設定できます。これは表に使用できるスペースに影響します。を使用することもできます。`PositioningType`の財産`Aspose.Pdf.Table`ページのコンテンツ領域内での水平方向と垂直方向の配置を制御します。

#### Q: テーブルを Excel や CSV などの別のファイル形式にエクスポートできますか?

A: Aspose.PDF for .NET は主に PDF ドキュメントを操作するために設計されています。 PDF ドキュメントを画像または XPS としてエクスポートできますが、テーブルを Excel や CSV などの形式にエクスポートすることは直接サポートされていません。テーブル データを別のファイル形式にエクスポートするには、追加のライブラリまたはメソッドを使用して PDF コンテンツを目的の形式に変換する必要がある場合があります。

#### Q: 表のセルにハイパーリンクを追加するにはどうすればよいですか?

 A: 表のセルにハイパーリンクを追加するには、`Aspose.Pdf.WebHyperlink`クラスを使用してハイパーリンクを作成し、それをアンカーとして`TextFragment`細胞の中。これにより、URL またはリンク ターゲットをセル内の特定のテキストまたはコンテンツに関連付け、クリック可能なハイパーリンクを作成できます。