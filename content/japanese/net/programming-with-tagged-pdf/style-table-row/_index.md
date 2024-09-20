---
title: スタイルテーブル行
linktitle: スタイルテーブル行
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF 内のテーブル行にスタイルを設定する方法をステップバイステップ ガイドで学習し、ドキュメントの書式設定を簡単に強化します。
type: docs
weight: 180
url: /ja/net/programming-with-tagged-pdf/style-table-row/
---
## 導入

構造がしっかりしていて、美しくフォーマットされた PDF ドキュメントを作成する場合、Aspose.PDF for .NET は頼りになるソリューションです。レポートや請求書を自動化する場合や、動的なテーブルを作成する場合など、さまざまなスタイルでテーブルをフォーマットすることが、洗練されたドキュメントを作成するための鍵となります。このチュートリアルでは、Aspose.PDF for .NET を使用してテーブル行のスタイルを設定する方法を詳しく説明します。コーヒーを飲みながらの楽しい会話のように、ステップ バイ ステップでガイドしますので、ご安心ください。

## 前提条件

細かい点に入る前に、準備が整っていることを確認しましょう。必要なものは次のとおりです。

1. Aspose.PDF for .NET ライブラリ  
   まだお持ちでない場合は、こちらから入手できます。[ここ](https://releases.aspose.com/pdf/net/) . また、[無料トライアル](https://releases.aspose.com/)始めましょう。
2. 開発環境  
   Visual Studio または任意の C# IDE をセットアップします。.NET もインストールする必要がありますが、すでに使い慣れていると思います。
3. C# と .NET の基礎知識  
   C# をよく理解していれば、このチュートリアルは簡単に理解できます。でも心配しないでください。各ステップを詳しく説明します。

## パッケージのインポート

Aspose.PDF の使用を開始する前に、必要な名前空間をインポートする必要があります。C# プロジェクトに、次の内容が含まれていることを確認してください。

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

これらは、テーブルを作成してスタイルを設定するために、そしてもちろん、コンプライアンスのためにタグ付けされたコンテンツを操作するために不可欠です。

それでは、タスクをステップごとに分解して、プロのようにテーブル行のスタイルを設定できるようにしましょう。

## ステップ1: 新しいPDFドキュメントを作成する

まず最初に、新しい PDF ドキュメントを作成しましょう。このドキュメントには、スタイル設定されたすべてのテーブル行が含まれます。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//ドキュメントを作成
Document document = new Document();
```

ここでは、単に新しい`Document`PDF ファイルを表すオブジェクトです。出力ファイルを保存するディレクトリ パスを必ず設定してください。

## ステップ2: タグ付けされたコンテンツを操作する

アクセシビリティのために PDF を構造化するには、タグ付きコンテンツを扱います。これにより、表などの構造化要素を作成し、PDF/UA などのアクセシビリティ標準に準拠させることができます。

```csharp
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");
```

ここでは、PDF のタグ付けされたコンテンツのタイトルと言語を設定しています。これは、PDF に名前を付けて、どの言語で話すかを指示するようなものです。

## ステップ3: テーブル構造を定義する

次に、これから作成する表の構造を定義しましょう。すべての表には、ヘッダー、本文、フッターが必要です。よく整理されたブログ投稿とよく似ています。

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

ここで行っているのは、ヘッダー付きのテーブルを作成することです（`THead`）、 体 （`TBody`）、フッター（`TFoot`）。これらの要素が行を保持します。

## ステップ4: テーブルヘッダー行を追加する

ヘッダーのない表はタイトルのない本のようなものです。まずはデータのコンテキストを提供するためにヘッダー行を作成しましょう。

```csharp
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText(String.Format("Head {0}", colIndex));
}
```

ここでは、ループして3つのヘッダーセルを追加します（`TableTHElement`）、それぞれに説明文を付けます。簡単ですよね？

## ステップ5: スタイル設定された本文行を追加する

次は楽しい部分、つまり行のスタイル設定です。カスタム スタイルで 7 つの行を作成しましょう。背景色、境界線、パディング、テキストの配置を設定します。

```csharp
for (int rowIndex = 0; rowIndex < 7; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = String.Format("Row {0}", rowIndex);
    trElement.BackgroundColor = Color.LightGoldenrodYellow;
    trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
    trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
    trElement.MinRowHeight = 100.0;
    trElement.FixedRowHeight = 120.0;
    trElement.IsInNewPage = (rowIndex % 3 == 1);
    trElement.IsRowBroken = true;

    for (int colIndex = 0; colIndex < 3; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
    }
}
```

- 背景色: プロフェッショナルでありながら温かみのある雰囲気を出すために、明るいゴールデンロッドイエローを使用しました。
- 境界線: 各行には濃い灰色の外側の境界線と青いセルの境界線が付けられ、シャープな外観になります。
- 高さとパディング: 行の高さが設定され、すっきりとした外観になるようにパディングが追加されます。
- ページ区切り: 表を読みやすくするために、2 行ごとに新しいページが始まります。

## ステップ6: フッター行を追加する

ヘッダーと同様に、フッターはテーブルを固定します。フッターを作成しましょう。

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText(String.Format("Foot {0}", colIndex));
}
```

3 つのフッター セルをループして、少しテキストを追加するだけです。フッターの代替テキストは、アクセシビリティを考慮して「Foot Row」にしています。

## ステップ7: PDFドキュメントを保存する

テーブルの準備ができたので、傑作を保存する時間です。

```csharp
document.Save(dataDir + "StyleTableRow.pdf");
```

このように、スタイルを設定した美しい表の行がすべて含まれた PDF が保存されます。

## ステップ8: PDF/UA準拠を検証する

当社の PDF がアクセシビリティ標準に準拠していることを確認するために、PDF/UA 準拠を検証します。

```csharp
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

これにより、PDF が PDF/UA 標準に準拠し、誰でもアクセスできるようになります。アクセシビリティこそが重要です。

## 結論

これで完了です。わずか数行のコードで、Aspose.PDF for .NET を使用して PDF に完全にスタイル設定された表を作成できました。ヘッダーからフッターまで、各行にスタイルを設定し、アクセシビリティ要素を追加し、ドキュメントのコンプライアンスを検証しました。企業レポートやプレゼンテーションを作成する場合でも、PDF を楽しむだけの場合でも、このガイドが役立ちます。さあ、プロのように表のスタイル設定を始めましょう。

## よくある質問

### 表のフォントスタイルも変更できますか?  
はい！フォントスタイルを変更するには、`TextState`各セルにオブジェクトがあり、完全なカスタマイズが可能です。

### テーブルに列を追加するにはどうすればよいですか?  
調整するだけです`colCount`変数を追加し、ヘッダー、本文、フッターのループにセルを追加します。

### 行の高さを設定しないとどうなりますか?  
行の高さを設定しない場合、テーブルはコンテンツに基づいて自動的に調整されます。

### これを動的な行数に使用できますか?  
もちろんです! データベースやその他のソースからデータを取得し、行数と列数を動的に調整できます。

### Aspose.PDF for .NET は無料で使用できますか?  
 Aspose.PDF for .NETはライセンス製品ですが、[無料トライアル](https://releases.aspose.com/)または[一時ライセンス](https://purchase.aspose.com/temporary-license/).