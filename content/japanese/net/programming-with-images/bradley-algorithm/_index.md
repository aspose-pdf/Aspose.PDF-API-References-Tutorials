---
title: ブラッドリーアルゴリズム
linktitle: ブラッドリーアルゴリズム
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET で Bradley アルゴリズムを使用して PDF ドキュメントを変換します。
type: docs
weight: 30
url: /ja/net/programming-with-images/bradley-algorithm/
---
このステップバイステップのガイドでは、Aspose.PDF for .NET で Bradley アルゴリズムを使用する方法を説明します。環境がすでにセットアップされていることを確認し、以下の手順に従ってください。

## ステップ 1: ドキュメント ディレクトリを定義する

開始する前に、ドキュメント用に正しいディレクトリを設定していることを確認してください。交換する`"YOUR DOCUMENT DIRECTORY"`コード内で、PDF ドキュメントが配置されているディレクトリへのパスを指定します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: ドキュメントを開く

このステップでは、`Document` Aspose.PDF のクラス。使用`Document`コンストラクターを開き、PDF ドキュメントへのパスを渡します。

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

## ステップ 3: 出力ファイルを定義する

結果のイメージとバイナリ イメージの出力ファイル名を定義します。交換する`"resultant_out.tif"`そして`"37116-bin_out.tif"`出力ファイルに必要な名前を付けます。

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

## ステップ 4: 解像度オブジェクトを作成する

を作成します`Resolution`オブジェクトを使用して TIFF 画像の解像度を設定します。この例では、300 dpi の解像度を使用しています。

```csharp
Resolution resolution = new Resolution(300);
```

## ステップ 5: TiffSettings オブジェクトを作成する

を作成します`TiffSettings`オブジェクトを使用して、出力 TIFF ファイルの設定を指定します。この例では、LZW 圧縮とピクセルあたり 1 ビットの色深度 (1 bpp 形式) を使用しています。

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
```

## ステップ 6: TIFF デバイスを作成する

を使用して TIFF デバイスを作成します。`TiffDevice`オブジェクトを作成し、解像度と TIFF 設定を指定します。

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

## ステップ 7: 特定のページを変換して画像を保存する

使用`Process`TIFF デバイスのメソッドを使用して、PDF ドキュメントの特定のページを変換し、画像を TIFF ファイルに保存します。ファイルの出力パスを指定します。

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

## ステップ 8: Bradley アルゴリズムを使用して画像を 2 値化する

使用`BinarizeBradley`Bradley アルゴリズムを使用して画像を 2 値化する TIFF デバイスのメソッド。このメソッドは、元のイメージの入力ストリームとバイナリ イメージの出力ストリームを受け取ります。 2値化の閾値（この例では0.1）を指定します。

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
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開いた文書
Document pdfDocument = new Document(dataDir+ "PageToTIFF.pdf");
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
//解像度オブジェクトの作成
Resolution resolution = new Resolution(300);
//TiffSettings オブジェクトを作成する
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
//TIFFデバイスの作成
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
//特定のページを変換し、画像をストリームに保存します
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

おめでとうございます！ Aspose.PDF for .NET で Bradley アルゴリズムを使用した変換が正常に完了しました。これで、結果として得られたイメージをプロジェクトまたはアプリケーションで使用できるようになります。

### よくある質問

#### Q: Bradley アルゴリズムとは何ですか?また、Aspose.PDF for .NET とどのように関連していますか?

A: Bradley アルゴリズムは、画質と鮮明さを向上させるために使用される画像処理技術です。 Aspose.PDF for .NET は、Bradley アルゴリズムを PDF ドキュメントに適用する便利な方法を提供し、画像を改善します。

#### Q: Aspose.PDF for .NET で Bradley アルゴリズムを使用する環境をセットアップするにはどうすればよいですか?

A: 始める前に、Aspose.PDF for .NET が適切にインストールされ、開発環境が構成されていることを確認してください。

#### Q: Bradley アルゴリズム プロセスでドキュメント ディレクトリを定義することの重要性は何ですか?

A: PDF ドキュメントが処理用の正しいパスに配置されるようにするには、正しいドキュメント ディレクトリを指定することが重要です。

#### Q: Bradley アルゴリズムの Aspose.PDF for .NET を使用して PDF ドキュメントを開くにはどうすればよいですか?

 A: を使用してください。`Document`クラスを使用して PDF ドキュメントを開きます。これは Bradley アルゴリズム プロセスの入力として機能します。

#### Q: Bradley アルゴリズム プロセスでイメージとバイナリ イメージの出力ファイル名を定義する目的は何ですか?

A: 出力ファイル名を定義すると、Bradley アルゴリズムを適用した後に結果のイメージとバイナリ イメージを保存する場所を指定できます。

#### Q: 解像度設定は、Bradley アルゴリズム プロセスの TIFF 画質にどのような影響を与えますか?

A: 解像度設定によって、Bradley アルゴリズムを適用した後に得られる TIFF 画像の詳細度と明瞭さのレベルが決まります。

#### Q: Bradley アルゴリズム プロセスで出力 TIFF 画像のどの設定をカスタマイズできますか?
A: 圧縮タイプや色深度などの設定をカスタマイズして、TIFF 画像の目的の出力を実現できます。

#### Q: TIFF デバイスは Bradley アルゴリズム プロセスにどのように貢献しますか?

A: TIFF デバイスは、画像を処理して Bradley アルゴリズムを適用するツールとして機能し、結果として画質が向上します。

#### Q: Bradley アルゴリズム プロセスで PDF ドキュメントの特定のページを TIFF イメージに変換するにはどうすればよいですか?

 A: を活用してください。`Process` TIFF デバイスのメソッドを使用して、PDF ドキュメントの特定のページを TIFF 画像に変換します。その後、Bradley アルゴリズムを使用してさらに処理できます。