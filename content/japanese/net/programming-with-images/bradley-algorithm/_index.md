---
title: ブラッドリーアルゴリズム
linktitle: ブラッドリーアルゴリズム
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET の Bradley アルゴリズムを使用して PDF を TIFF に変換する方法を学びます。シームレスな変換のためのステップバイステップ ガイド、前提条件、および FAQ。
type: docs
weight: 30
url: /ja/net/programming-with-images/bradley-algorithm/
---
## 導入

PDF ファイルの操作では、単に読み取ったり編集したりするだけでなく、画像に変換する必要がある場合もあります。PDF を TIFF 画像に変換する強力な方法の 1 つは、Aspose.PDF for .NET ライブラリを通じて Bradley アルゴリズムを使用することです。この方法により、ドキュメントのアーカイブやその他の特殊な使用例に最適な高品質のバイナリ画像が保証されます。

このチュートリアルでは、Bradley バイナリ化アルゴリズムを使用して PDF ページを TIFF 画像に変換するプロセスを詳細かつわかりやすく説明します。Aspose.PDF for .NET を使用すると、このタスクが簡素化され、ドキュメント ワークフローを自動化および合理化できるようになります。

## 前提条件

コードに進む前に、必要な情報がすべて揃っていることを確認しましょう。

-  Aspose.PDF for .NET: ライブラリが必要です。ここからダウンロードしてください。[ここ](https://releases.aspose.com/pdf/net/).
- Visual Studio (または任意の C# IDE)。
- C# の基礎知識。
- 有効な免許証または[一時ライセンス](https://purchase.aspose.com/temporary-license/)Aspose より。

## パッケージのインポート

まず最初に、プロジェクトに必要な名前空間をインポートしてください。これらのライブラリは、PDF ドキュメントを操作し、TIFF 形式に変換し、Bradley 2 値化アルゴリズムを適用するためのツールを提供します。

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

スムーズに実行できるように、プロセスを簡単な手順に分解してみましょう。このガイドの最後まで読めば、Bradley アルゴリズムを使用して PDF ページをバイナリ TIFF 画像に変換できるようになります。

## ステップ1: ドキュメントディレクトリを設定する

最初のステップは、PDF ドキュメントが保存されているディレクトリへのパスを指定することです。また、生成される TIFF 画像の出力パスも定義します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // PDFファイルへのパス
```

ここには、ソース PDF ファイルと変換された TIFF ファイルの両方が保存されます。コードがエラーなくファイルを読み書きできるように、ディレクトリが適切に設定されていることを確認してください。

## ステップ2: PDFドキュメントを開く

パスが設定されたら、変換する PDF ドキュメントを開きます。Aspose.PDF for .NET を使用すると、ドキュメントを簡単に読み込んでさらに処理することができます。

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

ここ、`PageToTIFF.pdf`はサンプル ファイルです。任意の PDF ファイルに置き換えることができます。ドキュメント オブジェクトには、さらに操作するための PDF が保持されます。

## ステップ3: 画像の出力パスを定義する

次に、標準 TIFF とバイナリ化されたバージョンの両方を含む、生成された TIFF ファイルの出力パスを指定します。

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

これらのパスを分離することで、標準の TIFF 変換用のファイルと、Bradley アルゴリズムを適用した後の 2 値化された画像用のファイルが 1 つずつ作成されます。

## ステップ4: 解決オブジェクトを作成する

PDF を TIFF に変換する場合、解像度は画像の品質を決定する上で重要な役割を果たします。ここでは、高品質の出力を確保するために 300 DPI に設定します。

```csharp
Resolution resolution = new Resolution(300);
```

DPI が高いほど、特に印刷またはアーカイブされるドキュメントを扱う場合に、画像の鮮明度が向上します。

## ステップ5: TIFF設定を構成する

次に、TIFF 画像の設定を構成する必要があります。ここでは、LZW 圧縮を使用し、色深度を 1bpp (ピクセルあたり 1 ビット) に設定してバイナリ画像を実現します。

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
```

深度を 1bpp に設定することで、画像をバイナリ出力用に準備します。LZW 圧縮は、品質を損なうことなくファイル サイズを縮小する効率性から選択されています。

## ステップ6: TIFFデバイスを作成する

ここで、変換を処理する TIFF デバイスを作成する必要があります。このデバイスは、前に定義した解像度と TIFF 設定を使用します。

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

TIFF デバイスはこの操作の中核です。PDF ドキュメントを取得し、事前定義された設定に基づいて各ページを TIFF 画像に変換します。

## ステップ7: PDFページをTIFFに変換する

PDFを処理して最初のページをTIFF画像に変換します。`Process`この方法を使用すると、特定のページまたはドキュメント全体を変換できます。この例では、最初のページを変換しています。

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

メソッドが完了すると、前に定義した場所に TIFF 画像が保存されます。

## ステップ8: Bradley二値化アルゴリズムを適用する

ここで魔法の Bradley アルゴリズムが登場します。このアルゴリズムは、グレースケールの TIFF 画像をバイナリ画像に変換し、ドキュメント認識システム用に最適化します。

```csharp
using (FileStream inStream = new FileStream(outputImageFile, FileMode.Open))
{
    using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
    {
        tiffDevice.BinarizeBradley(inStream, outStream, 0.1);
    }
}
```

 BinarizeBradleyメソッドは、2つのファイルストリーム（入力と出力）としきい値（ここでは、`0.1`) によって、2 値化レベルが決まります。実行すると、完全に 2 値化された画像が使用できるようになります。

## ステップ9: 変換が成功したことを確認する

最後に、プロセスが成功したことをユーザーに知らせることをお勧めします。これは、簡単なコンソール出力で行うことができます。

```csharp
System.Console.WriteLine("Conversion using Bradley algorithm performed successfully!");
```

これが印刷されると、PDF ページがバイナリ TIFF 画像に正常に変換されたことがわかります。

## 結論

これで完了です。Aspose.PDF for .NET を使用して PDF ページを TIFF 画像に変換し、Bradley 2 値化アルゴリズムを適用する方法を学習しました。このプロセスは、ドキュメントのアーカイブ、光学式文字認識 (OCR)、およびその他の専門的なアプリケーションに不可欠です。高品質の解像度と効率的な圧縮により、ドキュメント イメージが鮮明で扱いやすいサイズになることが保証されます。

## よくある質問

### ブラッドリーアルゴリズムとは何ですか?
ブラッドリー アルゴリズムは、周囲の状況に基づいて各ピクセルの適応しきい値を決定することにより、グレースケール画像をバイナリ (白黒) 画像に変換する 2 値化手法です。

### この方法を使用して複数の PDF ページを TIFF に変換できますか?
はい、変更できます`Process`ドキュメント内のページをループしてすべてのページを変換するメソッド。

### PDF を TIFF に変換する場合の最適な解像度は何ですか?
高画質の画像の場合、通常は 300 DPI が推奨されます。ただし、必要に応じてこの値を調整できます。

### 色深度における 1bpp とはどういう意味ですか?
1bpp (ピクセルあたり 1 ビット) は、画像が白黒になり、各ピクセルが完全に黒か完全に白になることを意味します。

### Bradley アルゴリズムは OCR に適していますか?
はい、Bradley アルゴリズムはスキャンされたドキュメント内のテキストのコントラストを強調するため、OCR の前処理でよく使用されます。