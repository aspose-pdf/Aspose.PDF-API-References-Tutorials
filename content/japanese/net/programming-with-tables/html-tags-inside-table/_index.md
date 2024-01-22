---
title: PDF ファイルの表内の HTML タグ
linktitle: PDF ファイルの表内の HTML タグ
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルのテーブル内で HTML タグを使用する方法を学びます。
type: docs
weight: 100
url: /ja/net/programming-with-tables/html-tags-inside-table/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントのテーブル内で HTML タグを使用する方法を学習します。 C#のソースコードをステップバイステップで解説していきます。このチュートリアルの最後には、HTML コンテンツを PDF ドキュメントの表に挿入する方法がわかります。はじめましょう！

## ステップ 1: 環境をセットアップする
Aspose.PDF for .NET を使用して C# 開発環境が構成されていることを確認してください。参照をライブラリに追加し、必要な名前空間をインポートします。

## ステップ 2: テーブル データの作成
String型の「データ」列を含むDataTableを作成します。次に、HTML コンテンツを使用してこの DataTable に行を追加します。

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);
```

## ステップ 3: ドキュメントとテーブルの作成
新しい PDF ドキュメントを作成し、このドキュメントにページを追加します。次に、Table クラスのインスタンスを初期化し、テーブルのプロパティを設定します。

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
tableProvider. ColumnWidths = "400 50";
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 2.5F;
margin. Left = 2.5F;
margin. Bottom = 1.0F;
tableProvider. DefaultCellPadding = margin;
```

## ステップ 4: テーブルにデータをインポートする
「ImportDataTable」メソッドを使用して、DataTable からテーブルにデータをインポートします。 DataTable の行と列のどの範囲をインポートする必要があるかを示すメソッド パラメーターを指定します。

```csharp
tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);
```

## ステップ 5: ドキュメントに表を追加する
テーブルをドキュメント ページに追加します。

```csharp
doc.Pages[1].Paragraphs.Add(tableProvider);
```

## ステージ 6: ドキュメントの保存
HTML コンテンツを含むテーブルを含む PDF ドキュメントを保存します。

```csharp
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

### Aspose.PDF for .NET を使用したテーブル内の HTML タグのソース コード例

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);

Document doc = new Document();
doc.Pages.Add();
//テーブルの新しいインスタンスを初期化します。
Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
//テーブルの列幅を設定する
tableProvider.ColumnWidths = "400 50 ";
//テーブルの境界線の色を LightGray に設定します
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
//表のセルの境界線を設定する
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 2.5F;
margin.Left = 2.5F;
margin.Bottom = 1.0F;
tableProvider.DefaultCellPadding = margin;

tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);

doc.Pages[1].Paragraphs.Add(tableProvider);
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

## 結論
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントのテーブル内で HTML タグを使用する方法を学びました。このステップバイステップ ガイドを使用すると、C# を使用して PDF ドキュメント内の表のセルに HTML コンテンツを挿入できます。

### PDF ファイルの表内の HTML タグに関する FAQ

#### Q: 表のセル内で他の HTML タグや属性を使用できますか?

 A: はい、表のセル内でさまざまな HTML タグと属性を使用できます。`<b>`, `<i>`, `<a>`、 などなど。 Aspose.PDF for .NET は、表のセル内のコンテンツの書式設定に使用できる幅広い HTML 要素とスタイルをサポートしています。

#### Q: 表のセル内の HTML コンテンツに CSS スタイルを適用できますか?

A: はい、表のセル内の HTML コンテンツに CSS スタイルを適用できます。 Aspose.PDF for .NET は、HTML 要素に適用できる基本的な CSS スタイルのサポートを提供します。

#### Q: 表のセル内に HTML コンテンツとともに画像を追加することはできますか?

 A: はい、表のセル内に HTML コンテンツとともに画像を追加できます。 HTMLを使用できます`<img>`タグを使用して、ローカル ファイルや URL などのさまざまなソースからの画像を含めます。

#### Q: テーブルに異なる列幅を指定するにはどうすればよいですか?

 A: テーブルにさまざまな列幅を指定するには、`ColumnWidths`テーブルのプロパティ。このプロパティは、スペースで区切られた値を含む文字列を受け取ります。各値は列の幅をポイント単位で表します。

#### Q: HTML コンテンツを含むセル内でネストされたテーブルを使用できますか?

A: はい、HTML コンテンツを含むセル内でネストされたテーブルを使用できます。個別のテーブル インスタンスを作成し、セル内の HTML コンテンツの一部として追加して、ネスト効果を実現できます。