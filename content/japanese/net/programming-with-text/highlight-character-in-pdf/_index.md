---
title: PDF ファイル内の文字を強調表示する
linktitle: PDF ファイル内の文字を強調表示する
second_title: Aspose.PDF for .NET API リファレンス
description: この包括的なステップバイステップ ガイドでは、Aspose.PDF for .NET を使用して PDF 内の文字を強調表示する方法を学びます。
type: docs
weight: 240
url: /ja/net/programming-with-text/highlight-character-in-pdf/
---
## 導入

PDF を扱う場合、学術目的、編集、または単に読みやすさを向上させるためなど、テキストや文字を強調する必要が頻繁に生じます。美しいドキュメントがあり、特定の部分を強調したいとします。そこで強調表示が役立ちます。このチュートリアルでは、強力な Aspose.PDF for .NET ライブラリを使用して PDF ファイル内の文字を強調表示する方法について詳しく説明します。 

## 前提条件

コードに進む前に、必要なものがすべて揃っていることを確認しましょう。必要なものは次のとおりです。

1. 開発環境: このチュートリアルでは、Visual Studio または同様の .NET IDE で作業していることを前提としています。
2.  Aspose.PDF for .NETライブラリ:まだお持ちでない場合は、[ここからダウンロード](https://releases.aspose.com/pdf/net/)プロジェクトに追加します。 
3. C# の基礎知識: C# プログラミングの入門書は、実装を簡単に理解するのに役立ちます。
4. PDF ドキュメント: 作業に使用できるサンプル PDF ファイルを用意しておく必要があります。 自分で作成することも、既存のドキュメントを利用することもできます。

## パッケージのインポート

まず、必要な名前空間をインポートする必要があります。これを行うには、C# ファイルの先頭にそれらを含める必要があります。

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Devices;
using Aspose.Pdf.Text;
using System;
using System.Drawing;
```

これらのパッケージは、Aspose ライブラリを使用して PDF ドキュメントを作成、操作、処理するために不可欠です。

それでは、PDF 内の文字を強調表示するプロセスをわかりやすい手順に分解してみましょう。 

## ステップ1: PDFドキュメントを初期化する

最初のステップは、PDF ドキュメントを初期化することです。これには、作業する PDF ファイルの読み込みが含まれます。手順は次のとおりです。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; //必ず正しいパスを設定してください。
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```
このスニペットでは、`YOUR DOCUMENT DIRECTORY`入力PDFファイルが保存されているマシン上の実際のパスを入力します。`Aspose.Pdf.Document`クラスは PDF を読み込むためにインスタンス化されます。

## ステップ2: レンダリングプロセスを設定する

次に、ドキュメントのレンダリング プロセスを準備する必要があります。これは、ページ上の文字を正確に強調表示するために不可欠です。

```csharp
int resolution = 150; //画像キャプチャの解像度を設定します。
using (MemoryStream ms = new MemoryStream())
{
    PdfConverter conv = new PdfConverter(pdfDocument);
    conv.Resolution = new Resolution(resolution, resolution);
    conv.GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
    Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```
テキストが適切に表示されるように、解像度を定義します。`PdfConverter`PDF ページを画像に変換して、その上に描画できるようにします。

## ステップ3: 描画用のグラフィックオブジェクトを作成する

描画プロセスを設定したら、ハイライト表示を実行するグラフィック オブジェクトを作成する必要があります。

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
    float scale = resolution / 72f; //スケール係数。
    gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);
```
ここでは、ビットマップ イメージからグラフィック オブジェクトを作成します。変換により、必要な解像度に正しく一致するようにレンダリングを調整できます。

## ステップ4: 各ページをループしてテキストを強調表示する

次に、PDF の各ページをループして、強調表示したいテキストの断片を見つけます。

```csharp
for (int i = 0; i < pdfDocument.Pages.Count; i++)
{
    Page page = pdfDocument.Pages[i + 1]; // Aspose ではページは 1 からインデックスされます。
    TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
    textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
    page.Accept(textFragmentAbsorber);
```
各ページにアクセスし、`TextFragmentAbsorber`正規表現パターン`@"[\S]+"`空白以外の文字をすべてキャプチャします。

## ステップ5: テキストの断片を抽出して強調表示する

次に、テキストの断片を抽出して強調表示します。このプロセスでは、強調表示したい文字の周囲に四角形を描画します。

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

foreach (TextFragment textFragment in textFragmentCollection)
{
    //ここでロジックを強調する
    for (int segNum = 1; segNum <= textFragment.Segments.Count; segNum++)
    {
        TextSegment segment = textFragment.Segments[segNum];
        for (int charNum = 1; charNum <= segment.Characters.Count; charNum++)
        {
            CharInfo characterInfo = segment.Characters[charNum];
            gr.DrawRectangle(Pens.Black, 
                (float)characterInfo.Rectangle.LLX, 
                (float)characterInfo.Rectangle.LLY, 
                (float)characterInfo.Rectangle.Width, 
                (float)characterInfo.Rectangle.Height);
        }
    }
}
```
各テキスト フラグメント、そのセグメント、および個々の文字をループし、以前に作成したグラフィック オブジェクトを使用してそれらの周囲に四角形を描画します。

## ステップ6: 変更した画像を保存する

ハイライトした後、結果の画像を新しい PNG ファイルとして保存する必要があります。

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```
この行は、変更されたビットマップ イメージを指定されたディレクトリに PNG ファイルとして保存します。 

## ステップ 7: 例外処理で終了する

最後に、コードを try-catch ブロックで囲んで、予期しないエラーを適切に処理できるようにすることをお勧めします。

```csharp
catch (Exception ex)
{
    Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get a 30-day temporary license from [here](https://Purchase.aspose.com/temporary-license/).");
}
```

このブロックは、プロセス中に発生する可能性のある例外をキャッチし、ユーザーに有益なフィードバックを提供します。

## 結論

これで完了です。Aspose.PDF for .NET を使用して PDF ファイル内の文字をハイライト表示できました。この強力なライブラリは、注釈、フォームの入力、ドキュメントの変換など、PDF 操作の無限の可能性への扉を開きます。Aspose を使い続けるときは、練習が鍵であることを忘れないでください。さまざまな機能を試し続ければ、すぐに PDF のプロになれます。

## よくある質問

### Aspose.PDF for .NET とは何ですか?
Aspose.PDF for .NET は、.NET アプリケーションでプログラムによって PDF ドキュメントを作成、操作、変換できるライブラリです。

### 複数のテキストフラグメントを一度に強調表示できますか?
はい、提供されているコードは、PDF 内のすべてのテキストをループして複数のフラグメントを強調表示するように調整できます。

### Aspose.PDF の無料版はありますか?
はい、Aspose では無料トライアルを提供しているため、購入前にライブラリをテストできます。

### Aspose.PDF を使用するにはライセンスが必要ですか?
はい、商用利用には有効なライセンスが必要ですが、テスト用に 30 日間の一時ライセンスを取得できます。

### さらに詳しいドキュメントはどこで見つかりますか?
参照するには[Aspose.PDF ドキュメント](https://reference.aspose.com/pdf/net/)実装と機能の詳細については、こちらをご覧ください。