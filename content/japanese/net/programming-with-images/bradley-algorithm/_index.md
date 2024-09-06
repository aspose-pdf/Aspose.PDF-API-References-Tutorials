---
title: ブラッドリーアルゴリズム
linktitle: ブラッドリーアルゴリズム
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET で Bradley アルゴリズムを使用して PDF ドキュメントを変換します。
type: docs
weight: 30
url: /ja/net/programming-with-images/bradley-algorithm/
---
このステップバイステップ ガイドでは、Aspose.PDF for .NET で Bradley アルゴリズムを使用する方法について説明します。環境がすでに設定されていることを確認し、以下の手順に従ってください。

## ステップ1: ドキュメントディレクトリを定義する

始める前に、ドキュメントの正しいディレクトリを設定してください。`"YOUR DOCUMENT DIRECTORY"`コード内に、PDF ドキュメントが保存されているディレクトリへのパスを含めます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ2: ドキュメントを開く

このステップでは、`Document` Aspose.PDFのクラス。`Document`コンストラクターを呼び出して、PDF ドキュメントへのパスを渡します。

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

## ステップ3: 出力ファイルを定義する

結果画像とバイナリ画像の出力ファイル名を定義します。`"resultant_out.tif"`そして`"37116-bin_out.tif"`出力ファイルの希望する名前を入力します。

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

## ステップ4: 解決オブジェクトを作成する

作成する`Resolution`オブジェクトを使用して、TIFF イメージの解像度を設定します。この例では、300 dpi の解像度を使用しています。

```csharp
Resolution resolution = new Resolution(300);
```

## ステップ5: TiffSettingsオブジェクトを作成する

作成する`TiffSettings`オブジェクトを使用して、出力 TIFF ファイルの設定を指定します。この例では、LZW 圧縮とピクセルあたり 1 ビットの色深度 (1 bpp 形式) を使用しています。

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
```

## ステップ6: TIFFデバイスを作成する

TIFFデバイスを作成するには、`TiffDevice`解像度と TIFF 設定を指定するオブジェクト。

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

## ステップ7: 特定のページを変換して画像を保存する

使用`Process`TIFF デバイスのメソッドを使用して PDF ドキュメントの特定のページを変換し、その画像を TIFF ファイルに保存します。ファイルの出力パスを指定します。

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

## ステップ8: ブラッドリーアルゴリズムを使用して画像を2値化する

使用`BinarizeBradley`TIFF デバイスのメソッドを使用して、Bradley アルゴリズムを使用して画像を 2 値化します。このメソッドは、元の画像の入力ストリームと 2 値画像の出力ストリームを受け取ります。2 値化しきい値 (この例では 0.1) を指定します。

```csharp
using (FileStream

  inStream = new FileStream(outputImageFile, FileMode.Open))
{
using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
{
tiffDevice. Binarize Bradley(inStream, outStream, 0.1);
}
}
```

### Aspose.PDF for .NET を使用した Bradley アルゴリズムのサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントを開く
Document pdfDocument = new Document(dataDir+ "PageToTIFF.pdf");
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
//解決オブジェクトを作成する
Resolution resolution = new Resolution(300);
//TiffSettingsオブジェクトを作成する
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
//TIFFデバイスの作成
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
//特定のページを変換し、画像をストリームに保存する
tiffDevice.Process(pdfDocument, outputImageFile);
using (FileStream inStream = new FileStream(outputImageFile, FileMode.Open))
{
	using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
	{
		tiffDevice.BinarizeBradley(inStream, outStream, 0.1);
	}
}
System.Console.WriteLine("Conversion using bradley algorithm performed successfully!");
```

## 結論

おめでとうございます! Aspose.PDF for .NET で Bradley アルゴリズムを使用した変換が正常に完了しました。これで、結果の画像をプロジェクトまたはアプリケーションで使用できるようになりました。

### よくある質問

#### Q: Bradley アルゴリズムとは何ですか? また、Aspose.PDF for .NET とどのように関係していますか?

A: Bradley アルゴリズムは、画像の品質と鮮明さを向上させるために使用される画像処理技術です。Aspose.PDF for .NET は、Bradley アルゴリズムを PDF ドキュメントに適用する便利な方法を提供し、画像の品質を向上させます。

#### Q: Aspose.PDF for .NET で Bradley アルゴリズムを使用するための環境をどのように設定すればよいですか?

A: 始める前に、Aspose.PDF for .NET が適切にインストールされ、開発環境が構成されていることを確認してください。

#### Q: Bradley アルゴリズム プロセスでドキュメント ディレクトリを定義することの重要性は何ですか?

A: PDF ドキュメントが処理のために正しいパスに配置されることを確認するには、正しいドキュメント ディレクトリを指定することが重要です。

#### Q: Bradley アルゴリズムで Aspose.PDF for .NET を使用して PDF ドキュメントを開くにはどうすればよいですか?

 A:`Document` Bradley アルゴリズム プロセスの入力として機能する PDF ドキュメントを開くクラスです。

#### Q: Bradley アルゴリズム プロセスでイメージとバイナリ イメージの出力ファイル名を定義する目的は何ですか?

A: 出力ファイル名を定義すると、Bradley アルゴリズムを適用した後に結果の画像とバイナリ イメージが保存される場所を指定できます。

#### Q: 解像度設定は、Bradley アルゴリズム プロセスにおける TIFF 画像の品質にどのように影響しますか?

A: 解像度設定によって、Bradley アルゴリズムを適用した後の TIFF 画像の詳細レベルと鮮明度が決まります。

#### Q: Bradley アルゴリズム プロセスで出力 TIFF イメージのどのような設定をカスタマイズできますか?
A: 圧縮タイプや色深度などの設定をカスタマイズして、TIFF イメージの希望する出力を実現できます。

#### Q: TIFF デバイスは Bradley アルゴリズム プロセスにどのように貢献しますか?

A: TIFF デバイスは、画像を処理し、Bradley アルゴリズムを適用するツールとして機能し、画像の品質を向上させます。

#### Q: Bradley アルゴリズム プロセスで PDF ドキュメントの特定のページを TIFF 画像に変換するにはどうすればよいですか?

 A: 活用する`Process` TIFF デバイスのメソッドを使用して PDF ドキュメントの特定のページを TIFF 画像に変換し、その後 Bradley アルゴリズムを使用してさらに処理することができます。