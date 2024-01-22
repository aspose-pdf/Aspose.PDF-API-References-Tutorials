---
title: Excel ワークシート データをテーブルにエクスポート
linktitle: Excel ワークシート データをテーブルにエクスポート
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、Excel シートから PDF テーブルにデータをエクスポートします。
type: docs
weight: 70
url: /ja/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
このチュートリアルでは、Aspose.PDF for .NET ライブラリを使用して、Excel ワークシートからデータをエクスポートし、PDF ドキュメント内に表を作成する方法を学習します。ソースコードを段階的に確認し、各セクションを詳しく説明します。このチュートリアルを完了すると、Excel ワークシートのデータを含む表を含む PDF ファイルを生成できるようになります。始めましょう！

## 要件
始める前に、以下のものがあることを確認してください。

- C# プログラミング言語の基本的な知識
- マシンにインストールされている Visual Studio
- Aspose.PDF for .NET ライブラリがプロジェクトに追加されました

## ステップ 1: 環境のセットアップ
まず、Visual Studio で新しい C# プロジェクトを作成します。ソリューション エクスプローラーでプロジェクトを右クリックし、[NuGet パッケージの管理] を選択して、「Aspose.PDF」を検索して、Aspose.PDF for .NET ライブラリへの参照を追加します。パッケージをインストールすれば準備完了です。

## ステップ 2: Excel ワークシートのロード
コードの最初のステップでは、Excel ドキュメントを含むディレクトリへのパスを定義します。 「YOUR DOCUMENT DIRECTORY」を Excel ファイルが置かれている実際のディレクトリ パスに置き換えます。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

ここでは、Aspose.Cells ライブラリを使用して Excel ワークブックを読み込みます。 「newBook1.xlsx」を Excel ファイルの名前に置き換えてください。

## ステップ 3: ワークシートへのアクセス
次に、Excel ファイルの最初のワークシートにアクセスする必要があります。これを行うには、`Worksheets`のコレクション`Workbook`物体。

```csharp
// Excel ファイルの最初のワークシートへのアクセス
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

Excel ファイルに複数のワークシートが含まれている場合は、インデックス値を変更できます。`[0]`別のワークシートにアクセスします。

## ステップ 4: データを DataTable にエクスポートする
ここで、Excel ワークシートの内容を`DataTable`物体。エクスポートするセルの範囲を指定するには、`ExportDataTable`方法。

```csharp
// 1セル目から7行2列の内容をDataTableにエクスポート
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

この例では、ワークシートの最初のセル (0, 0) から最後のセルまでのすべての行と列をエクスポートします。要件に基づいて適切な範囲を設定します。

## ステップ 5: PDF ドキュメントの作成
次に、Aspose.PDF ライブラリを使用して新しい PDF ドキュメントを作成します。

```csharp
// Document インスタンスをインスタンス化する
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

これにより、コンテンツを追加できる空の PDF ドキュメントが作成されます。

## ステップ 6: ページとテーブルを追加する
データを表形式で表示するには、PDF ドキュメントにページと表を追加する必要があります。

```csharp
//ドキュメントインスタンスにページを作成する
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

//テーブルオブジェクトを作成する
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

//セクションの段落コレクションに Table オブジェクトを追加します。
sec1.Paragraphs.Add(tab1);
```

ここでは、新しいページとテーブル オブジェクトを作成します。次に、その表をページの段落コレクションに追加します。

## ステップ 7: テーブルのプロパティを設定する
データをインポートする前に、列幅やデフォルトのセル境界線など、テーブルのいくつかのプロパティを設定する必要があります。

```csharp
//テーブルの列幅を設定する
tab1.ColumnWidths = "40 100 100";

//BorderInfo オブジェクトを使用して表のデフォルトのセル境界線を設定します
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

この例では、列幅を 40、100、および 100 単位に設定します。データに基づいて値を調整します。また、各セルのすべての辺に境界線を表示するようにデフォルトのセル境界線を設定します。

## ステップ 8: テーブルへのデータのインポート
次に、からデータをインポートします。`DataTable`を使用してオブジェクトをテーブルに挿入します`ImportDataTable`方法。

```csharp
//上記で作成した DataTable から Table オブジェクトにデータをインポートします
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

ここでは、インポートする行と列の範囲を指定します。この例では、すべての行と列を`dataTable`物体。

## ステップ 9: テーブルのフォーマットを設定する
表の外観を向上させるために、特定のセルまたは行に書式設定を適用できます。このステップでは、テーブルの最初の行と交互の行をフォーマットします。

```csharp
//テーブルから最初の行を取得します
Aspose.Pdf.Row row1 = tab1.Rows[0];

//最初の行の書式を設定する
foreach(Aspose.Pdf.Cell curCell in row1.Cells)
{
     //最初の行のセルの背景色を設定します。
     curCell.BackgroundColor = Color.Blue;//最初の行のセルの面を設定します。
     curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    
     // 1行目のセルのフォント色を設定します。
     curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    
     //最初の行のセルのテキストの配置を設定します。
     curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

//代替行フォーマット
for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
     foreach(Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
     {
         //交互の行のセルの背景色を設定します。
         curCell.BackgroundColor = Color.Gray;
        
         //交互の行のセルのテキストの色を設定します。
         curCell.DefaultCellTextState.ForegroundColor = Color.White;
     }
}
```

ここでは、最初の行のセルを繰り返し処理し、背景色、フォントフェイス、フォントの色、テキストの配置を設定します。次に、交互の行のすべてのセルを反復処理し、背景とテキストの色を設定します。

## ステップ 10: PDF ドキュメントを保存する
最後に、PDF ドキュメントを指定した場所に保存します。

```csharp
//PDFを保存する
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

「YOUR DOCUMENT DIRECTORY」を、出力 PDF ファイルの目的のディレクトリ パスとファイル名に置き換えてください。

### Aspose.PDF for .NET を使用して Excel ワークシート データをテーブルにエクスポートするためのソース コードの例

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
// Excel ファイルの最初のワークシートへのアクセス
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
// 1セル目から7行2列の内容をDataTableにエクスポート
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

//ドキュメントインスタンスをインスタンス化する
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
//ドキュメントインスタンスにページを作成する
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

//テーブルオブジェクトを作成する
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

//セクションの段落コレクションに Table オブジェクトを追加します。
sec1.Paragraphs.Add(tab1);

//テーブルの列幅を設定します。 ColumnCount を手動で指定する必要があります。
//現在の Excel ワークシートには 3 つの列があるため、同じ数を指定しています。
tab1.ColumnWidths = "40 100 100";

//BorderInfo オブジェクトを使用して表のデフォルトのセル境界線を設定します
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

//上記で作成した DataTable から Table オブジェクトにデータをインポートします
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
//テーブルから最初の行を取得します
Aspose.Pdf.Row row1 = tab1.Rows[0];

// 1 行目のすべてのセルを反復処理し、背景色を青に設定します。
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	//表の 1 行目のすべてのセルの背景を設定します。
	curCell.BackgroundColor = Color.Blue;
	//表の1行目のセルのフォントフェイスを設定します。
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	//表の 1 行目のすべてのセルのフォントの色を設定します。
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	// 1行目のセルのテキスト配置を中央に設定します。
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	// 1 行目のすべてのセルを反復処理し、背景色を青に設定します。
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		// 1行目を除くすべてのセルの背景色を設定します。
		curCell.BackgroundColor = Color.Gray;
		// 1行目を除くすべてのセルの文字色を設定します。
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

//PDF を保存する
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## 結論
このチュートリアルでは、Aspose.PDF for .NET ライブラリを使用して Excel ワークシートから PDF テーブルにデータをエクスポートする方法を学びました。 Excel ワークシートの読み込み、PDF ドキュメントの作成、テーブルの追加、データのインポート、テーブルの書式設定といった段階的なプロセスを説明しました。 Excel データを含むテーブルを含む PDF ファイルをプログラムで生成できるようになりました。

### よくある質問

#### Q: Excel ワークシート データを PDF テーブルにエクスポートする目的は何ですか?

A: Excel ワークシート データを PDF テーブルにエクスポートすると、データを構造化され、整理された形式で表示できます。 Excel ワークシートのデータを含む表を含む PDF ファイルを生成できるため、情報をポータブルなドキュメント形式で共有および保存することが容易になります。

#### Q: PDF 表の外観をカスタマイズできますか?

A: はい、Aspose.PDF for .NET が提供するさまざまなプロパティを使用して PDF テーブルの外観をカスタマイズできます。提供された C# ソース コードでは、特定の要件に合わせて列幅、セルの境界線、テキストの配置、フォント スタイルなどを変更できます。

#### Q: 複数のワークシートを含む Excel ファイルを処理するにはどうすればよいですか?

 A: 提供された C# コードでは、インデックスを使用して Excel ファイルの最初のワークシートにアクセスしました。`[0]` 。 Excel ファイルに複数のワークシートが含まれている場合は、次のようにインデックス値を適宜変更することでそれらにアクセスできます。`[1]` 2 番目のワークシートの場合、または`[2]` 番目のワークシートの場合。

#### Q: PDF テーブル内の特定の行またはセルに別の書式設定を適用できますか?

A: はい、PDF テーブル内の特定の行またはセルに異なる書式設定を適用できます。提供された C# ソース コードでは、背景色、フォント スタイル、およびフォント色を変更することで、最初の行と交互の行を異なる形式でフォーマットする方法を示しました。必要に応じて、同様の書式設定手法を特定の行またはセルに適用できます。

#### Q: Aspose.PDF for .NET は、Excel データを PDF テーブルにエクスポートできる唯一のライブラリですか?

A: Aspose.PDF for .NET は、.NET アプリケーションで PDF ドキュメントを操作するための強力なライブラリです。他のライブラリも利用できる場合がありますが、Aspose.PDF for .NET は、Excel データからテーブルを含む PDF ファイルを生成、操作、エクスポートするための幅広い機能を提供するため、このようなタスクによく使用されます。