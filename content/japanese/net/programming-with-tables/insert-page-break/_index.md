---
title: PDF ファイルに改ページを挿入する
linktitle: PDF ファイルに改ページを挿入する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルに改ページを挿入する方法を学びます。
type: docs
weight: 110
url: /ja/net/programming-with-tables/insert-page-break/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルに改ページを挿入する方法を学習します。 C#のソースコードをステップバイステップで解説していきます。このチュートリアルの最後では、PDF ドキュメントの表の特定の行数の後に改ページを追加する方法がわかります。はじめましょう！

## ステップ 1: 環境をセットアップする
Aspose.PDF for .NET を使用して C# 開発環境が構成されていることを確認してください。参照をライブラリに追加し、必要な名前空間をインポートします。

## ステップ 2: ドキュメントとテーブルの作成
新しい Document インスタンスを作成し、このドキュメントにページを追加します。次に、PDF ドキュメント内のテーブルを表す Table インスタンスを作成します。テーブルの境界線スタイルも定義します。

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## ステップ 3: テーブルに行を追加する
ループを使用して配列に 200 行を追加します。行ごとに Row のインスタンスを作成し、テキスト コンテンツを含む 2 つのセルを追加します。

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
    
     // 10行追加したら改ページを挿入します
     if (counter % 10 == 0 && counter != 0)
         row. IsInNewPage = true;
}
```

## ステップ 4: ドキュメントに表を追加する
テーブルをドキュメント ページの段落コレクションに追加します。

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## ステップ 5: ドキュメントを保存する
PDF ドキュメントを改ページを挿入して保存します。

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### Aspose.PDF for .NET を使用した改ページの挿入のソース コード例

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//ドキュメントインスタンスをインスタンス化する
Document doc = new Document();
// PDF ファイルのページコレクションにページを追加
doc.Pages.Add();
//テーブルインスタンスの作成
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
//表の境界線スタイルを設定する
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
//表のデフォルトの境界線スタイルを境界線の色を赤に設定します
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
//テーブルの列幅を指定する
tab.ColumnWidths = "100 100";
//テーブルに 200 行を追加するループを作成します。
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	// 10 行が追加されると、新しいページに新しい行がレンダリングされます
	if (counter % 10 == 0 && counter != 0) row.IsInNewPage = true;
}
//PDF ファイルの段落コレクションに表を追加します
doc.Pages[1].Paragraphs.Add(tab);

dataDir = dataDir + "InsertPageBreak_out.pdf";
// PDF ドキュメントを保存する
doc.Save(dataDir);

Console.WriteLine("\nPage break inserted successfully.\nFile saved at " + dataDir);
```

## 結論
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントに改ページを挿入する方法を学びました。このステップバイステップ ガイドを使用すると、C# を使用して PDF ドキュメント内の表の特定の行数の後に改ページを追加できます。

### PDF ファイルに改ページを挿入する場合の FAQ

#### Q: 改ページ後に作成される新しいページのページ サイズを変更するにはどうすればよいですか?

 A: 改ページの後に作成される新しいページのページ サイズを変更するには、`PageSize`の財産`Page`物体。たとえば、次のコードを使用して、ページ サイズを A4 に設定できます。

```csharp
//ページサイズをA4に設定します
doc.Pages[1].SetPageSize(PageSize.A4);
```

#### Q: 改ページ後の新しいページのページ余白を制御できますか?

 A: はい、改ページ後の新しいページのページ余白を制御できます。使用`Margin`の財産`Page`ページ余白を設定するオブジェクト。たとえば、すべての余白を 10 ポイントに設定するには、次のコードを使用できます。

```csharp
//すべての余白を 10 ポイントに設定します
doc.Pages[1].Margin = new MarginInfo(10, 10, 10, 10);
```

#### Q: 改ページ後の新しいページにヘッダーとフッターを追加することはできますか?

 A: はい、改ページ後の新しいページにヘッダーとフッターを追加できます。使用`Page.Header`そして`Page.Footer`プロパティを使用して、ページのヘッダー セクションとフッター セクションにコンテンツを追加します。例えば：

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

 A: はい、特定の行数の後以外の特定の場所に改ページを挿入できます。設定できるのは、`IsInNewPage`行のプロパティを`true`テーブルがその行の後に新しいページを開始するように強制します。

#### Q: コンテンツの高さに基づいて改ページの動作を調整するにはどうすればよいですか?

A: を使用できます。`IsBroken`テーブルのプロパティを使用して、ページ間での自動行分割を有効または無効にします。に設定すると`true`を使用すると、コンテンツの高さに基づいて行をページ間で区切ることができます。