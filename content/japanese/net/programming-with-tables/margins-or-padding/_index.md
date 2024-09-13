---
title: 余白またはパディング
linktitle: 余白またはパディング
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して表の余白またはパディングを設定する方法を学習します。
type: docs
weight: 140
url: /ja/net/programming-with-tables/margins-or-padding/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して表の余白やパディングを設定する手順を順を追って説明します。この機能を理解して C# ソース コードに実装するのに役立つ説明とコード スニペットを提供します。

## ステップ1: ドキュメントとページの設定
まず、次のコードを使用してドキュメントとページを設定する必要があります。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//空のコンストラクタを呼び出してDocumentオブジェクトをインスタンス化する
Document doc = new Document();
Page page = doc.Pages.Add();
```

## ステップ2: テーブルの作成
次に、Aspose.Pdf.Table クラスを使用してテーブル オブジェクトを作成します。

```csharp
//テーブルオブジェクトをインスタンス化する
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
//目的のセクションの段落コレクションに表を追加します
page.Paragraphs.Add(tab1);
```

## ステップ3: 列幅とデフォルトのセル境界線を設定する
テーブルの列幅とデフォルトのセル境界線を設定するには、次のコードを使用します。

```csharp
//テーブルの列幅を設定する
tab1. ColumnWidths = "50 50 50";
//BorderInfoオブジェクトを使用してデフォルトのセル境界線を設定する
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## ステップ4: 表の境界線とセルの余白を設定する
テーブルの境界線とセルの余白を設定するには、MarginInfo オブジェクトを作成し、そのプロパティを設定します。

```csharp
// MarginInfoオブジェクトを作成し、左、下、右、上の余白を設定します。
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;

//デフォルトのセルパディングをMarginInfoオブジェクトに設定する
tab1. DefaultCellPadding = margin;

//別のカスタマイズされたBorderInfoオブジェクトを使用して表の境界線を設定する
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
```

## ステップ5: 行とセルの追加
次に、表に行とセルを追加しましょう。新しい行を作成し、そこにセルを追加します。

```csharp
//表に行を作成し、行にセルを作成します
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
```

## ステップ6: セルにテキストを追加する
セルにテキストを追加するには、TextFragment オブジェクトを作成し、目的のセルに追加します。

```csharp
TextFragment mytext = new TextFragment("col3 with large text string");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
```

## ステップ7: PDFを保存する
PDF ドキュメントを保存するには、次のコードを使用します。

```csharp
dataDir = dataDir + "MarginsOrPadding_out.pdf";
//PDFを保存する
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir);
```

### Aspose.PDF for .NET を使用した余白またはパディングのサンプル ソース コード

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//空のコンストラクタを呼び出してDocumentオブジェクトをインスタンス化する
Document doc = new Document();
Page page = doc.Pages.Add();
//テーブルオブジェクトをインスタンス化する
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
//希望するセクションの段落コレクションに表を追加します
page.Paragraphs.Add(tab1);
//テーブルの列幅を設定する
tab1.ColumnWidths = "50 50 50";
// BorderInfo オブジェクトを使用してデフォルトのセル境界線を設定する
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
//別のカスタマイズされたBorderInfoオブジェクトを使用して表の境界線を設定する
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
//MarginInfoオブジェクトを作成し、左、下、右、上の余白を設定します。
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
//デフォルトのセルパディングをMarginInfoオブジェクトに設定する
tab1.DefaultCellPadding = margin;
//表に行を作成し、行にセルを作成します
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
TextFragment mytext = new TextFragment("col3 with large text string");
//Row1.Cells.Add("セル内に配置する大きなテキスト文字列を含む列3");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
// Row1.Cells[2].Paragraphs[0].FixedWidth= 80;
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// PDFを保存する
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir); 
```

## 結論
おめでとうございます。Aspose.PDF for .NET を使用して、表に余白やパディングを設定する方法を学習しました。この知識は、ドキュメントの書式設定機能を強化し、表を視覚的に魅力的にするのに役立ちます。

### よくある質問

#### Q: 表内の個々のセルに異なる余白やパディングを設定できますか?

 A: はい、Aspose.PDF for .NETを使用して、表内の個々のセルに異なる余白やパディングを設定できます。提供されている例では、`DefaultCellPadding`プロパティ。特定のセルに異なるパディングを設定するには、`MarginInfo`各セルを個別に選択し、余白を変更します。

#### Q: テーブルの境界線の色やスタイルを変更するにはどうすればよいですか?

 A: 表の境界線の色やスタイルを変更するには、`Color`そして`Width`の特性`BorderInfo`オブジェクト。例では、境界線の色を黒、幅を1F（1ポイント）に設定しています。`tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);`必要に応じて色と幅を調整できます。

#### Q: 表にヘッダーやフッターを追加することはできますか?

A: はい、Aspose.PDF for .NET を使用して、表にヘッダーまたはフッターを追加できます。ヘッダーとフッターは通常、列ラベル、表のタイトル、要約データなどの追加情報を含む個別の行です。追加の行を作成し、異なるスタイルを設定し、表のコンテンツの上または下に追加できます。

#### Q: 表のセル内のテキストの配置を調整するにはどうすればよいですか?

 A: 表のセル内のテキストの配置を調整するには、`HorizontalAlignment`そして`VerticalAlignment`の特性`TextFragment`オブジェクト。例えば、テキストを水平に中央揃えにするには、次のように設定します。`mytext.HorizontalAlignment = HorizontalAlignment.Center;`同様に、`mytext.VerticalAlignment`垂直方向の配置を制御します。

#### Q: テキストの代わりに表のセルに画像を追加できますか?

 A: はい、Aspose.PDF for .NETを使用して表のセルに画像を追加できます。`TextFragment`オブジェクトを作成すると、`Image`オブジェクトを作成し、画像ファイルを読み込み、`cell.Paragraphs.Add(image);`方法。これにより、テキスト コンテンツと一緒にテーブルに画像を挿入できます。