---
title: PDF ファイルに改ページを挿入する
linktitle: PDF ファイルに改ページを挿入する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルに改ページを挿入する方法を学習します。
type: docs
weight: 110
url: /ja/net/programming-with-tables/insert-page-break/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルに改ページを挿入する方法を学びます。C# のソース コードを段階的に説明します。このチュートリアルの最後には、PDF ドキュメントの表の特定の行数の後に改ページを追加する方法がわかります。さあ、始めましょう!

## ステップ1: 環境の設定
Aspose.PDF for .NET を使用して C# 開発環境が構成されていることを確認してください。ライブラリへの参照を追加し、必要な名前空間をインポートします。

## ステップ2: ドキュメントと表の作成
新しい Document インスタンスを作成し、このドキュメントにページを追加します。次に、PDF ドキュメント内の表を表す Table インスタンスを作成します。また、表の境界線のスタイルも定義します。

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## ステップ3: テーブルに行を追加する
ループを使用して配列に 200 行を追加します。行ごとに、Row のインスタンスを作成し、テキスト コンテンツを含む 2 つのセルを追加します。

```csharp
for (int counter = 0; counter <= 200; counter++)
{
     Aspose.Pdf.Row row = new Aspose.Pdf.Row();
     tab. Rows. Add(row);
    
     Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
     cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
     row. Cells. Add(cell1);
    
     Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
     cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
     row. Cells. Add(cell2);
    
     // 10行追加されると、新しい改ページが挿入されます
     if (counter % 10 == 0 && counter != 0)
         row. IsInNewPage = true;
}
```

## ステップ4: ドキュメントに表を追加する
ドキュメント ページの段落コレクションに表を追加します。

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## ステップ5: ドキュメントを保存する
ページ区切りを挿入した状態で PDF ドキュメントを保存します。

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### Aspose.PDF for .NET を使用して改ページを挿入するためのサンプル ソース コード

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//ドキュメントインスタンスをインスタンス化する
Document doc = new Document();
// PDFファイルのページコレクションにページを追加する
doc.Pages.Add();
//テーブルインスタンスを作成する
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
//テーブルの境界線のスタイルを設定する
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
//テーブルのデフォルトの境界線スタイルを境界線の色を赤に設定する
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
//表の列幅を指定する
tab.ColumnWidths = "100 100";
//テーブルに200行を追加するループを作成する
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	//10行追加されると、新しいページに新しい行がレンダリングされます
	if (counter % 10 == 0 && counter != 0) row.IsInNewPage = true;
}
//PDF ファイルの段落コレクションに表を追加する
doc.Pages[1].Paragraphs.Add(tab);

dataDir = dataDir + "InsertPageBreak_out.pdf";
// PDF文書を保存する
doc.Save(dataDir);

Console.WriteLine("\nPage break inserted successfully.\nFile saved at " + dataDir);
```

## 結論
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントに改ページを挿入する方法を学習しました。このステップ バイ ステップ ガイドを使用すると、C# を使用して PDF ドキュメント内の表の特定の行数の後に改ページを追加できます。

### PDF ファイルに改ページを挿入するための FAQ

#### Q: ページ区切り後に作成された新しいページのページ サイズを変更するにはどうすればよいですか?

 A: 改ページ後に作成される新しいページのページサイズを変更するには、`PageSize`の財産`Page`オブジェクト。たとえば、次のコードを使用してページ サイズを A4 に設定できます。

```csharp
//ページサイズをA4に設定する
doc.Pages[1].SetPageSize(PageSize.A4);
```

#### Q: ページ区切り後の新しいページのページ余白を制御できますか?

 A: はい、改ページ後の新しいページのページ余白を制御できます。`Margin`の財産`Page`オブジェクトを使用してページ余白を設定します。たとえば、すべての余白を 10 ポイントに設定するには、次のコードを使用します。

```csharp
//すべての余白を10ポイントに設定する
doc.Pages[1].Margin = new MarginInfo(10, 10, 10, 10);
```

#### Q: ページ区切り後の新しいページにヘッダーとフッターを追加することは可能ですか?

 A: はい、改ページ後の新しいページにヘッダーとフッターを追加できます。`Page.Header`そして`Page.Footer`プロパティを使用して、ページのヘッダーとフッターのセクションにコンテンツを追加します。例:

```csharp
//新しいページにヘッダーを追加する
doc.Pages[1].Header = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Header content") }
};

//新しいページにフッターを追加する
doc.Pages[1].Footer = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Footer content") }
};
```

#### Q: 特定の行数の後以外の特定の場所に改ページを挿入できますか?

 A: はい、特定の行数の後以外の特定の場所に改ページを挿入できます。`IsInNewPage`行のプロパティ`true`その行の後にテーブルが新しいページを開始するように強制します。

#### Q: コンテンツの高さに基づいて改ページ動作を調整するにはどうすればよいですか?

 A:`IsBroken`テーブルのプロパティで、ページ間の自動行区切りを有効または無効にします。`true`コンテンツの高さに基づいて行をページ間で分割できます。