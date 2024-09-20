---
title: PDF ファイル内の境界線を抽出
linktitle: PDF ファイル内の境界線を抽出
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルから境界線を抽出し、画像として保存する方法を学びます。コード サンプルと成功のためのヒントを含むステップ バイ ステップ ガイド。
type: docs
weight: 80
url: /ja/net/programming-with-tables/extract-border/
---
## 導入

PDF を扱う場合、境界線やグラフィカル パスなどの特定の要素を抽出するのは困難な作業のように思えるかもしれません。しかし、Aspose.PDF for .NET を使用すると、PDF ファイルから境界線や図形を簡単に抽出し、画像として保存できます。このチュートリアルでは、PDF から境界線を抽出し、PNG 画像として保存するプロセスについて詳しく説明します。PDF のグラフィカル コンテンツを制御する準備をしましょう。

## 前提条件

コードに進む前に、すべてが設定されていることを確認してください。

1.  Aspose.PDF for .NET: Aspose.PDFライブラリをまだインストールしていない場合は、[ここからダウンロード](https://releases.aspose.com/pdf/net/)また、無料トライアルまたは購入したライセンスを通じてライセンスを適用する必要があります。
2. IDE セットアップ: Visual Studio またはその他の .NET IDE で C# プロジェクトをセットアップします。Aspose.PDF ライブラリへの必要な参照が追加されていることを確認します。
3. 入力PDFファイル: 境界線を抽出するPDFファイルを用意してください。このチュートリアルでは、次のファイルを参照します。`input.pdf`.

## 必要なパッケージのインポート

まず、必要な名前空間をインポートすることから始めましょう。これらのパッケージは、PDF コンテンツを操作するために必要なツールを提供します。

```csharp
using System.IO;
using System;
using System.Drawing.Drawing2D;
using System.Drawing.Imaging;
using System.Collections;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

基本事項はこれで説明しましたので、ステップバイステップのガイドに進み、コードの各部分を分解して詳細を説明します。


## ステップ1: PDFドキュメントの読み込み

最初のステップは、抽出したい境界線を含む PDF ドキュメントを読み込むことです。読み始める前に本を開くのと同じように考えてください。コンテンツにアクセスする必要があります。

まず、PDFファイルが保存されているディレクトリを指定して、`Aspose.Pdf.Document`クラス。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
```

このコードは、`input.pdf`指定されたディレクトリからファイルを取得します。ファイル パスが正しいことを確認してください。そうでない場合、ファイルが見つからないというエラーが発生する可能性があります。

## ステップ2: グラフィックスとビットマップの設定

抽出を開始する前に、描画するキャンバスを作成する必要があります。.NET の世界では、これは Bitmap オブジェクトと Graphics オブジェクトを設定することを意味します。Bitmap は画像を表し、Graphics オブジェクトを使用すると、PDF から抽出された境界線などの図形を描画できます。

```csharp
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);
```

内訳は次のとおりです。
- PDF の最初のページと同じサイズのビットマップ イメージを作成します。
- GraphicsPath は、図形 (この場合は境界線) を定義するために使用されます。
- マトリックスはグラフィックスがどのように変換されるかを定義します。PDF と .NET は座標系が異なるため、反転マトリックスが必要です。

## ステップ3: PDFコンテンツの処理


PDF ファイルは一連の描画コマンドであり、境界情報を識別して抽出するには、これらの各コマンドを処理する必要があります。

```csharp
foreach (Operator op in doc.Pages[1].Contents)
{
    //状態の保存/復元、線の描画、図形の塗りつぶしなどのコマンドを処理します。
}
```

コードは、PDF のコンテンツ ストリーム内のすべての描画演算子をループします。各演算子は、線、四角形、またはその他のグラフィカルな命令を表す場合があります。

## ステップ4: PDF演算子の処理

PDF ファイル内の各演算子はアクションを制御します。境界線を抽出するには、「移動」、「線」、「四角形を描く」などのコマンドを識別する必要があります。次の演算子はこれらのアクションを処理します。

- MoveTo: カーソルを開始点に移動します。
- LineTo: 現在のポイントから新しいポイントまで線を描きます。
- Re: 四角形を描画します (これは境界線の一部である可能性があります)。

```csharp
Aspose.Pdf.Operators.MoveTo opMoveTo = op as Aspose.Pdf.Operators.MoveTo;
Aspose.Pdf.Operators.LineTo opLineTo = op as Aspose.Pdf.Operators.LineTo;
Aspose.Pdf.Operators.Re opRe = op as Aspose.Pdf.Operators.Re;

if (opMoveTo != null)
{
    lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
    System.Drawing.PointF linePoint = new System.Drawing.PointF((float)opLineTo.X, (float)opLineTo.Y);
    graphicsPath.AddLine(lastPoint, linePoint);
    lastPoint = linePoint;
}
else if (opRe != null)
{
    System.Drawing.RectangleF re = new System.Drawing.RectangleF((float)opRe.X, (float)opRe.Y, (float)opRe.Width, (float)opRe.Height);
    graphicsPath.AddRectangle(re);
}
```

このステップでは、次の操作を行います。
- 描画された線や図形ごとにポイントをキャプチャします。
- 長方形の場合（`opRe` ）に直接追加します`graphicsPath`これは後で境界線を描くために使用します。

## ステップ5: 境界線を描く

境界線を形成する線と四角形を特定したら、実際にそれらを Bitmap オブジェクトに描画する必要があります。ここで Graphics オブジェクトが登場します。

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
    gr.SmoothingMode = SmoothingMode.HighQuality;
    gr.DrawPath(new System.Drawing.Pen(strokeColor), graphicsPath);
}
```

- ビットマップに基づいて Graphics オブジェクトを作成します。
- SmoothingMode.HighQuality を使用すると、滑らかな画像が得られます。
- 最後に、DrawPath を使用して境界線を描画します。

## ステップ6: 抽出した境界線を保存する

境界線を抽出したので、次はそれを画像ファイルとして保存します。これにより、境界線が PNG として保存されます。

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

- ビットマップは PNG 画像として保存されます。
- この画像を開いて、抽出された境界線を表示できるようになりました。

## 結論

Aspose.PDF for .NET を使用して PDF ファイルから境界線を抽出するのは、最初は難しいように思えるかもしれませんが、一度分解してみると簡単になります。PDF の描画演算子を理解し、強力な .NET ライブラリを利用することで、グラフィック コンテンツを効率的に操作および抽出できます。このガイドは、PDF 操作を開始するための強力な基礎を提供します。

## よくある質問

### PDF 内の複数のページをどのように処理しますか?  
文書内の各ページをループするには、`doc.Pages`ハードコーディングの代わりに`doc.Pages[1]`.

### 同じアプローチを使用して、テキストなどの他の要素を抽出できますか?  
はい、Aspose.PDF は PDF ファイルからテキスト、画像、その他のコンテンツを抽出するための豊富な API を提供します。

### 制限を回避するためにライセンスを適用するにはどうすればよいですか?  
あなたはできる[ライセンスを適用する](https://purchase.aspose.com/temporary-license/)それをロードすることで`License`Aspose によって提供されるクラス。

### PDF に境界線がない場合はどうなるのでしょうか?  
PDF に目に見える境界線が含まれていない場合、グラフィック抽出プロセスで結果が得られない可能性があります。PDF コンテンツに描画可能な境界線が含まれていることを確認してください。

### 出力を PNG 以外の形式で保存できますか?  
はい、変更するだけです`ImageFormat.Png`サポートされている別の形式（例：`ImageFormat.Jpeg`.