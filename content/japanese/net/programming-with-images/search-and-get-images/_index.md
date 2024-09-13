---
title: PDF ファイル内の画像を検索して取得する
linktitle: PDF ファイル内の画像を検索して取得する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルから画像を簡単に抽出する方法を学びます。このステップ バイ ステップ ガイドに従って、PDF 処理スキルを向上させましょう。
type: docs
weight: 260
url: /ja/net/programming-with-images/search-and-get-images/
---
## 導入

Aspose.PDF for .NET を使用して PDF ファイルから画像を抽出する簡単な方法をお探しですか? まさにうってつけの場所です! この記事では、PDF ドキュメントに埋め込まれた画像を効果的に検索して取得する方法について詳しく説明します。熟練した開発者でも、PDF 操作の世界に足を踏み入れたばかりでも、このガイドではプロセス全体をステップごとに説明します。

## 前提条件

コードの細部に入る前に、リストにチェックを入れる必要のある前提条件がいくつかあります。 

### .NET フレームワーク

お使いのマシンに .NET Framework がインストールされていることを確認してください。Aspose.PDF for .NET はさまざまなバージョンと互換性がありますが、最新の機能と改善点をすべて活用するには、最新の安定リリースを使用することをお勧めします。

### Aspose.PDF ライブラリ

Aspose.PDF ライブラリにアクセスする必要があります。まだアクセスしていない場合は、次のリンクからダウンロードできます。[Aspose.PDF for .NET をダウンロード](https://releases.aspose.com/pdf/net/)さらに、[1ヶ月無料トライアル](https://releases.aspose.com/)無料でプロジェクトを開始できます。

### 開発環境

コードをシームレスに記述して実行するには、Visual Studio や好みの IDE などの適切な開発環境を設定する必要があります。

## パッケージのインポート

Aspose.PDF for .NET を使用するには、まず適切な名前空間をプロジェクトにインポートする必要があります。必要な手順は次のとおりです。

```csharp
using System.IO;
using Aspose.Pdf;
using System;
```

これらのパッケージはそれぞれ、PDF文書を操作する際に特定の目的を果たします。`Aspose.Pdf`名前空間は操作の基礎であり、他の 2 つは PDF 内の画像とテキストの処理に役立ちます。

## ステップ1: ドキュメントパスを設定する

まず最初に、PDF ファイルが保存されているパスを定義する必要があります。次のコードでそれを設定します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 「YOUR DOCUMENT DIRECTORY」をPDFファイルを含むディレクトリへの実際のパスに置き換えます。例:`C:\Documents\`.

## ステップ2: PDFドキュメントを開く

次に、PDF文書をアプリケーションに読み込みます。これは、新しい`Document`指定したファイル パスを持つインスタンスを作成します。

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SearchAndGetImages.pdf");
```

## ステップ3: ImagePlacementAbsorberを作成する

PDF内の画像を検索するには、`ImagePlacementAbsorber`オブジェクト。このクラスは、抽出プロセス中に PDF から画像を吸収するのに役立ちます。

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
```

## ステップ4: すべてのページでアブソーバーを受け入れる

このステップは、`Document`すべてのページに画像吸収体を適用します。これにより、ドキュメント内のどこに配置した画像も確実に識別されます。

```csharp
doc.Pages.Accept(abs);
```

## ステップ5: 画像の配置をループする

画像を理解したら、次は画像を詳しく調べます。PDF から抽出した各画像の配置をループします。

```csharp
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
    //画像のプロパティを取得するためのさらなる手順
}
```

## ステップ6: 画像のプロパティを抽出する

ループ内では、各画像に関する貴重なプロパティの取得を開始できます。`imagePlacement`オブジェクトでは、寸法と解像度にアクセスできます。

```csharp
XImage image = imagePlacement.Image; //画像を取得する

Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
```

## 結論

これで完了です。これらの手順に従うと、Aspose.PDF for .NET を使用して PDF ファイルから画像を効率的に検索して取得できます。わずか数行のコードで、貴重な画像とそのプロパティを抽出でき、アプリケーションに多くの可能性が開かれます。

## よくある質問

### Aspose.PDF ライブラリは無料で使用できますか?  
Aspose.PDF for .NET は有料ライブラリですが、1 か月間の無料試用版をダウンロードできます。

### パスワードで保護された PDF ファイルから画像を抽出できますか?  
はい、ただし、ドキュメントを開くときにパスワードを入力する必要があります。

### PDF から抽出できる画像の種類は何ですか?  
形式（JPEG、PNG など）に関係なく、埋め込まれたすべての画像を抽出できます。

### 抽出できる画像の数に制限はありますか?  
厳密な制限はなく、PDF ファイル自体によって異なります。

### 抽出した画像をディスクに保存できますか?  
はい、画像をディスクに保存するには、`XImage`コード内のオブジェクト。