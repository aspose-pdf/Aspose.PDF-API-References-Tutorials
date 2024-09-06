---
title: Excel ワークシートのデータをテーブルにエクスポート
linktitle: Excel ワークシートのデータをテーブルにエクスポート
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、Excel シートから PDF テーブルにデータをエクスポートします。
type: docs
weight: 70
url: /ja/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
このチュートリアルでは、Aspose.PDF for .NET ライブラリを使用して、Excel ワークシートからデータをエクスポートし、PDF ドキュメントにテーブルを作成する方法を学習します。ソース コードをステップごとに説明し、各セクションを詳しく説明します。このチュートリアルの最後には、Excel ワークシートのデータを含むテーブルを含む PDF ファイルを生成できるようになります。さあ、始めましょう!

## 要件
始める前に、以下のものを用意してください。

- C#プログラミング言語の基礎知識
- お使いのマシンに Visual Studio がインストールされている
- Aspose.PDF for .NET ライブラリがプロジェクトに追加されました

## ステップ1: 環境の設定
まず、Visual Studio で新しい C# プロジェクトを作成します。ソリューション エクスプローラーでプロジェクトを右クリックし、[NuGet パッケージの管理] を選択して「Aspose.PDF」を検索し、Aspose.PDF for .NET ライブラリへの参照を追加します。パッケージをインストールすれば準備完了です。

## ステップ2: Excelワークシートの読み込み
コードの最初のステップでは、Excel ドキュメントを含むディレクトリへのパスを定義します。「YOUR DOCUMENT DIRECTORY」を、Excel ファイルが配置されている実際のディレクトリ パスに置き換えます。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

ここでは、Aspose.Cells ライブラリを使用して Excel ワークブックを読み込みます。「newBook1.xlsx」を Excel ファイルの名前に置き換えてください。

## ステップ3: ワークシートにアクセスする
次に、Excelファイルの最初のワークシートにアクセスする必要があります。`Worksheets`コレクションの`Workbook`物体。

```csharp
// Excelファイルの最初のワークシートにアクセスする
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

Excelファイルに複数のワークシートが含まれている場合は、インデックス値を変更できます。`[0]`別のワークシートにアクセスします。

## ステップ 4: DataTable へのデータのエクスポート
ここで、Excelワークシートの内容を`DataTable`オブジェクト。エクスポートするセルの範囲を`ExportDataTable`方法。

```csharp
// 番目のセルから始まる 7 行 2 列の内容を DataTable にエクスポートします。
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

この例では、ワークシートの最初のセル (0, 0) から最後のセルまでのすべての行と列をエクスポートします。要件に応じて適切な範囲を設定します。

## ステップ5: PDFドキュメントの作成
ここで、Aspose.PDF ライブラリを使用して新しい PDF ドキュメントを作成します。

```csharp
//ドキュメントインスタンスをインスタンス化する
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

これにより、コンテンツを追加できる空の PDF ドキュメントが作成されます。

## ステップ6: ページと表を追加する
データを表形式で表示するには、PDF ドキュメントにページと表を追加する必要があります。

```csharp
//ドキュメントインスタンスにページを作成する
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

//テーブルオブジェクトを作成する
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

//セクションの段落コレクションにTableオブジェクトを追加します。
sec1.Paragraphs.Add(tab1);
```

ここでは、新しいページとテーブル オブジェクトを作成します。次に、そのテーブルをページの段落コレクションに追加します。

## ステップ7: テーブルプロパティの設定
データをインポートする前に、列の幅やデフォルトのセルの境界線など、テーブルのいくつかのプロパティを設定する必要があります。

```csharp
//テーブルの列幅を設定する
tab1.ColumnWidths = "40 100 100";

//BorderInfo オブジェクトを使用してテーブルのデフォルトのセル境界線を設定する
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

この例では、列幅を 40、100、100 単位に設定しています。データに基づいて値を調整してください。また、各セルのすべての辺に境界線が表示されるように、デフォルトのセル境界線を設定しています。

## ステップ8: テーブルへのデータのインポート
さて、データをインポートします`DataTable`オブジェクトをテーブルに挿入するには、`ImportDataTable`方法。

```csharp
//上記で作成したDataTableからTableオブジェクトにデータをインポートします。
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

ここでは、インポートする行と列の範囲を指定します。この例では、`dataTable`物体。

## ステップ9: 表の書式設定
表の外観を向上させるために、特定のセルまたは行に書式を適用できます。この手順では、表の最初の行と交互の行に書式を設定します。

```csharp
//テーブルから1行目を取得する
Aspose.Pdf.Row row1 = tab1.Rows[0];

//最初の行をフォーマットする
foreach(Aspose.Pdf.Cell curCell in row1.Cells)
{
     //最初の行のセルの背景色を設定する
     curCell.BackgroundColor = Color.Blue;//最初の行のセルの面を設定する
     curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    
     //最初の行のセルのフォント色を設定する
     curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    
     //最初の行のセルのテキスト配置を設定する
     curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

//交互行形式
for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
     foreach(Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
     {
         //交互の行のセルの背景色を設定する
         curCell.BackgroundColor = Color.Gray;
        
         //交互の行のセルのテキストの色を設定する
         curCell.DefaultCellTextState.ForegroundColor = Color.White;
     }
}
```

ここでは、最初の行のセルを反復処理して、背景色、フォント フェイス、フォント色、テキスト配置を設定します。次に、交互の行のすべてのセルを反復処理して、背景色とテキスト色を設定します。

## ステップ10: PDFドキュメントを保存する
最後に、PDF ドキュメントを指定された場所に保存します。

```csharp
//PDFを保存する
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

「YOUR DOCUMENT DIRECTORY」を、出力 PDF ファイルの目的のディレクトリ パスとファイル名に置き換えてください。

### Aspose.PDF for .NET を使用して Excel ワークシート データをテーブルにエクスポートするためのサンプル ソース コード

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
// Excelファイルの最初のワークシートにアクセスする
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
// 番目のセルから始まる 7 行 2 列の内容を DataTable にエクスポートします。
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

//ドキュメントインスタンスをインスタンス化する
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
//ドキュメントインスタンスにページを作成する
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

//テーブルオブジェクトを作成する
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

//セクションの段落コレクションにTableオブジェクトを追加します。
sec1.Paragraphs.Add(tab1);

//テーブルの列幅を設定します。ColumnCount を手動で指定する必要があります。
//現在のExcelワークシートには3つの列があるので、同じカウントを指定しています。
tab1.ColumnWidths = "40 100 100";

//BorderInfo オブジェクトを使用してテーブルのデフォルトのセル境界線を設定する
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

//上記で作成したDataTableからTableオブジェクトにデータをインポートします。
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
//テーブルから1行目を取得する
Aspose.Pdf.Row row1 = tab1.Rows[0];

// 1行目のすべてのセルを反復処理し、背景色を青に設定します。
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	//表の 1 行目にあるすべてのセルの背景を設定します。
	curCell.BackgroundColor = Color.Blue;
	//表の 1 行目のセルのフォント フェイスを設定します。
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	//表の 1 行目にあるすべてのセルのフォント色を設定します。
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	// 1行目のセルのテキスト配置を中央に設定します。
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	// 1行目のすべてのセルを反復処理し、背景色を青に設定します。
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		// 1行目を除くすべてのセルの背景色を設定します。
		curCell.BackgroundColor = Color.Gray;
		// 1 行目を除くすべてのセルのテキストの色を設定します。
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

//PDFを保存する
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## 結論
このチュートリアルでは、Aspose.PDF for .NET ライブラリを使用して、Excel ワークシートから PDF テーブルにデータをエクスポートする方法を学習しました。Excel ワークシートの読み込み、PDF ドキュメントの作成、テーブルの追加、データのインポート、テーブルの書式設定のプロセスをステップごとに説明しました。これで、Excel データを含むテーブルを含む PDF ファイルをプログラムで生成できるようになりました。

### よくある質問

#### Q: Excel ワークシート データを PDF テーブルにエクスポートする目的は何ですか?

A: Excel ワークシートのデータを PDF テーブルにエクスポートすると、データを構造化され整理された形式で表示できます。Excel ワークシートのデータを含むテーブルを含む PDF ファイルを生成できるため、ポータブル ドキュメント形式で情報を共有および保存しやすくなります。

#### Q: PDF テーブルの外観をカスタマイズできますか?

A: はい、Aspose.PDF for .NET が提供するさまざまなプロパティを使用して、PDF テーブルの外観をカスタマイズできます。提供されている C# ソース コードでは、列幅、セルの境界線、テキストの配置、フォント スタイルなどを、特定の要件に合わせて変更できます。

#### Q: 複数のワークシートを含む Excel ファイルをどのように処理すればよいですか?

 A: 提供されたC#コードでは、インデックスを使用してExcelファイルの最初のワークシートにアクセスしました。`[0]` Excelファイルに複数のワークシートが含まれている場合は、次のようにインデックス値を変更することでアクセスできます。`[1]` 2番目のワークシートまたは`[2]`3番目のワークシート用。

#### Q: PDF テーブル内の特定の行またはセルに異なる書式を適用できますか?

A: はい、PDF テーブルの特定の行またはセルに異なる書式を適用できます。提供されている C# ソース コードでは、背景色、フォント スタイル、フォント色を変更して、最初の行と交互の行を異なる書式で設定する方法を示しました。必要に応じて、特定の行またはセルに同様の書式設定手法を適用できます。

#### Q: Aspose.PDF for .NET は、Excel データを PDF テーブルにエクスポートできる唯一のライブラリですか?

A: Aspose.PDF for .NET は、.NET アプリケーションで PDF ドキュメントを操作するための強力なライブラリです。他にも利用できるライブラリがあるかもしれませんが、Aspose.PDF for .NET は、Excel データからテーブルを含む PDF ファイルを生成、操作、エクスポートするための幅広い機能と能力を備えているため、このようなタスクでよく使用されます。