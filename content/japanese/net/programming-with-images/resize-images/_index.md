---
title: PDF ファイル内の画像のサイズを変更する
linktitle: PDF ファイル内の画像のサイズを変更する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内の画像のサイズを変更するためのステップバイステップのガイド。
type: docs
weight: 250
url: /ja/net/programming-with-images/resize-images/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイル内の画像のサイズを変更する方法を説明します。この操作を簡単に実行するには、次の手順に従います。

## 前提条件

始める前に、以下のものがあることを確認してください。

- Visual Studio またはその他の開発環境がインストールされ、構成されている。
- C# プログラミング言語の基本的な知識。
- .NET 用の Aspose.PDF ライブラリがインストールされています。 Aspose公式Webサイトからダウンロードできます。

## ステップ 1: PDF ドキュメントをロードする

まず、次のコードを使用して PDF ドキュメントを読み込みます。

```csharp
//時刻を初期化する
var time = DateTime.Now.Ticks;

string dataDir = "YOUR DOCUMENTS DIRECTORY";
//文書を開く
Document pdfDocument = new Document(dataDir + "ResizeImage.pdf");
```

PDF ドキュメントへの正しいパスを指定してください。

## ステップ 2: 最適化オプションの初期化

画像のサイズを変更する前に、最適化オプションを初期化する必要があります。次のコードを使用します。

```csharp
//最適化オプションの初期化
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();

//画像圧縮オプションを有効にする
optimizeOptions.ImageCompressionOptions.CompressImages = true;

//画質を設定する
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;

//画像のサイズ変更オプションを有効にする
optimizeOptions.ImageCompressionOptions.ResizeImages = true;

//最大解像度を設定する
optimizeOptions.ImageCompressionOptions.MaxResolution = 300;
```

ニーズに応じて最適化設定を調整できます。

## ステップ 3: PDF ドキュメントの最適化

次に、定義した最適化オプションを使用して PDF ドキュメントを最適化します。次のコードを使用します。

```csharp
// OptimizationOptions を使用して PDF ドキュメントを最適化する
pdfDocument.OptimizeResources(optimizeOptions);

dataDir = dataDir + "ResizeImages_out.pdf";
//更新されたドキュメントを保存する
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage resized successfully.\nFile saved as: " + dataDir);
```

更新された PDF ドキュメントに必要なパスとファイル名を必ず指定してください。

### Aspose.PDF for .NET を使用した画像のサイズ変更のサンプル ソース コード 
```csharp
//初期化時間
var time = DateTime.Now.Ticks;
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開いた文書
Document pdfDocument = new Document(dataDir + "ResizeImage.pdf");
//最適化オプションの初期化
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();            
//CompressImages オプションを設定する
optimizeOptions.ImageCompressionOptions.CompressImages = true;            
//画質オプションを設定する
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;            
//ResizeImage オプションを設定する
optimizeOptions.ImageCompressionOptions.ResizeImages = true;            
//MaxResolution オプションを設定する
optimizeOptions.ImageCompressionOptions.MaxResolution = 300;
//OptimizationOptions を使用して PDF ドキュメントを最適化する
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "ResizeImages_out.pdf";
//更新されたドキュメントを保存する
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage resized successfully.\nFile saved at " + dataDir);
```

## 結論

おめでとうございます！ Aspose.PDF for .NET を使用して PDF ドキュメント内の画像のサイズを正常に変更しました。この方法を独自のプロジェクトに適用して、PDF ファイル内の画像のサイズを変更できるようになりました。

### よくある質問

#### Q: Aspose.PDF for .NET を使用して PDF ファイル内の画像のサイズを変更したいのはなぜですか?

A: PDF ファイル内の画像のサイズを変更すると、ドキュメントのサイズが最適化され、パフォーマンスが向上します。これは、共有を容易にするため、または PDF ドキュメントの読み込みを高速化するためにファイル サイズを削減したい場合に特に便利です。

#### Q: 画像のサイズ変更は、PDF ドキュメント内の画像の品質にどのような影響を与えますか?

 A: 画像のサイズ変更には、画像のサイズと解像度の縮小が含まれるため、ファイル サイズが小さくなる可能性があります。これにより画質がある程度低下する可能性がありますが、`ImageQuality`パラメータ (`optimizeOptions.ImageCompressionOptions.ImageQuality`) を使用すると、画像サイズと品質のバランスを制御できます。

####  Q：その目的は何ですか？`MaxResolution` option in the optimization settings?

 A:`MaxResolution`オプション （`optimizeOptions.ImageCompressionOptions.MaxResolution`) PDF ドキュメント内の画像の最大解像度を設定します。解像度が高い画像は、最適化プロセス中にこの指定された値まで縮小されます。

#### Q: 画像のサイズ変更の最適化設定を調整するにはどうすればよいですか?

 A: 提供されたコードで、最適化オプションの値を変更して、希望する画像のサイズ変更と圧縮を実現できます。たとえば、次のように変更できます。`ImageQuality`そして`MaxResolution`値を使用して、要件に応じて最適化プロセスをカスタマイズします。

#### Q: PDF ドキュメント内の特定の画像のサイズを選択的に変更できますか?

A: 提供されたコードは、同じ最適化設定を使用して PDF ドキュメント内のすべての画像を最適化します。特定の画像を選択的にサイズ変更したい場合は、それらの画像を個別にターゲットにするようにコードを変更する必要がある場合があります。

####  Q: どうやって`pdfDocument.OptimizeResources` method work in resizing images?

 A:`OptimizeResources`このメソッドは、画像のサイズ変更や圧縮など、指定された最適化オプションを PDF ドキュメントに適用します。定義された最適化設定を PDF ドキュメントのリソースに適用することで、PDF ドキュメントのファイル サイズを削減できます。

#### Q: PDF ドキュメントを保存する前に、サイズ変更した画像をプレビューすることはできますか?

A: 提供されているコードは、サイズ変更された画像を含む PDF ドキュメントを直接最適化して保存します。保存する前にサイズ変更した画像をプレビューしたい場合は、プレビュー画像を生成するようにコードを変更する必要がある場合もあります。

#### Q: この画像サイズ変更方法を自分のプロジェクトに統合するにはどうすればよいですか?

A: このメソッドをプロジェクトに統合するには、説明されている手順に従い、必要に応じてコードを変更します。このコードをアプリケーションに組み込むことで、PDF ドキュメント内の画像のサイズを変更するプロセスを自動化できます。

#### Q: Aspose.PDF for .NET ライブラリは、PDF 最適化のための他の機能を提供しますか?

A: はい。Aspose.PDF for .NET ライブラリは、フォントやテキストの最適化、未使用オブジェクトの削除、冗長データの削減など、画像のサイズ変更以外にもさまざまな最適化オプションを提供します。ライブラリのドキュメントと例を調べて、その最適化機能の全範囲を確認できます。