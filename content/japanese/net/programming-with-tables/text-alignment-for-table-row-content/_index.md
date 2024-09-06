---
title: 表の行コンテンツのテキスト配置
linktitle: 表の行コンテンツのテキスト配置
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF テーブル内の行コンテンツを揃える方法を学習します。
type: docs
weight: 210
url: /ja/net/programming-with-tables/text-alignment-for-table-row-content/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントの表の行の内容を揃える方法を段階的に説明します。提供されている C# ソース コードについて説明し、実装方法を示します。

## ステップ1: PDFドキュメントの作成
まず、PDF ドキュメントを作成します。

```csharp
var dataDir = "YOUR DOCUMENTS DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## ステップ2: テーブルの初期化
次に、テーブルを初期化します。

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## ステップ3: テーブルの境界線の色を設定する
テーブルの境界線の色を設定します。

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## ステップ4: 表のセルの境界線を構成する
テーブルセルの境界線を設定します。

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## ステップ5: ループしてテーブルに10行追加する
ここで、ループを使用してテーブルに 10 行を追加します。

```csharp
for (int row_count = 0; row_count < 10; row_count++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row.VerticalAlignment = VerticalAlignment.Center;

     row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
     row.Cells.Add("Column("+row_count+",2)");
     row.Cells.Add("Column("+row_count+",3)");
}
```

## ステップ6: 垂直線の位置合わせを構成する
表の行の垂直方向の配置を設定します。

```csharp
row.VerticalAlignment = VerticalAlignment.Center;
```

## ステップ7: 行セルにコンテンツを追加する
行セルにコンテンツを追加します。

```csharp
row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
row.Cells.Add("Column("+row_count+",2)");
row.Cells.Add("Column("+row_count+",3)");
```

## ステップ8: ドキュメントページにテーブルを追加する
次に、ドキュメント ページにテーブルを追加してみましょう。

```csharp
Page tocPage = doc.Pages.Add();
tocPage.Paragraphs.Add(table);
```

## ステップ9: PDF文書を保存する
最後に、PDF ドキュメントを保存します。

```csharp
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

### Aspose.PDF for .NET を使用したテーブル行コンテンツのテキスト配置のサンプル ソース コード

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

//PDFドキュメントを作成
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
//テーブルの新しいインスタンスを初期化します
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
//テーブルの境界線の色をLightGrayに設定する
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
//表のセルの境界線を設定する
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
//10行を追加するループを作成する
for (int row_count = 0; row_count < 10; row_count++)
{
	//テーブルに行を追加する
	Aspose.Pdf.Row row = table.Rows.Add();
	row.VerticalAlignment = VerticalAlignment.Center;

	row.Cells.Add("Column (" + row_count + ", 1)" + DateTime.Now.Ticks);
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
Page tocPage = doc.Pages.Add();
//入力ドキュメントの最初のページにテーブルオブジェクトを追加します
tocPage.Paragraphs.Add(table);
//テーブルオブジェクトを含む更新されたドキュメントを保存する
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

## 結論
おめでとうございます。Aspose.PDF for .NET を使用して PDF ドキュメント内の表の行の内容を揃える方法を学習しました。このステップ バイ ステップ ガイドでは、ドキュメントの作成、表の初期化、境界線と配置の構成、コンテンツの追加、PDF ドキュメントの保存の方法を説明しました。これで、この知識を自分のプロジェクトに適用できます。

### よくある質問

#### Q: 表のセルの内容を水平に揃えるにはどうすればよいですか?

 A: 表のセルの内容を水平方向に揃えるには、`HorizontalAlign`細胞の特性`TextState`オブジェクト。例えば、テキストを中央揃えにするには、`cell.TextState.HorizontalAlignment = HorizontalAlignment.Center`設定することもできます`HorizontalAlignment.Left`または`HorizontalAlignment.Right`それぞれ左揃えと右揃えです。

#### Q: テーブル内の個々のセルに異なる境界線のスタイルと色を適用できますか?

 A: はい、表内の個々のセルに異なる境界線のスタイルと色を適用できます。特定のセルの境界線をカスタマイズするには、`cell.Border`不動産を新しいものに`BorderInfo`境界線の側面、幅、色など、必要な設定でオブジェクトを作成します。

#### Q: セル内の表コンテンツの垂直方向の配置を調整するにはどうすればよいですか?

 A: セル内の表コンテンツの垂直方向の配置は、`VerticalAlignment`行のプロパティ`VerticalAlignment.Center`, `VerticalAlignment.Top`、 または`VerticalAlignment.Bottom`このプロパティは、その行内のすべてのセルの垂直方向の配置を制御します。

#### Q: テーブルに列や行を動的に追加することは可能ですか?

 A: はい、テーブルに列や行を動的に追加することができます。`table.Rows.Add()`新しい行を追加する方法と`row.Cells.Add()`行に新しいセルを追加するメソッド。これはループ内で実行することも、特定の要件に基づいて実行することもできます。

#### Q: 特定のセルまたは表全体の背景色を設定するにはどうすればよいですか?

 A: 特定のセルまたは表全体の背景色を設定するには、`BackgroundColor`の財産`Cell`または`Table`オブジェクト。例えば、セルの背景色を設定するには、`cell.BackgroundColor = Aspose.Pdf.Color.LightBlue`.