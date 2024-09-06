---
title: 高速画像縮小
linktitle: 高速画像縮小
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、PDF ファイル内の画像のサイズをすばやく縮小します。
type: docs
weight: 130
url: /ja/net/programming-with-images/fast-shrink-images/
---
このガイドでは、Aspose.PDF for .NET を使用して PDF ファイル内の画像のサイズをすばやく縮小する方法について、手順ごとに説明します。環境がすでに設定されていることを確認し、以下の手順に従ってください。

## ステップ1: 時間を初期化する

始める前に、圧縮パフォーマンスを測定するための時間を初期化します。開始時間を記録するために次のコードを追加します。

```csharp
var time = DateTime.Now.Ticks;
```

## ステップ2: ドキュメントディレクトリを定義する

正しいドキュメントディレクトリを設定してください。`"YOUR DOCUMENT DIRECTORY"`コード内に、PDF ドキュメントが保存されているディレクトリへのパスを含めます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ3: PDF文書を開く

このステップでは、`Document` Aspose.PDFのクラス。`Document`コンストラクターを呼び出して、PDF ドキュメントへのパスを渡します。

```csharp
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
```

## ステップ4: 最適化オプションを初期化する

このステップでは、画像圧縮の最適化オプションを初期化します。`OptimizationOptions`適切なオプションを設定します。この例では、画像圧縮を有効にし、画像品質を 75 に設定し、高速圧縮バージョンを使用します。

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
optimizeOptions.ImageCompressionOptions.CompressImages = true;
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;
optimizeOptions.ImageCompressionOptions.Version = Pdf.Optimization.ImageCompressionVersion.Fast;
```

## ステップ5: PDFドキュメントを最適化する

このステップでは、先に定義した最適化オプションを使用してPDF文書を最適化します。`OptimizeResources`方法の`pdfDocument`オブジェクトを作成し、最適化オプションを渡します。

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## ステップ6: 更新されたPDFドキュメントを保存する

更新されたPDF文書を`Save`方法の`pdfDocument`オブジェクト。PDF ファイルの出力パスを指定します。

```csharp
dataDir = dataDir + "FastShrinkImages_out.pdf";
pdfDocument.Save(dataDir);
```

### Aspose.PDF for .NET を使用した高速画像縮小のサンプル ソース コード 
```csharp
//初期化時間
var time = DateTime.Now.Ticks;
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントを開く
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
//最適化オプションを初期化する
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
//CompressImagesオプションを設定する
optimizeOptions.ImageCompressionOptions.CompressImages = true;
//画質オプションを設定する
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;
//画像圧縮バージョンを高速に設定する
optimizeOptions.ImageCompressionOptions.Version = Pdf.Optimization.ImageCompressionVersion.Fast;
// OptimizationOptionsを使用してPDFドキュメントを最適化する
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "FastShrinkImages_out.pdf";
//更新されたドキュメントを保存する
pdfDocument.Save(dataDir);
Console.WriteLine("Ticks: {0}", DateTime.Now.Ticks - time);
Console.WriteLine("\nImage fast shrinked successfully.\nFile saved at " + dataDir);
```

## 結論

おめでとうございます! Aspose.PDF for .NET を使用して PDF 内の画像のサイズをすばやく縮小しました。最適化された PDF ファイルは、指定したディレクトリに保存されます。これで、画像が縮小されたこの PDF ファイルを使用して、より効率的な保存や共有のニーズに対応できます。

### よくある質問

#### Q: Aspose.PDF for .NET を使用して PDF ファイル内の画像のサイズをすばやく縮小する必要があるのはなぜですか?

A: PDF ファイル内の画像のサイズをすばやく縮小すると、ファイルの保存、共有、転送を最適化できるため、パフォーマンスが向上し、リソースの消費が削減されます。

#### Q: PDF 文書で画像圧縮を行うとどのような利点がありますか?

A: PDF ドキュメントで画像を圧縮すると、許容できる画質を維持しながらファイル サイズを最小限に抑えることができるため、読み込み時間が短縮され、必要なストレージ容量が削減され、データ転送の効率が向上します。

#### Q: Aspose.PDF for .NET はどのようにして PDF ファイル内の画像サイズを高速に縮小するのですか?

A: Aspose.PDF for .NET は、PDF ドキュメントを開き、画像圧縮オプションを適用し、画像サイズを縮小して最適化された PDF ファイルを保存するための効率的なプロセスを提供します。

####  Q: の意義は何ですか？`OptimizationOptions` class in fast image size reduction?

 A:`OptimizationOptions`クラスを使用すると、画像圧縮オプションを含むさまざまな最適化設定を定義して、PDF ドキュメント内の画像のサイズを効果的に削減できます。

#### Q: 画像圧縮設定をカスタマイズして、ファイル サイズと画像品質のバランスを制御することはできますか?

A: はい、画像品質や圧縮バージョンなどのパラメータを調整して画像圧縮設定をカスタマイズし、ファイル サイズと画像の外観のバランスを希望どおりにすることができます。

####  Q:`pdfDocument.OptimizeResources` method work to reduce image sizes?

 A:`OptimizeResources`このメソッドは PDF ドキュメントを分析し、画像圧縮設定を含む指定された最適化オプションを適用して、画像やその他のリソースのサイズを縮小します。

#### Q: PDF ドキュメント内の特定の範囲のページに高速画像サイズ縮小を適用することは可能ですか?

 A:`OptimizeResources`この方法では、最適化オプションが PDF ドキュメント全体に適用されます。特定のページに最適化を適用する場合は、最適化の前にそれらのページを新しいドキュメントに抽出する必要があります。

#### Q: 画像サイズを高速に縮小すると効果的なシナリオにはどのようなものがありますか?

A: 画像サイズの高速縮小は、オンライン配布、電子メールの添付、アーカイブ用に PDF ファイルを準備する場合や、多数の画像を含む大きなドキュメントを扱う場合に役立ちます。

#### Q: 画像サイズを縮小すると、PDF ドキュメント内の画像の視覚的な品質に影響しますか?

A: 圧縮によって画像サイズを小さくすると、ある程度画像の品質に影響が出る可能性があります。サイズの縮小と許容できる画像品質のバランスを見つけることが重要です。

#### Q: 高速画像サイズ縮小プロセスのパフォーマンスを測定するにはどうすればよいでしょうか?

 A: 開始時間を記録することでパフォーマンスを測定できます。`DateTime.Now.Ticks`最適化プロセスの前にメソッドを実行し、プロセス後の経過時間を計算します。