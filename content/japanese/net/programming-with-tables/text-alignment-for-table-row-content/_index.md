---
title: 表の行コンテンツのテキストの配置
linktitle: 表の行コンテンツのテキストの配置
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF テーブルの行コンテンツを整列する方法を学びます。
type: docs
weight: 210
url: /ja/net/programming-with-tables/text-alignment-for-table-row-content/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントの表内の行の内容を整列する方法を段階的に説明します。提供されている C# ソース コードについて説明し、実装方法を示します。

## ステップ 1: PDF ドキュメントの作成
まず、PDF ドキュメントを作成します。

```csharp
var dataDir = "YOUR DOCUMENTS DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## ステップ 2: テーブルの初期化
次に、テーブルを初期化します。

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## ステップ 3: テーブルの境界線の色の設定
テーブルの境界線の色を設定します。

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## ステップ 4: 表のセルの境界線を構成する
表のセルの境界線を設定します。

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## ステップ 5: テーブルに 10 行を追加するループ
次に、ループを使用してテーブルに 10 行を追加します。

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

## ステップ 6: 垂直線の配置を構成する
テーブルの行の垂直方向の配置を構成します。

```csharp
row.VerticalAlignment = VerticalAlignment.Center;
```

## ステップ 7: 行セルにコンテンツを追加する
行セルにコンテンツを追加します。

```csharp
row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
row.Cells.Add("Column("+row_count+",2)");
row.Cells.Add("Column("+row_count+",3)");
```

## ステップ 8: ドキュメント ページに表を追加する
次に、テーブルをドキュメント ページに追加しましょう。

```csharp
Page tocPage = doc.Pages.Add();
tocPage.Paragraphs.Add(table);
```

## ステップ 9: PDF ドキュメントを保存する
最後に、PDF ドキュメントを保存します。

```csharp
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

### Aspose.PDF for .NET を使用したテーブル行コンテンツのテキスト配置のソース コード例

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

//PDFドキュメントの作成
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
//テーブルの新しいインスタンスを初期化します。
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
//テーブルの境界線の色を LightGray に設定します
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
//表のセルの境界線を設定する
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
//10行を追加するループを作成します
for (int row_count = 0; row_count < 10; row_count++)
{
	//テーブルに行を追加
	Aspose.Pdf.Row row = table.Rows.Add();
	row.VerticalAlignment = VerticalAlignment.Center;

	row.Cells.Add("Column (" + row_count + ", 1)" + DateTime.Now.Ticks);
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
Page tocPage = doc.Pages.Add();
//入力ドキュメントの最初のページにテーブル オブジェクトを追加します
tocPage.Paragraphs.Add(table);
//テーブルオブジェクトを含む更新されたドキュメントを保存する
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

## 結論
おめでとうございます！ Aspose.PDF for .NET を使用して、PDF ドキュメント内のテーブルの行の内容を整列する方法を学習しました。このステップバイステップのガイドでは、ドキュメントの作成、表の初期化、境界線と配置の構成、コンテンツの追加、PDF ドキュメントの保存の方法を説明しました。この知識を自分のプロジェクトに適用できるようになりました。

### よくある質問

#### Q: 表のセルの内容を水平方向に揃えるにはどうすればよいですか?

 A: 表のセルの内容を水平方向に整列するには、`HorizontalAlign`細胞の性質`TextState`物体。たとえば、テキストを中央揃えにするには、次を使用します。`cell.TextState.HorizontalAlignment = HorizontalAlignment.Center` 。に設定することもできます`HorizontalAlignment.Left`または`HorizontalAlignment.Right`それぞれ左揃えと右揃えに対応します。

#### Q: 表内の個々のセルに異なる境界線のスタイルと色を適用できますか?

 A: はい、表内の個々のセルに異なる境界線のスタイルと色を適用できます。特定のセルの境界線をカスタマイズするには、`cell.Border`プロパティを新しいものに`BorderInfo`境界線の辺、幅、色などの必要な設定を使用してオブジェクトを作成します。

#### Q: セル内の表のコンテンツの垂直方向の配置を調整するにはどうすればよいですか?

 A: セル内の表の内容の垂直方向の配置を調整するには、`VerticalAlignment`行のプロパティ`VerticalAlignment.Center`, `VerticalAlignment.Top`、 または`VerticalAlignment.Bottom`。このプロパティは、その行内のすべてのセルの垂直方向の配置を制御します。

#### Q: テーブルに列や行を動的に追加することはできますか?

 A: はい、テーブルに列と行を動的に追加するには、`table.Rows.Add()`新しい行を追加するメソッドと`row.Cells.Add()`新しいセルを行に追加するメソッド。これはループ内で行うことも、特定の要件に基づいて行うこともできます。

#### Q: 特定のセルまたはテーブル全体の背景色を設定するにはどうすればよいですか?

 A: 特定のセルまたはテーブル全体の背景色を設定するには、`BackgroundColor`の財産`Cell`または`Table`物体。たとえば、セルの背景色を設定するには、次を使用します。`cell.BackgroundColor = Aspose.Pdf.Color.LightBlue`.