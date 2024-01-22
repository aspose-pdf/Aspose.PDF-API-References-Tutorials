---
title: ウィンドウに自動フィット
linktitle: ウィンドウに自動フィット
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用し、PDF 生成でウィンドウに自動調整するためのステップバイステップ ガイド。
type: docs
weight: 50
url: /ja/net/programming-with-tables/auto-fit-to-window/
---
次の記事は、提供されている C# ソース コードを使用して、.NET 用の Aspose.PDF ライブラリを使用してウィンドウに自動調整する機能を実現する方法についてのステップバイステップ ガイドです。 Auto Fit To Window 機能を使用すると、表示するウィンドウに合わせたレイアウトで PDF ファイルを生成できます。この機能は、ユーザーが使用する PDF リーダー ウィンドウのサイズに合わせて PDF ドキュメントを自動的に調整する場合に特に便利です。

## ステップ 1: 環境のセットアップ

始める前に、.NET 用の Aspose.PDF ライブラリをマシンにインストールする必要があります。また、必要な名前空間をプロジェクトにインポートしてください。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: PDF ドキュメントの作成

始めるには、`Document`デフォルトのコンストラクターを呼び出してオブジェクトを作成します。

```csharp
Document doc = new Document();
```

次に、セクションを作成します。`Pdf`物体。

```csharp
Page sec1 = doc.Pages.Add();
```

## ステップ 3: ドキュメントに表を追加する

このステップでは、PDF ドキュメントに表を追加します。まず、`Table`物体。

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

次に、テーブルをセクションの段落コレクションに追加します。

```csharp
sec1.Paragraphs.Add(tab1);
```

##  ステップ 4: テーブルの外観をカスタマイズする

セルの境界線や余白などのプロパティを設定することで、表の外観をカスタマイズできます。

```csharp
tab1. ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);

Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin.Right = 5f;
margin. Bottom = 5f;

tab1. DefaultCellPadding = margin;
```

##  ステップ 4: テーブルに行とセルを追加する

次に、テーブルに行とセルを追加しましょう。まず行を作成し、その行にセルを追加します。

```csharp
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");

Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
```

## ステップ 5: ドキュメントを保存する

最後に、出力ファイルのパスを指定してドキュメントを保存します。

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
doc.Save(dataDir);
```

### Aspose.PDF for .NET を使用した Auto Fit To Window のソース コード例

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//空のコンストラクターを呼び出して Pdf オブジェクトをインスタンス化します。
Document doc = new Document();
// PDF オブジェクトにセクションを作成する
Page sec1 = doc.Pages.Add();

//テーブルオブジェクトをインスタンス化する
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
//目的のセクションの段落コレクションに表を追加します
sec1.Paragraphs.Add(tab1);

//テーブルの列幅で設定します
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

//BorderInfo オブジェクトを使用してデフォルトのセル境界線を設定する
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

//別のカスタマイズされた BorderInfo オブジェクトを使用してテーブルの境界線を設定する
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
//MarginInfo オブジェクトを作成し、その左、下、右、上マージンを設定します。
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;

//デフォルトのセルパディングを MarginInfo オブジェクトに設定します。
tab1.DefaultCellPadding = margin;

//テーブルに行を作成し、その行にセルを作成します。
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");

dataDir = dataDir + "AutoFitToWindow_out.pdf";
//テーブルオブジェクトを含む更新されたドキュメントを保存する
doc.Save(dataDir);
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して、ウィンドウに自動調整機能を備えた PDF ファイルを生成する方法を学びました。この機能は、PDF ドキュメントを表示ウィンドウのサイズに自動的に調整する場合に非常に便利です。 Aspose.PDF for .NET は、PDF ファイルを生成および操作するための他の多くの強力な機能を提供します。このライブラリをさらに探索して、そのすべての機能を発見することをお勧めします。

### よくある質問

#### Q: PDF 生成における [ウィンドウに自動調整] 機能の目的は何ですか?

A: PDF 生成の [ウィンドウに自動調整] 機能により、PDF ドキュメントのレイアウトがユーザーが使用する PDF リーダー ウィンドウのサイズに自動的に調整されます。これにより、表示が向上し、利用可能な表示領域内にコンテンツが完全に収まるようになります。

#### Q: フォントのサイズや色など、表の外観をカスタマイズできますか?

A: はい、Aspose.PDF for .NET を使用して PDF ドキュメント内の表の外観をカスタマイズできます。提供されているコード スニペットは、セルの境界線、余白、列幅などのプロパティを設定する方法を示しています。表とその内容のフォント サイズ、色、その他のスタイル設定をさらにカスタマイズできます。

#### Q: Aspose.PDF for .NET を C# プロジェクトに統合するにはどうすればよいですか?

A: C# プロジェクトで Aspose.PDF for .NET を使用するには、まずマシンに .NET 用の Aspose.PDF ライブラリをインストールする必要があります。次に、C# プロジェクトのライブラリへの参照を追加できます。最後に、Aspose.PDF for .NET によって提供されるクラスとメソッドにアクセスするために必要な名前空間をインポートします。

#### Q: Aspose.PDF for .NET は .NET Core アプリケーションと互換性がありますか?

A: はい、Aspose.PDF for .NET は .NET Core アプリケーションと互換性があります。 .NET Framework、.NET Core、.NET 5.0+ など、さまざまな .NET プラットフォームをサポートします。

#### Q: PDF ドキュメントにさらに表を追加できますか?

A: はい、コード スニペットで示されているのと同様の手順に従って、PDF ドキュメントに複数の表を追加できます。の新しいインスタンスを作成するだけです。`Aspose.Pdf.Table`クラスを作成し、PDF ドキュメントの別のセクションまたはページに追加します。