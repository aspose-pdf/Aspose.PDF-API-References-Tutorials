---
title: PDF ファイル内の画像の周囲にテキストを配置する
linktitle: PDF ファイル内の画像の周囲にテキストを配置する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF 内の画像の周囲にテキストを配置する方法を学びます。ステップ バイ ステップ ガイドに従って、画像とテキストを並べて配置したプロフェッショナルな PDF を作成します。
type: docs
weight: 260
url: /ja/net/programming-with-text/placing-text-around-image/
---
## 導入

PDF ファイル内の画像の周囲にテキストを配置しようとしたけれど、難しいと感じたことはありませんか? もしそうなら、ここが正解です! Aspose.PDF for .NET を使用すると、このプロセスが簡単になり、数行のコードで画像の周囲にテキストを配置できます。レポート、ドキュメント、プレゼンテーションのいずれを作成する場合でも、この機能はコンテンツのレイアウトを強化し、視覚的に魅力的にするための優れた方法です。今日は、Aspose.PDF for .NET を使用して PDF ドキュメント内の画像の周囲にテキストを配置する方法について説明します。

## 前提条件

コードに進む前に、すべてがセットアップされていることを確認しましょう。必要なものは次のとおりです。

-  Aspose.PDF for .NET: ダウンロードはこちらから[ここ](https://releases.aspose.com/pdf/net/).
- Visual Studio: スムーズに進めるために、最新バージョンがインストールされていることを確認してください。
- .NET Framework: この例では .NET を使用するため、環境が .NET 開発用に設定されていることを確認してください。
- 一時ライセンス：一時ライセンスを申請することができます[ここ](https://purchase.aspose.com/temporary-license/)製品を評価する場合。

Aspose.PDF for .NETをまだセットアップしていない場合は、[ドキュメント](https://reference.aspose.com/pdf/net/).

## 名前空間のインポート

コーディングを始める前に、必要な名前空間をインポートする必要があります。これを行うためのコード スニペットは次のとおりです。

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

これらの名前空間は、次のようなクラスへのアクセスを提供するため不可欠です。`Document`, `Page`, `Image` 、 そして`HtmlFragment`これを使用して PDF を作成および操作します。

準備ができたので、Aspose.PDF for .NET を使用して PDF ファイル内の画像の周囲にテキストを配置する方法を詳しく説明します。手順を追って説明します。

## ステップ1: ドキュメントオブジェクトのインスタンスを作成する

まず、PDFドキュメントを作成する必要があります。Aspose.PDFでは、`Document`オブジェクト。このオブジェクトは、追加するすべてのコンテンツの基盤として機能します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

ここでは、空の PDF ドキュメントを作成しました。まだページはありませんが、心配しないでください。次の手順でページを追加します。

## ステップ2: ドキュメントにページを追加する

ドキュメントが完成したら、次はページを追加します。これは、コンテンツを追加する空白の紙を作成するようなものと考えてください。

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

このコードは、ドキュメントに新しいページを追加します。デフォルトではページは空白ですが、これを変更します。

## ステップ3: コンテンツを整理するための表を作成する

画像とテキストを適切に配置するには、表を使用します。PDF 内の表は、Word 文書や HTML と同様に、レイアウトの構造化に役立ちます。

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

このスニペットは表を作成し、それをページに追加します。表は、画像とテキストを配置するためのフレームワークと考えてください。

## ステップ4: テーブルの列幅を設定する

テーブルを追加したので、列の幅を定義する必要があります。これにより、ページ上の画像とテキストのサイズが適切になります。

```csharp
table1.ColumnWidths = "120 270";
```

この行は、画像用とテキスト用の 2 つの列の幅を設定します。画像またはテキストに必要なスペースが増減する場合は、これらの値を調整します。

## ステップ5: 余白とパディングを定義する

すべてがきれいに見えるように、テーブルに余白とパディングを追加しましょう。

```csharp
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
table1.DefaultCellPadding = margin;
```

これらの設定により、テーブルの間隔が一定になり、コンテンツの視覚的な魅力が向上します。

## ステップ6: 表に画像を挿入する

さて、楽しい部分、つまり画像の追加に取り掛かりましょう。今回は Aspose のロゴを追加しますが、好きな画像を自由に使用してください。

```csharp
Aspose.Pdf.Row row1 = table1.Rows.Add();
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

何が起こっているか見てみましょう:
- 指定されたディレクトリから画像を読み込みます。
- 画像の高さと幅を設定します。
- 最後に、テーブルの最初のセルに画像を追加します。

## ステップ7: 画像の横にテキストを追加する

画像を配置したら、その横にテキストを追加しましょう。この例では、HTML 形式のテキストを使用してコンテンツのスタイルを設定します。

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF document reporting component that enables .NET applications to <b>create PDF documents from scratch</b> without utilizing Adobe Acrobat.</font>";

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

このブロックは、画像の横のセル内にスタイル設定されたタイトルと説明を追加します。HTML タグを使用してテキストをフォーマットし、さらにカスタマイズすることができます。

## ステップ8: 垂直方向の配置を調整する

デフォルトでは、表のセルのコンテンツは希望どおりに配置されない場合があります。この場合、テキストがセルの上部に揃えられるようにする必要があります。

```csharp
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
```

これにより、テキストがセルの上部に配置され、レイアウトがすっきりとプロフェッショナルに保たれます。

## ステップ9: 画像と説明の下にテキストを追加する

画像とテキストの下にさらにコンテンツを追加したい場合があります。そのために、テーブルに別の行を追加しましょう。

```csharp
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
SecondRow.Cells[0].ColSpan = 2;
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

ここでは、レイアウトのバランスを保つために、両方の列にまたがる追加のテキストを含む別の行を追加しました。

## ステップ10: PDFドキュメントを保存する

最後に、変更内容を確認できるようにドキュメントを保存する必要があります。

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

これにより、画像とテキストが希望どおりにフォーマットされた PDF が保存されます。

## 結論

PDF 内の画像の周囲にテキストを配置するのは大変な作業のように思えるかもしれませんが、Aspose.PDF for .NET を使用すると、そのプロセスが簡単になります。表、画像、スタイル設定されたテキストを活用することで、最小限の労力でプロフェッショナルな外観の PDF を作成できます。わずか数行のコードで、コンテンツを必要な場所に正確に配置できるため、ドキュメントは洗練された整理された外観になります。

## よくある質問

### この方法を使用して、テキスト付きの複数の画像を配置できますか?
はい、表に行とセルを追加するだけで、追加の画像やテキストを含めることができます。

### 画像の配置を変更できますか?
もちろんです! セルの配置プロパティを調整することで、画像の配置を変更できます。

### テキストのスタイルをさらに変更するにはどうすればよいですか?
 HTMLタグは`HtmlFragment`オブジェクトに太字、斜体、さまざまなフォントなどのさまざまなスタイルを適用します。

### テキストと画像の間の間隔を制御できますか?
はい、`MarginInfo`オブジェクトを使用すると、要素間のパディングとマージンを制御できます。

### テキストにリンクを追加することは可能ですか?
もちろんです！HTML形式のテキストにハイパーリンクを埋め込むには、`<a>`タグ。