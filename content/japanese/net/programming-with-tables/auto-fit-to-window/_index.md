---
title: ウィンドウに自動フィット
linktitle: ウィンドウに自動フィット
second_title: Aspose.PDF for .NET API リファレンス
description: この詳細なステップバイステップ ガイドでは、Aspose.PDF for .NET を使用してテーブルをウィンドウに自動的に合わせる方法を学習します。PDF で洗練された適切なサイズのテーブルを作成するのに最適です。
type: docs
weight: 50
url: /ja/net/programming-with-tables/auto-fit-to-window/
---
## 導入

PDF を扱う場合、表を扱うのが一般的ですが、それらの表をページの幅にぴったりと合わせる必要がある場合もあります。このチュートリアルでは、Aspose.PDF for .NET を使用して、表をウィンドウに自動的に合わせる方法について説明します。これにより、表が洗練されて整理され、オーバーフローや列の不均等などの問題を防ぐことができます。学習する準備はできましたか? さあ、始めましょう!

## 前提条件

ステップバイステップガイドに進む前に、いくつか必要なものがあります。

1. プロジェクトにAspose.PDF for .NETがインストールされていること。まだインストールしていない場合は、[ここからダウンロード](https://releases.aspose.com/pdf/net/)または探索する[無料試用版](https://releases.aspose.com/).
2. .NET プログラミングに関する基本的な理解。
3. システムに Visual Studio または .NET 対応の IDE がインストールされていること。

>  PS Aspose.PDFを制限なく使用するにはライセンスが必要であることを忘れないでください。[ここ](https://purchase.aspose.com/buy)または[一時ライセンス](https://purchase.aspose.com/temporary-license/)すべての機能を試すことができます。

## パッケージのインポート

コードに進む前に、必要な名前空間をインポートする必要があります。

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

これで準備は完了です。次は、Aspose.PDF for .NET を使用してテーブルをウィンドウに自動的に合わせる方法を理解するために、これをシンプルでわかりやすい手順に分解してみましょう。

## ステップ1: ドキュメントオブジェクトを初期化する

まず、PDF ドキュメントを作成する必要があります。このドキュメントは、ページや表を追加する空白のシートと考えてください。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//空のコンストラクタを呼び出してPdfオブジェクトをインスタンス化する
Document doc = new Document();
```
  
ここでは、`Document` Aspose.PDFのクラス。`dataDir`完了後に PDF が保存される場所です。

## ステップ2: ドキュメントにページを追加する

PDF ドキュメントにはページが必要ですよね? ページを追加してみましょう。

```csharp
// Pdfオブジェクトにセクション（ページ）を作成する
Page sec1 = doc.Pages.Add();
```
  
ドキュメントに新しいページを追加しました。`Pages.Add()`方法。これは、表を配置する新しいシートをドキュメントに追加するものと考えることができます。

## ステップ3: テーブルの作成と構成

次に、テーブルを作成し、ウィンドウ内に収まるように調整します。

```csharp
//テーブルオブジェクトをインスタンス化する
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
//希望するセクションの段落コレクションに表を追加します
sec1.Paragraphs.Add(tab1);
```
  
新しい`Table`オブジェクトを作成し、それをページの段落コレクションに追加しました。各 PDF ページには異なる段落を含めることができますが、ここでは表を段落として扱っています。

## ステップ4: 列幅を定義してウィンドウに自動調整する

次に、列の幅を設定し、テーブルがウィンドウに合わせて調整されることを確認します。

```csharp
//表の列幅を設定する
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
```
  
表の列幅を固定しましたが、`ColumnAdjustment.AutoFitToWindow`これにより、テーブルのサイズが使用可能なウィンドウに合わせて調整されます。

## ステップ5: 表とセルの境界線と余白を設定する

境界線のない表は読みにくいことがよくあります。見た目を整頓するために境界線と余白を定義しましょう。

```csharp
// BorderInfo オブジェクトを使用してデフォルトのセル境界線を設定する
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

//別のカスタマイズされたBorderInfoオブジェクトを使用して表の境界線を設定する
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);

//MarginInfoオブジェクトを作成し、左、下、右、上の余白を設定します。
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;

//デフォルトのセルパディングをMarginInfoオブジェクトに設定する
tab1.DefaultCellPadding = margin;
```
  
表とセルの両方に境界線を追加するには、`BorderInfo`クラスでは、太さを定義します。余白は、セルにパディングスペースを与えるために設定されます。

## ステップ6: 表に行とセルを追加する

内容のない表ですか? それはダメです! 行とセルを追加しましょう。

```csharp
//表に行を作成し、行にセルを作成します
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");

Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
```
  
2 つの行を作成し、各行に 3 つのセルを追加します。ここで実際のデータを入力します (文字列からより複雑な要素まで何でもかまいません)。

## ステップ7: ドキュメントを保存する

すべての設定が完了したら、新しく作成した PDF ドキュメントを保存します。

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
//テーブルオブジェクトを含む更新されたドキュメントを保存する
doc.Save(dataDir);
```
  
の`doc.Save()`メソッドはPDFを指定されたディレクトリに保存します。この場合、文書は次のように保存されます。`AutoFitToWindow_out.pdf`定義したディレクトリ内。

## 結論

これで完了です。Aspose.PDF for .NET を使用して、ウィンドウに自動的に収まるテーブルを作成しました。これにより、テーブルがプロフェッショナルで適切に収まる外観になるだけでなく、さまざまなデータ サイズを扱う際の柔軟性も得られます。レポート、請求書、またはテーブルを必要とするドキュメントを作成する場合でも、この方法は、すっきりとした読みやすいレイアウトを維持するのに最適です。

## よくある質問

### 動的に行を追加できますか?  
はい、行を追加し続けることができます。`tab1.Rows.Add()`コンテンツに応じて動的にメソッドを実行します。

### 自動調整したくない場合は、テーブルをどのように調整すればよいですか?  
手動で設定することもできます`ColumnWidths`使用せずに`ColumnAdjustment.AutoFitToWindow`テーブルの幅を固定します。

### セル内に画像やその他のコンテンツを追加できますか?  
はい、Aspose.PDF では、セル内に画像、テキスト、さらには他の表を追加できます。

### より複雑なテーブル スタイルが必要な場合はどうすればよいでしょうか?  
背景色、テキストの配置、フォント設定などのプロパティを使用して、表とセルのスタイルをさらにカスタマイズできます。

### この表を PDF 以外の形式でエクスポートすることは可能ですか?  
もちろんです! Aspose.PDF は、HTML、DOCX などのさまざまな形式へのエクスポートをサポートしています。