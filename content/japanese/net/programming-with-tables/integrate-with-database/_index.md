---
title: PDF ファイルのデータベースと統合
linktitle: PDF ファイルのデータベースと統合
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、データベースからのデータを PDF ファイルに埋め込みます。
type: docs
weight: 120
url: /ja/net/programming-with-tables/integrate-with-database/
---
このチュートリアルでは、Aspose.PDF for .NET を使用してデータベースのデータを PDF ファイルに埋め込む方法を学習します。 C#のソースコードをステップバイステップで解説していきます。このチュートリアルの最後には、テーブル データをデータベースから PDF ドキュメントにインポートする方法がわかります。はじめましょう！

## ステップ 1: 環境をセットアップする
Aspose.PDF for .NET を使用して C# 開発環境が構成されていることを確認してください。参照をライブラリに追加し、必要な名前空間をインポートします。

## ステップ 2: DataTable の作成
PDF ドキュメントに埋め込みたいデータを表す DataTable のインスタンスを作成します。この例では、Employee_ID、Employee_Name、Gender の 3 つの列を含む DataTable を作成します。また、ダミー データを含む 2 つの行を DataTable に追加します。

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

## ステップ 3: PDF ドキュメントと表を作成する
Document のインスタンスを作成し、このドキュメントにページを追加します。次に、PDF ドキュメント内のテーブルを表す Table インスタンスを作成します。テーブルの列幅と境界線のスタイルを定義します。

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "40 100 100 100";
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## ステップ 4: DataTable からテーブルにデータをインポートする
ImportDataTable メソッドを使用して、DataTable から PDF ドキュメント内のテーブルにデータをインポートします。

```csharp
table.ImportDataTable(dt, true, 0, 1, 3, 3);
```

## ステップ 5: ドキュメントに表を追加する
テーブルをドキュメント ページの段落コレクションに追加します。

```csharp
doc.Pages[1].Paragraphs.Add(table);
```

## ステップ 6: ドキュメントを保存する
埋め込みデータベースのデータを含む PDF ドキュメントを保存します。

```csharp
doc.Save(dataDir + "DataIntegrated_out.pdf");
```

おめでとう！ Aspose.PDF for .NET を使用してデータベース データを PDF ドキュメントに埋め込む方法がわかりました。

### Aspose.PDF for .NET を使用したデータベースとの統合のソース コード例

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));
//プログラムで DataTable オブジェクトに 2 行を追加します。
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
//ドキュメントインスタンスの作成
Document doc = new Document();
doc.Pages.Add();
//テーブルの新しいインスタンスを初期化します。
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
//テーブルの列幅を設定する
table.ColumnWidths = "40 100 100 100";
//テーブルの境界線の色を LightGray に設定します
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
//表のセルの境界線を設定する
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.ImportDataTable(dt, true, 0, 1, 3, 3);

//入力ドキュメントの最初のページにテーブル オブジェクトを追加します
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "DataIntegrated_out.pdf";
//テーブルオブジェクトを含む更新されたドキュメントを保存する
doc.Save(dataDir);

Console.WriteLine("\nDatabase integrated successfully.\nFile saved at " + dataDir);
```

## 結論
このチュートリアルでは、Aspose.PDF for .NET を使用してデータベースから PDF ドキュメントにデータを埋め込む方法を学びました。このステップバイステップ ガイドを使用して、独自のデータベースからデータをインポートし、PDF ドキュメントで表示できます。 Aspose.PDF ドキュメントをさらに詳しく調べて、この強力なライブラリが提供する他の機能や可能性を発見してください。

### PDF ファイルでのデータベースとの統合に関する FAQ

#### Q: Aspose.PDF for .NET を MySQL、SQL Server、Oracle などのさまざまなデータベース タイプで使用できますか?

A: はい、Aspose.PDF for .NET は、MySQL、SQL Server、Oracle などのさまざまなデータベース タイプで使用できます。 Aspose.PDF for .NET は、データベース、XML ファイルなどを含むさまざまなデータ ソースからデータを読み取る機能を提供します。目的のデータベース タイプからデータを取得し、DataTable または Aspose.PDF for .NET と互換性のあるその他のデータ構造にデータを取り込むことができます。

#### Q: PDF ドキュメント内の表の外観をカスタマイズするにはどうすればよいですか?

A: Aspose.PDF for .NET ライブラリによって提供されるさまざまなプロパティを使用して、PDF ドキュメント内の表の外観をカスタマイズできます。たとえば、表とそのセルにさまざまな枠線スタイル、背景色、フォント スタイル、配置を設定できます。テーブルの外観のカスタマイズの詳細については、Aspose.PDF for .NET のドキュメントを参照してください。

#### Q: データベースからインポートされたデータにハイパーリンクやインタラクティブな要素を追加することはできますか?

A: はい、データベースからインポートされたデータにハイパーリンクやその他のインタラクティブな要素を追加できます。 Aspose.PDF for .NET は、PDF ドキュメントへのハイパーリンク、ブックマーク、その他の対話型要素の追加をサポートしています。 DataTable のコンテンツをテーブルにインポートする前に操作して、ハイパーリンクやその他の対話型機能を含めることができます。

#### Q: テーブルが特定の行数を超えた場合、テーブルをページ分割できますか?

 A: はい、テーブルが特定の行数を超える場合は、テーブルをページ分割できます。これを実現するには、`IsInNewPage`Row オブジェクトのプロパティを使用して、特定の行の後に新しいページを開始する必要があることを示します。ページごとに表示する行数を計算し、`IsInNewPage`それに応じてプロパティ。

#### Q: データベース データが埋め込まれた PDF ドキュメントを DOCX や XLSX などの異なるファイル形式にエクスポートするにはどうすればよいですか?

A: Aspose.PDF for .NET を使用すると、PDF ドキュメントを DOCX (Microsoft Word) や XLSX (Microsoft Excel) などの他のさまざまなファイル形式に変換できます。 Aspose.PDF for .NET ライブラリを、Aspose.Words や Aspose.Cells などの他の Aspose ライブラリと組み合わせて使用すると、これを実現できます。まず、データベース データが埋め込まれた PDF ドキュメントを保存し、それぞれの Aspose ライブラリを使用して希望のファイル形式に変換します。