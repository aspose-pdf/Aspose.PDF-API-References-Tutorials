---
title: 画像の高速縮小
linktitle: 画像の高速縮小
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用すると、PDF ファイル内の画像のサイズをすばやく縮小できます。
type: docs
weight: 130
url: /ja/net/programming-with-images/fast-shrink-images/
---
このガイドでは、Aspose.PDF for .NET を使用して PDF ファイル内の画像のサイズをすばやく縮小する方法を段階的に説明します。環境がすでにセットアップされていることを確認し、以下の手順に従ってください。

## ステップ 1: 時間を初期化する

始める前に、圧縮パフォーマンスを測定する時間を初期化します。次のコードを追加して開始時間を記録します。

```csharp
var time = DateTime.Now.Ticks;
```

## ステップ 2: ドキュメント ディレクトリを定義する

必ず正しいドキュメント ディレクトリを設定してください。交換する`"YOUR DOCUMENT DIRECTORY"`コード内で、PDF ドキュメントが配置されているディレクトリへのパスを指定します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 3: PDF ドキュメントを開く

このステップでは、`Document` Aspose.PDF のクラス。使用`Document`コンストラクターを開き、PDF ドキュメントへのパスを渡します。

```csharp
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
```

## ステップ 4: 最適化オプションを初期化する

このステップでは、画像圧縮の最適化オプションを初期化します。のインスタンスを作成します`OptimizationOptions`そして適切なオプションを設定します。この例では、画像圧縮を有効にし、画質を 75 に設定し、高速圧縮バージョンを使用します。

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
optimizeOptions.ImageCompressionOptions.CompressImages = true;
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;
optimizeOptions.ImageCompressionOptions.Version = Pdf.Optimization.ImageCompressionVersion.Fast;
```

## ステップ 5: PDF ドキュメントを最適化する

このステップでは、前に定義した最適化オプションを使用して PDF ドキュメントを最適化します。電話してください`OptimizeResources`の方法`pdfDocument`オブジェクトを指定し、最適化オプションを渡します。

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## ステップ 6: 更新された PDF ドキュメントを保存する

更新された PDF ドキュメントを保存するには、`Save`の方法`pdfDocument`物体。 PDFファイルの出力パスを指定します。

```csharp
dataDir = dataDir + "FastShrinkImages_out.pdf";
pdfDocument.Save(dataDir);
```

### Aspose.PDF for .NET を使用した高速縮小画像のサンプル ソース コード 
```csharp
//初期化時間
var time = DateTime.Now.Ticks;
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開いた文書
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
//最適化オプションの初期化
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
//CompressImages オプションを設定する
optimizeOptions.ImageCompressionOptions.CompressImages = true;
//画質オプションを設定する
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;
//今ヶ江圧縮バージョンを高速に設定する
optimizeOptions.ImageCompressionOptions.Version = Pdf.Optimization.ImageCompressionVersion.Fast;
//OptimizationOptions を使用して PDF ドキュメントを最適化する
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "FastShrinkImages_out.pdf";
//更新されたドキュメントを保存する
pdfDocument.Save(dataDir);
Console.WriteLine("Ticks: {0}", DateTime.Now.Ticks - time);
Console.WriteLine("\nImage fast shrinked successfully.\nFile saved at " + dataDir);
```

## 結論

おめでとうございます！ Aspose.PDF for .NET を使用して、PDF 内の画像のサイズをすばやく縮小しました。最適化された PDF ファイルが指定したディレクトリに保存されます。より効率的なストレージや共有のニーズに合わせて、画像を縮小したこの PDF ファイルを使用できるようになりました。

### よくある質問

#### Q: Aspose.PDF for .NET を使用して PDF ファイル内の画像のサイズをすぐに縮小したいのはなぜですか?

A: PDF ファイル内の画像のサイズを迅速に縮小すると、保存、共有、または送信のためにファイルが最適化され、パフォーマンスが向上し、リソース消費が削減されます。

#### Q: PDF ドキュメントで画像圧縮を行うとどのような利点がありますか?

A: PDF ドキュメントの画像圧縮により、許容可能な画質を維持しながらファイル サイズを最小限に抑えることができ、読み込み時間の短縮、ストレージ要件の削減、およびデータ転送効率の向上につながります。

#### Q: Aspose.PDF for .NET はどのようにして PDF ファイル内の画像サイズの高速削減を促進しますか?

A: Aspose.PDF for .NET は、PDF ドキュメントを開き、画像圧縮オプションを適用し、画像サイズを縮小して最適化された PDF ファイルを保存するための合理化されたプロセスを提供します。

####  Q: の重要性は何ですか?`OptimizationOptions` class in fast image size reduction?

 A:`OptimizationOptions`クラスを使用すると、画像圧縮オプションを含むさまざまな最適化設定を定義して、PDF ドキュメント内の画像のサイズを効果的に削減できます。

#### Q: 画像圧縮設定をカスタマイズして、ファイル サイズと画質のバランスを制御できますか?

A: はい、画質や圧縮バージョンなどのパラメータを調整して画像圧縮設定をカスタマイズし、ファイル サイズと画像の外観の間で望ましいバランスを実現できます。

####  Q: どうやって`pdfDocument.OptimizeResources` method work to reduce image sizes?

 A:`OptimizeResources`このメソッドは PDF ドキュメントを分析し、画像圧縮設定を含む指定された最適化オプションを適用して、画像やその他のリソースのサイズを削減します。

#### Q: PDF ドキュメント内の特定のページ範囲に高速画像サイズ縮小を適用することはできますか?

 A:`OptimizeResources`このメソッドは、PDF ドキュメント全体に最適化オプションを適用します。特定のページに最適化を適用する場合は、最適化の前にそれらのページを新しいドキュメントに抽出する必要があります。

#### Q: 画像サイズの高速削減が有益となるシナリオにはどのようなものがありますか?

A: オンライン配布、電子メールへの添付、アーカイブ用に PDF ファイルを準備する場合、または多数の画像を含む大きなドキュメントを扱う場合には、画像サイズの高速削減が有益です。

#### Q: 画像サイズを小さくすると、PDF ドキュメント内の画像の視覚的な品質に影響しますか?

A: 圧縮によって画像サイズを小さくすると、画質にある程度影響する可能性があります。サイズの縮小と許容可能な画質の間のバランスを見つけることが重要です。

#### Q: 高速画像サイズ縮小プロセスのパフォーマンスを測定するにはどうすればよいですか?

 A: パフォーマンスを測定するには、`DateTime.Now.Ticks`最適化処理前のメソッドと処理後の経過時間を計算します。