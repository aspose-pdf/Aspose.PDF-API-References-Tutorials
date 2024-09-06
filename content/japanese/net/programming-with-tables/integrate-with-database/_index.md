---
title: PDFファイル内のデータベースとの統合
linktitle: PDFファイル内のデータベースとの統合
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、データベースのデータを PDF ファイルに埋め込みます。
type: docs
weight: 120
url: /ja/net/programming-with-tables/integrate-with-database/
---
このチュートリアルでは、Aspose.PDF for .NET を使用してデータベースのデータを PDF ファイルに埋め込む方法を学習します。C# のソース コードをステップごとに説明します。このチュートリアルの最後には、データベースのテーブル データを PDF ドキュメントにインポートする方法がわかります。さあ、始めましょう!

## ステップ1: 環境の設定
Aspose.PDF for .NET を使用して C# 開発環境が構成されていることを確認してください。ライブラリへの参照を追加し、必要な名前空間をインポートします。

## ステップ 2: DataTable の作成
PDF ドキュメントに埋め込むデータを表す DataTable のインスタンスを作成します。この例では、Employee_ID、Employee_Name、Gender の 3 つの列を持つ DataTable を作成します。また、ダミー データを含む 2 つの行を DataTable に追加します。

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));

DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);

dr = dt. NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
```

## ステップ3: PDFドキュメントと表の作成
Document のインスタンスを作成し、このドキュメントにページを追加します。次に、PDF ドキュメント内の表を表す Table インスタンスを作成します。表の列幅と境界線のスタイルを定義します。

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "40 100 100 100";
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## ステップ4: DataTableからテーブルにデータをインポートする
ImportDataTable メソッドを使用して、DataTable から PDF ドキュメント内のテーブルにデータをインポートします。

```csharp
table.ImportDataTable(dt, true, 0, 1, 3, 3);
```

## ステップ5: ドキュメントに表を追加する
ドキュメント ページの段落コレクションに表を追加します。

```csharp
doc.Pages[1].Paragraphs.Add(table);
```

## ステップ6: ドキュメントを保存する
埋め込みデータベースのデータを含む PDF ドキュメントを保存します。

```csharp
doc.Save(dataDir + "DataIntegrated_out.pdf");
```

おめでとうございます! Aspose.PDF for .NET を使用してデータベース データを PDF ドキュメントに埋め込む方法がわかりました。

### Aspose.PDF for .NET を使用してデータベースと統合するためのサンプル ソース コード

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));
//プログラムでDataTableオブジェクトに2行追加する
DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
//ドキュメントインスタンスを作成する
Document doc = new Document();
doc.Pages.Add();
//テーブルの新しいインスタンスを初期化します
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
//テーブルの列幅を設定する
table.ColumnWidths = "40 100 100 100";
//テーブルの境界線の色をLightGrayに設定する
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
//表のセルの境界線を設定する
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.ImportDataTable(dt, true, 0, 1, 3, 3);

//入力ドキュメントの最初のページにテーブルオブジェクトを追加します
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "DataIntegrated_out.pdf";
//テーブルオブジェクトを含む更新されたドキュメントを保存する
doc.Save(dataDir);

Console.WriteLine("\nDatabase integrated successfully.\nFile saved at " + dataDir);
```

## 結論
このチュートリアルでは、Aspose.PDF for .NET を使用してデータベースのデータを PDF ドキュメントに埋め込む方法を学習しました。このステップ バイ ステップ ガイドを使用して、独自のデータベースからデータをインポートし、PDF ドキュメントに表示できます。Aspose.PDF ドキュメントをさらに詳しく調べて、この強力なライブラリが提供するその他の機能と可能性を確認してください。

### PDF ファイルでのデータベースとの統合に関する FAQ

#### Q: Aspose.PDF for .NET を MySQL、SQL Server、Oracle などの異なるデータベース タイプで使用できますか?

A: はい、Aspose.PDF for .NET は、MySQL、SQL Server、Oracle などのさまざまなデータベース タイプで使用できます。Aspose.PDF for .NET には、データベース、XML ファイルなど、さまざまなデータ ソースからデータを読み取る機能があります。必要なデータベース タイプからデータを取得し、それを DataTable または Aspose.PDF for .NET と互換性のあるその他のデータ構造に取り込むことができます。

#### Q: PDF ドキュメント内の表の外観をカスタマイズするにはどうすればよいですか?

A: Aspose.PDF for .NET ライブラリが提供するさまざまなプロパティを使用して、PDF ドキュメント内の表の外観をカスタマイズできます。たとえば、表とそのセルの境界線のスタイル、背景色、フォント スタイル、配置をそれぞれ設定できます。表の外観のカスタマイズの詳細については、Aspose.PDF for .NET のドキュメントを参照してください。

#### Q: データベースからインポートしたデータにハイパーリンクやインタラクティブな要素を追加することは可能ですか?

A: はい、データベースからインポートしたデータにハイパーリンクやその他のインタラクティブな要素を追加できます。Aspose.PDF for .NET は、PDF ドキュメントへのハイパーリンク、ブックマーク、その他のインタラクティブな要素の追加をサポートしています。テーブルにインポートする前に DataTable のコンテンツを操作し、ハイパーリンクやその他のインタラクティブな機能を含めることができます。

#### Q: 特定の行数を超えた場合にテーブルをページ分割できますか?

 A: はい、テーブルが特定の行数を超える場合はページ区切りを付けることができます。これを実現するには、`IsInNewPage`Rowオブジェクトのプロパティを使用して、特定の行の後に新しいページを開始するように指定できます。ページごとに表示する行数を計算し、`IsInNewPage`それに応じて財産。

#### Q: データベース データが埋め込まれた PDF ドキュメントを DOCX や XLSX などの別のファイル形式にエクスポートするにはどうすればよいですか?

A: Aspose.PDF for .NET を使用すると、PDF ドキュメントを DOCX (Microsoft Word) や XLSX (Microsoft Excel) などのさまざまなファイル形式に変換できます。これを実現するには、Aspose.PDF for .NET ライブラリを Aspose.Words や Aspose.Cells などの他の Aspose ライブラリと組み合わせて使用します。まず、データベース データが埋め込まれた PDF ドキュメントを保存し、次にそれぞれの Aspose ライブラリを使用して目的のファイル形式に変換します。