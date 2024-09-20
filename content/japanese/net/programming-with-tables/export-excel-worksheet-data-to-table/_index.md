---
title: Excel ワークシートのデータをテーブルにエクスポート
linktitle: Excel ワークシートのデータをテーブルにエクスポート
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して Excel ワークシート データを PDF テーブルにエクスポートする方法を学びます。コード例、前提条件、役立つヒントを含むステップバイステップのチュートリアルです。
type: docs
weight: 70
url: /ja/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
## 導入

Excel ワークシートからデータを PDF ファイルにエクスポートし、テーブル形式に整然と整理する必要があったことはありませんか? Excel に大量のデータがあり、それをプロフェッショナルな PDF として共有する必要があると想像してみてください。複雑に思えるかもしれませんね。しかし、Aspose.PDF for .NET を使用すると、このタスクを簡単に実行できます。このチュートリアルでは、Aspose.PDF for .NET を使用して Excel ワークシートのデータを PDF ドキュメント内のテーブルにエクスポートするプロセスについて説明します。初心者でも最後までプロのように感じられるよう、すべてを詳しく説明してステップごとに説明します。

## 前提条件

コーディングを始める前に、いくつかの設定をしておきましょう。

1.  Aspose.PDF for .NETライブラリ – 最新バージョンがインストールされていることを確認してください。[ここからダウンロード](https://releases.aspose.com/pdf/net/).
2.  Aspose.Cells for .NET ライブラリ – Excel の操作にはこれが必要です。ここからダウンロードしてください。[ここ](https://releases.aspose.com/cells/net/).
3. .NET 開発環境 - Visual Studio のようなツールはコーディングに最適です。
4. Excel ファイル - エクスポートするデータを含む Excel ファイルを用意します。

 Aspose.PDFとAspose.Cellsライブラリをお持ちでない場合は、[無料トライアル](https://releases.aspose.com/).

## パッケージのインポート

まず、プロジェクトに Aspose.PDF ライブラリと Aspose.Cells ライブラリの両方がインストールされていることを確認します。これらは、Visual Studio の NuGet パッケージ マネージャーを使用してインストールできます。

C# コードに必要なパッケージをインポートする方法は次のとおりです。

```csharp
using System.Data;
using System.IO;
using System.Linq;
```

前提条件が設定されたので、Excel シートから PDF ドキュメントのテーブルにデータをエクスポートするプロセスを説明しましょう。

## ステップ1: Excelワークブックを読み込む

まず、Excel ブックをプログラムに読み込む必要があります。この手順では、Aspose.Cells を使用して Excel ファイルを開きます。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Excelワークブックを読み込む
Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

説明: ここでは、Excelファイルが保存されているディレクトリパスを指定し、次の方法でワークブックを読み込みます。`Aspose.Cells.Workbook`必ず調整してください`"YOUR DOCUMENT DIRECTORY"`ファイルの場所を指定します。

## ステップ2: 最初のワークシートにアクセスする

ワークブックを読み込んだ後、データが保存されている最初のワークシートにアクセスする必要があります。

```csharp
// Excelファイルの最初のワークシートにアクセスする
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

説明: この手順は簡単です。エクスポートするデータが含まれているワークブックの最初のワークシートを取得します。

## ステップ3: データをDataTableにエクスポートする

ここで、Excel シートから DataTable オブジェクトにデータをエクスポートします。このオブジェクトは、データを PDF に転送するための仲介役として機能します。

```csharp
// 1番目のセルから始まる7行2列の内容をDataTableにエクスポートする
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

説明:`ExportDataTable`このメソッドは、ワークシートの最初のセルからすべての行と列にわたるデータを抽出します。このデータは、`DataTable`今後の使用のために。

## ステップ4: 新しいPDFドキュメントを作成する

次に、Aspose.PDF を使用して新しい PDF ドキュメントを作成する必要があります。

```csharp
//ドキュメントインスタンスをインスタンス化する
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

//ドキュメントインスタンスにページを作成する
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

説明: ここで、新しい`Aspose.Pdf.Document`そこにページを追加します。このページには、後で Excel データから作成するテーブルが含まれます。

## ステップ5: PDFで表オブジェクトを作成する

次に、PDF ドキュメント内に表を作成します。

```csharp
//テーブルオブジェクトを作成する
Aspose.Pdf.Table table = new Aspose.Pdf.Table();

//ページの段落コレクションにTableオブジェクトを追加します。
page.Paragraphs.Add(table);
```

説明: 私たちは`Aspose.Pdf.Table`オブジェクトを作成してページの段落コレクションに追加します。これにより、テーブルがページに表示されるようになります。

## ステップ6: 列の幅と境界線を設定する

PDF 内の表には列幅を定義する必要があります。表を読みやすくするために境界線も追加します。

```csharp
//テーブルの列幅を設定する
table.ColumnWidths = "40 100 100";

//デフォルトのセル境界線を設定する
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

説明: 3つの列の幅を設定し、すべてのセルにデフォルトの境界線を太さで設定します。`0.1F`.

## ステップ 7: DataTable から PDF テーブルにデータをインポートする

ここで、DataTable から PDF テーブルにデータをインポートします。

```csharp
// DataTableからTableオブジェクトにデータをインポートする
table.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

説明:`ImportDataTable`メソッドは、すべてのデータを`DataTable`PDF テーブルに追加します。これにより、Excel シートのデータがテーブルに入力されます。

## ステップ8: ヘッダー行のスタイルを設定する

背景色、フォント、配置を変更して、表のヘッダー行のスタイルを設定しましょう。

```csharp
//テーブルから最初の行を取得する
Aspose.Pdf.Row headerRow = table.Rows[0];

//ヘッダー行のスタイルを設定する
foreach (Aspose.Pdf.Cell cell in headerRow.Cells)
{
    cell.BackgroundColor = Color.Blue;
    cell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    cell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    cell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}
```

説明: 最初の行 (ヘッダー) のすべてのセルをループし、背景色を青、テキスト色を黄色に設定し、テキストを中央に揃えます。

## ステップ9: 残りの行のスタイルを設定する

ヘッダーと残りの行を区別するために、残りの行に異なるスタイルを追加しましょう。

```csharp
for (int i = 1; i <= dataTable.Rows.Count; i++)
{
    foreach (Aspose.Pdf.Cell cell in table.Rows[i].Cells)
    {
        cell.BackgroundColor = Color.Gray;
        cell.DefaultCellTextState.ForegroundColor = Color.White;
    }
}
```

説明: ヘッダーを除くすべての行に、灰色の背景と白のテキスト色を設定します。

## ステップ10: PDFドキュメントを保存する

最後に、表を含む PDF ドキュメントを保存します。

```csharp
// PDFを保存する
pdfDocument.Save(dataDir + "Exceldata_toPdf_table.pdf");
```

説明: PDF を指定されたディレクトリに保存します。これで、Excel データが美しくフォーマットされた PDF テーブル内に格納されます。

## 結論

これで完了です。わずか数ステップで、Aspose.PDF for .NET を使用して、Excel ワークシートから PDF 内のテーブルにデータをエクスポートできました。プロセスを分解して途中でスタイルを設定することで、出力をカスタマイズし、データがきれいでプロフェッショナルに見えるようにすることができます。次に誰かが Excel ファイルを渡して PDF レポートを要求したときに、何をすべきか正確にわかります。

## よくある質問

### テーブルをさらにカスタマイズできますか?
もちろんです! 色、フォント、配置を変更したり、特定のセルに境界線を追加したりすることもできます。

### Aspose.PDF for .NET は無料ですか?
無料トライアルを提供していますが、長期間使用するにはライセンスが必要です。[ここで購入](https://purchase.aspose.com/buy).

### 特定の行と列のみをエクスポートできますか?
はい、パラメータを変更することができます。`ExportDataTable`特定の範囲をエクスポートする方法。

### これは大きな Excel ファイルでも機能しますか?
はい、Aspose.Cells は大きな Excel ファイルを効率的に処理できるように設計されています。

### PDF にページを追加するにはどうすればよいですか?
使用できます`pdfDocument.Pages.Add()`必要な数だけページを追加します。