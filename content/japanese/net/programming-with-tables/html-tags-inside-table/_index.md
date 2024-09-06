---
title: PDF ファイル内のテーブル内の HTML タグ
linktitle: PDF ファイル内のテーブル内の HTML タグ
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内のテーブル内で HTML タグを使用する方法を学習します。
type: docs
weight: 100
url: /ja/net/programming-with-tables/html-tags-inside-table/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して、PDF ドキュメントのテーブル内で HTML タグを使用する方法を学習します。C# のソース コードをステップごとに説明します。このチュートリアルの最後には、PDF ドキュメントのテーブルに HTML コンテンツを挿入する方法がわかります。さあ、始めましょう!

## ステップ1: 環境の設定
Aspose.PDF for .NET を使用して C# 開発環境が構成されていることを確認してください。ライブラリへの参照を追加し、必要な名前空間をインポートします。

## ステップ2: テーブルデータの作成
String 型の「データ」列を含む DataTable を作成します。次に、HTML コンテンツを使用してこの DataTable に行を追加します。

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

## ステップ3: ドキュメントと表の作成
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

## ステップ4: テーブルにデータをインポートする
「ImportDataTable」メソッドを使用して、DataTable からテーブルにデータをインポートします。メソッド パラメータを指定して、DataTable のどの行と列の範囲をインポートするかを指定します。

```csharp
tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);
```

## ステップ5: ドキュメントに表を追加する
ドキュメントページにテーブルを追加します。

```csharp
doc.Pages[1].Paragraphs.Add(tableProvider);
```

## ステージ6: ドキュメントの保存
HTML コンテンツを含むテーブルを含む PDF ドキュメントを保存します。

```csharp
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

### Aspose.PDF for .NET を使用したテーブル内の HTML タグのサンプル ソース コード

```csharp
//ドキュメント ディレクトリへのパス。
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
//テーブルの新しいインスタンスを初期化します
Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
//テーブルの列幅を設定する
tableProvider.ColumnWidths = "400 50 ";
//テーブルの境界線の色をLightGrayに設定する
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
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントのテーブル内で HTML タグを使用する方法を学習しました。このステップ バイ ステップ ガイドを使用すると、C# を使用して PDF ドキュメントのテーブル セルに HTML コンテンツを挿入できます。

### PDF ファイル内のテーブル内の HTML タグに関する FAQ

#### Q: テーブルセル内で他の HTML タグや属性を使用できますか?

 A: はい、表のセル内ではさまざまなHTMLタグや属性を使用できます。`<b>`, `<i>`, `<a>`など、他にも多数あります。Aspose.PDF for .NET は、テーブル セル内のコンテンツの書式設定に使用できるさまざまな HTML 要素とスタイルをサポートしています。

#### Q: テーブルセル内の HTML コンテンツに CSS スタイルを適用できますか?

A: はい、テーブル セル内の HTML コンテンツに CSS スタイルを適用できます。Aspose.PDF for .NET は、HTML 要素に適用できる基本的な CSS スタイルをサポートしています。

#### Q: 表のセル内に HTML コンテンツとともに画像を追加することは可能ですか?

 A: はい、表のセル内にHTMLコンテンツと一緒に画像を追加できます。HTMLを使用できます。`<img>`ローカル ファイルや URL など、さまざまなソースからの画像を含めるためのタグ。

#### Q: テーブルに異なる列幅を指定するにはどうすればよいですか?

 A: テーブルの列幅を異なる値に指定するには、`ColumnWidths`テーブルのプロパティ。このプロパティは、スペースで区切られた値を含む文字列を受け取ります。各値は、列の幅をポイント単位で表します。

#### Q: HTML コンテンツを含むセル内でネストされたテーブルを使用できますか?

A: はい、HTML コンテンツを含むセル内でネストされたテーブルを使用できます。個別のテーブル インスタンスを作成し、セル内の HTML コンテンツの一部として追加することで、ネスト効果を実現できます。