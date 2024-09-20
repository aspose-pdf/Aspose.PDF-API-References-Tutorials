---
title: テーブルセルのスタイル
linktitle: テーブルセルのスタイル
second_title: Aspose.PDF for .NET API リファレンス
description: この詳細なチュートリアルでは、Aspose.PDF for .NET を使用して PDF 内のテーブル セルにスタイルを設定する方法を説明します。指示に従って、美しい PDF テーブルを作成し、書式設定します。
type: docs
weight: 160
url: /ja/net/programming-with-tagged-pdf/style-table-cell/
---
## 導入

プロフェッショナルな PDF テーブルを作成するのは難しい場合がありますが、Aspose.PDF for .NET を使用すると、驚くほど簡単に作成できます。ヘッダー、フッター、または特定のテーブル セルのスタイルを設定する場合でも、この強力なライブラリには、美しくフォーマットされた PDF ドキュメントを作成するために必要なすべてのツールが用意されています。このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントのテーブル セルのスタイルを設定する方法について説明します。心配しないでください。すべてをわかりやすい手順に分解します。

## 前提条件

コードに進む前に、次の前提条件を満たしていることを確認してください。

1. Aspose.PDF for .NET: Aspose.PDFの最新バージョンをダウンロードしてインストールします。[ここ](https://releases.aspose.com/pdf/net/).
2. IDE (Visual Studio など): .NET 開発環境をセットアップします。
3. C# プログラミングの基礎知識: C# に関する多少の知識が必要です。
4.  Aspose.PDFライセンス: 一時ライセンスまたはフルライセンスを取得して、ライブラリの全機能をロック解除します。無料トライアルを入手できます。[ここ](https://purchase.aspose.com/temporary-license/).

## パッケージのインポート

始める前に、必要な名前空間をインポートしてください。プロジェクトには次のものが必要です。

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

すべての設定が完了したら、ステップバイステップのガイドに進みましょう。

PDF ドキュメントに表を作成し、そのセルにスタイルを設定します。各ステップでプロセスを詳しく説明します。

## ステップ1: 新しいPDFドキュメントを作成する

最初のステップは、新しいPDFドキュメントを作成することです。Aspose.PDFでは、新しい`Document`PDF ファイルを表すオブジェクト。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//新しいPDF文書を作成する
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");
```

ここでは、PDF ドキュメントを初期化し、タイトルと言語を設定します。これにより、ドキュメントに適切な構造が与えられ、PDF/UA 準拠に不可欠なものになります。

## ステップ2: テーブル構造を設定する

PDF 内の表は構造要素内で定義されます。表を作成し、表の行と列を定義しましょう。

```csharp
//ルート構造要素を取得する
StructureElement rootElement = taggedContent.RootElement;

//テーブル構造要素を作成する
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

これでテーブルのヘッダーが定義されました（`TableTHeadElement`）、 体 （`TableTBodyElement`）、足（`TableTFootElement`) セクション。これらはテーブルの骨組みと考えることができます。

## ステップ3: ヘッダーセルのスタイルを設定する

ヘッダー セルにスタイルを設定すると、目立つようになります。ここでは、背景色、境界線、テキストの配置を適用します。

```csharp
int colCount = 4;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
    thElement.BackgroundColor = Color.GreenYellow;
    thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
    thElement.IsNoBorder = true;
    thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
    thElement.Alignment = HorizontalAlignment.Right;
}
```

このステップでは、各ヘッダー セルをループして、緑がかった黄色の背景、灰色の境界線、右揃えのテキストを設定します。これらのプロパティを調整して、希望するデザインに合わせることができます。

## ステップ4: テーブル本体にデータを入力してスタイルを設定する

表の本体には実際のデータが含まれています。ここでは、特定の余白、境界線、テキスト設定を使用して各セルのスタイルを設定する方法を説明します。

```csharp
int rowCount = 4;

for (int rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = $"Row {rowIndex}";

    for (int colIndex = 0; colIndex < colCount; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
        tdElement.BackgroundColor = Color.Yellow;
        tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
        tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
        tdElement.Alignment = HorizontalAlignment.Center;
        
        TextState cellTextState = new TextState();
        cellTextState.ForegroundColor = Color.DarkBlue;
        cellTextState.FontSize = 7.5F;
        cellTextState.FontStyle = FontStyles.Bold;
        cellTextState.Font = FontRepository.FindFont("Arial");
        tdElement.DefaultCellTextState = cellTextState;
    }
}
```

このステップでは、表の本体を4行にし、各セルの背景を黄色、中央揃えの太字の青い文字でスタイル設定します。`MarginInfo`テキストの周囲のパディングを定義するクラス。

## ステップ5: フッターのスタイルを設定する

テーブルに完全な構造を与えるために、ヘッダーの場合と同じように、フッター セルを追加してスタイルを設定します。

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText($"Foot {colIndex}");
}
```

フッター セクションはヘッダーと同様のスタイルになっているため、読者は表の構造を簡単に理解できます。

## ステップ6: PDFドキュメントを保存して検証する

最後に、PDF ドキュメントを保存し、PDF/UA に準拠しているかどうかを確認します。

```csharp
//タグ付けされたPDF文書を保存する
document.Save(dataDir + "StyleTableCell.pdf");

// PDF/UA準拠の確認
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

PDFを保存し、`Validate`アクセシビリティ標準 (PDF/UA 準拠) を満たしていることを確認する方法。

## 結論

Aspose.PDF for .NET を使用した PDF の表のスタイル設定は強力かつ柔軟です。数行のコードで、PDF ドキュメントを目立たせるカスタム表デザインを作成できます。セルの境界線や背景のカスタマイズからアクセシビリティ準拠の確保まで、Aspose.PDF を使用すると、洗練された PDF ファイルを簡単に作成できます。

## よくある質問

### 個々のテーブルセルに異なるスタイルを適用できますか?  
はい、カスタマイズすることで個々のセルにスタイルを設定できます。`TableTDElement`プロパティ。

### 表のセルを結合するにはどうすればいいですか?  
あなたは`ColSpan`そして`RowSpan`表内のセルを結合するためのプロパティ。

### PDF/UA 準拠の表を作成することは可能ですか?  
はい、このガイドで説明されているように、次の方法でドキュメントを検証することでPDF/UA準拠を確保できます。`Validate`方法。

### 表のセルに異なるフォントを使用できますか?  
もちろんです！`TextState`各セルのオブジェクト。

### Aspose.PDF for .NET をダウンロードするにはどうすればいいですか?  
ダウンロードはこちらから[リリースページ](https://releases.aspose.com/pdf/net/).