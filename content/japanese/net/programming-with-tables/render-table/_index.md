---
title: PDF ドキュメントで表をレンダリングする
linktitle: PDF ドキュメントで表をレンダリングする
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用してテーブルをレンダリングすることで、プロフェッショナルな PDF を簡単に作成できます。ドキュメント生成をマスターするには、ステップ バイ ステップ ガイドに従ってください。
type: docs
weight: 170
url: /ja/net/programming-with-tables/render-table/
---
## 導入

プログラムでプロフェッショナルな PDF を作成するのは大変な作業のように思えるかもしれませんが、Aspose.PDF for .NET を使用すると、簡単に作成できます。レポート、請求書、または表形式のデータを必要とするその他のドキュメント タイプを作成する場合でも、Aspose.PDF には必要なツールが用意されています。このチュートリアルでは、PDF ドキュメントで表をレンダリングする方法を段階的に説明します。最後には、表の操作方法、ページ プロパティの管理方法、PDF ファイルを簡単に保存する方法をしっかりと理解できるようになります。

## 前提条件

コードに進む前に、必要なものは次のとおりです。

-  Visual Studio: お使いのマシンにVisual Studioがインストールされていることを確認してください。ダウンロードできます。[ここ](https://visualstudio.microsoft.com/downloads/).
-  Aspose.PDF for .NET: Aspose.PDFライブラリは、[Aspose リリースページ](https://releases.aspose.com/pdf/net/).
- C# の基礎知識: C# の基礎を理解すると、より理解しやすくなります。
- .NET Framework: 理想的には、互換性のある .NET 環境で作業していることを確認します。

これらの前提条件を設定したら、PDF ドキュメントの作成を開始する準備が整います。

## パッケージのインポート

C# ファイルの先頭で、必要な Aspose.PDF 名前空間をインポートする必要があります。これにより、プロジェクトでライブラリ機能を利用できるようになります。

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

プロジェクトにAspose.PDFライブラリへの必要な参照を追加したことを確認してください。NuGetを使用している場合は、検索するだけで簡単に追加できます。`Aspose.PDF`.

これですべての設定が終わったので、PDF ドキュメントでテーブルをレンダリングするためのプロセスを管理しやすいステップに分解してみましょう。心配しないでください。各ステップをわかりやすい説明で説明します。

## ステップ1: ドキュメントとページ情報を設定する

まず最初に、新しいドキュメントを作成し、そのページ設定を構成する必要があります。手順は次のとおりです。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo.Left = 37;
marginInfo.Right = 37;
marginInfo.Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;
```

説明： 
- まず、ドキュメントを保存する場所を定義します（`dataDir`）。 
- 次に、新しいインスタンスを作成します。`Document`クラス。 
- ページの余白を設定して、表の周囲に余裕のあるスペースを作ります。
- 最後に、ドキュメントを横向きに設定します。これは、幅の広い表を表示するときに役立ちます。

## ステップ2: 最初のテーブルを作成する

次に、最初のテーブルを作成し、サンプル データを入力します。

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "50 100"; //列幅を定義する
```

説明: ここでは、`Table`クラスを作成し、列の幅を設定します。最初の列の幅は 50 単位、2 番目の列の幅は 100 単位になります。

## ステップ3: テーブルに行を入力する

次に、ループでテーブルに行を追加してみましょう。

```csharp
Page curPage = doc.Pages.Add(); //新しいページを追加する
for (int i = 1; i <= 120; i++)
{
    Aspose.Pdf.Row row = table.Rows.Add();
    row.FixedRowHeight = 15; //行の高さを固定する
    
    Aspose.Pdf.Cell cell1 = row.Cells.Add();
    cell1.Paragraphs.Add(new TextFragment("Content 1"));
    
    Aspose.Pdf.Cell cell2 = row.Cells.Add();
    cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
```

説明： 
- ここで、テーブルを追加するための新しいページを作成します。
- 私たちは`for`ループしてテーブルに 120 行を追加します。各行の高さは 15 単位に固定されています。
- 各行内に 2 つのセルを追加し、テキストを入力します。

## ステップ4: ページに最初のテーブルを追加する

テーブルにデータを入力し終えたら、それを現在のページに追加します。

```csharp
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs.Add(table);
```

説明: この手順では、作成した表を現在のページの段落に追加し、PDF ドキュメントで表が表示されるようにします。

## ステップ5: 2番目のテーブルを作成する

次に、異なるコンテンツを含む 2 番目のテーブルを作成し、それを新しいページに追加します。

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
    Aspose.Pdf.Row row = table1.Rows.Add();
    Aspose.Pdf.Cell cell1 = row.Cells.Add();
    cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
    
    Aspose.Pdf.Cell cell2 = row.Cells.Add();
    cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true; // 2番目のテーブルを新しいページに表示するように設定する
paragraphs.Add(table1);
```

説明： 
- このコード スニペットは、幅が 100 単位の 2 つの列を持つ新しいテーブルを作成します。
- あ`for`ループはサンプルコンテンツを含む 10 行を追加します。
- 設定により`table1.IsInNewPage` true に設定すると、このテーブルが新しいページに表示されるようになり、整理された状態が保たれます。

## ステップ6: ドキュメントを保存する

テーブルの準備ができたので、ドキュメントを保存しましょう。

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);
```

説明: ファイル名を指定して、定義したディレクトリにドキュメントを保存します。このコードを実行すると、次のタイトルのPDFファイルが作成されます。`IsNewPageProperty_Test_out.pdf`指定した場所に作成されます。

## ステップ7: 確認メッセージ

最後に、すべてがスムーズに動作したことをユーザーに知らせるために、わかりやすいコンソール メッセージを追加します。

```csharp
Console.WriteLine("\nTable rendered successfully on a page.\nFile saved at " + dataDir);
```

説明: これは、操作が成功したことと、ユーザーが新しい PDF ファイルを見つけることができる場所を確認するための簡単な方法です。

## 結論

これで完了です。Aspose.PDF for .NET を使用して、PDF ドキュメントにテーブルをレンダリングできました。わずか数行のコードで、大量のデータを整理された形式で処理および表示できるため、情報量が多く、見た目も魅力的なドキュメントを作成できます。在庫リスト、財務レポート、教育ドキュメントなど、どのような作業であっても、テーブルは複雑な情報を一目で伝える優れた方法です。

## よくある質問

### Aspose.PDF の表の外観をカスタマイズできますか?  
もちろんです! 色、境界線、フォント スタイル、その他のプロパティを調整して、表の外観を向上させることができます。

### Aspose.PDF は無料で使用できますか?  
 Aspose.PDFは無料試用版を提供していますが、商用利用には購入が必要です。価格を確認するには[ここ](https://purchase.aspose.com/buy).

### Aspose.PDF の問題に関するサポートを受けるにはどうすればよいですか?  
Asposeサポートフォーラムから支援を求めることができます[ここ](https://forum.aspose.com/c/pdf/10).

### 無料試用版には制限はありますか？  
はい、試用版には、生成されたドキュメントに透かしを入れるなどの制限がある場合があります。完全な機能を使用するには、一時ライセンスの取得を検討してください。[ここ](https://purchase.aspose.com/temporary-license/).

### Aspose.PDF の機能に関する詳細情報はどこで入手できますか?  
利用可能な包括的なドキュメントを調べることができます[ここ](https://reference.aspose.com/pdf/net/).