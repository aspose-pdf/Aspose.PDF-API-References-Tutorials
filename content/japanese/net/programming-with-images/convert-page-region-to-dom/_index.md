---
title: ページ領域を DOM に変換
linktitle: ページ領域を DOM に変換
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用すると、PDF ページの特定の領域をドキュメント オブジェクト モデル (DOM) に簡単に変換できます。
type: docs
weight: 80
url: /ja/net/programming-with-images/convert-page-region-to-dom/
---
このガイドでは、Aspose.PDF for .NET を使用してページの特定の領域をドキュメント オブジェクト モデル (DOM) に変換する方法を段階的に説明します。環境がすでにセットアップされていることを確認し、以下の手順に従ってください。

## ステップ 1: ドキュメント ディレクトリを定義する

開始する前に、ドキュメント用に正しいディレクトリを設定していることを確認してください。交換する`"YOUR DOCUMENT DIRECTORY"`コード内で、PDF ドキュメントが配置されているディレクトリへのパスを指定します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: ドキュメントを開く

このステップでは、`Document` Aspose.PDF のクラス。使用`Document`コンストラクターを開き、PDF ドキュメントへのパスを渡します。

```csharp
Document document = new Document(dataDir + "AddImage.pdf");
```

## ステップ 3: ページ領域の四角形を取得する

このステップでは、DOM に変換するページの特定の領域を表す四角形を定義します。使用`Aspose.Pdf.Rectangle`四角形の座標を定義するクラス。

```csharp
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
```

## ステップ 4: ページのトリミング領域を定義する

使用`CropBox`の財産`Page`オブジェクトを使用して、ページのクロップ ボックスを目的の領域の四角形に設定します。

```csharp
document.Pages[1].CropBox = pageRect;
```

## ステップ 5: トリミングされた PDF ドキュメントをストリームに保存する

このステップでは、トリミングされた PDF ドキュメントをストリームに保存します。`MemoryStream`クラス。

```csharp
MemoryStream ms = new MemoryStream();
document.Save(ms);
```

## ステップ 6: トリミングされた PDF ドキュメントを開いて画像に変換する

トリミングされた PDF ドキュメントを開くには、`Document`クラスを取得して画像に変換します。 300 dpi の解像度を使用します。

```csharp
document = newDocument(ms);
Resolution resolution = new Resolution(300);
PngDevice pngDevice = new PngDevice(resolution);
```

## ステップ 7: 特定のページを画像に変換する

を使用して特定のページを画像に変換します。`Process`の方法`pngDevice`物体。画像の出力パスを指定します。

```csharp
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
pngDevice.Process(document.Pages[1], dataDir);
```

### Aspose.PDF for .NET を使用してページ領域を DOM に変換するサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開いた文書
Document document = new Document( dataDir + "AddImage.pdf");
//特定のページ領域の四角形を取得する
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
//目的のページ領域の四角形ごとに CropBox 値を設定します
document.Pages[1].CropBox = pageRect;
//切り取ったドキュメントをストリームに保存する
MemoryStream ms = new MemoryStream();
document.Save(ms);
//トリミングされた PDF ドキュメントを開いて画像に変換する
document = new Document(ms);
//解像度オブジェクトの作成
Resolution resolution = new Resolution(300);
//指定した属性を持つ PNG デバイスを作成する
PngDevice pngDevice = new PngDevice(resolution);
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
//特定のページを変換し、画像をストリームに保存します
pngDevice.Process(document.Pages[1], dataDir);
ms.Close();
Console.WriteLine("\nPage region converted to DOM successfully.\nFile saved at " + dataDir); 
```

## 結論

おめでとうございます！ Aspose.PDF for .NET を使用して、ページの特定の領域をドキュメント オブジェクト モデル (DOM) に変換することに成功しました。結果のイメージは指定されたディレクトリに保存されます。これで、このイメージをプロジェクトまたはアプリケーションで使用できるようになります。

## よくある質問

#### Q: Aspose.PDF for .NET を使用してページの特定の領域をドキュメント オブジェクト モデル (DOM) に変換する目的は何ですか?

A: PDF ページの特定の領域をドキュメント オブジェクト モデル (DOM) に変換すると、PDF ドキュメント内のコンテンツの特定のセクションを抽出して操作するのに役立ちます。

#### Q: Aspose.PDF for .NET は、特定のページ領域の DOM への変換をどのように容易にしますか?

A: Aspose.PDF for .NET は、目的のページ領域の定義、トリミング領域の設定、トリミングされた PDF ドキュメントのストリームへの保存、指定されたページ領域の画像への変換を行うための段階的なプロセスを提供します。

#### Q: 変換プロセスを開始する前にドキュメント ディレクトリを定義することが重要なのはなぜですか?

A: ドキュメント ディレクトリを指定すると、PDF ドキュメントと結果の画像が目的の出力パスに正しく配置されます。

####  Q: どうやって`Document` class in Aspose.PDF for .NET help in the conversion process?

 A:`Document`クラスを使用すると、PDF ドキュメントを開いて操作し、保存することができます。この場合、PDF ドキュメントをロードし、そのトリミングされたバージョンを作成するために使用されます。

####  Q：その目的は何ですか？`Rectangle` class in the page region conversion process?

 A:`Rectangle`クラスは、DOM に変換する PDF ページ上の特定の領域の座標を定義します。トリミング領域を正確に指定するのに役立ちます。

#### Q: 変換プロセスにおいて、ページのトリミング領域はどのようにして希望の領域に設定されますか?

 A:`CropBox`の財産`Page`オブジェクトは、ページのトリミング領域を、特定の領域を表す定義された四角形に設定するために使用されます。

#### Q: 変換プロセス中に、トリミングされた PDF ドキュメントはどのようにストリームに保存されますか?

 A: トリミングされた PDF ドキュメントは次の場所に保存されます。`MemoryStream`オブジェクトを使用すると、PDF コンテンツを効率的に操作できるようになります。

####  Q：どのような役割をするのですか`PngDevice` class play in the page region to DOM conversion process?

 A:`PngDevice`クラスは、トリミングされた PDF ドキュメントを PNG などの画像形式に変換するのに役立ち、特定のページ領域を視覚化できるようになります。

#### Q: 変換プロセス中に、結果の画像の解像度やその他の属性を調整できますか?

 A: はい、設定することで、結果の画像の解像度やその他の属性を変更できます。`PngDevice`ページを変換する前のオブジェクト。