---
title: PDF ファイル内の列テキストの抽出
linktitle: PDF ファイル内の列テキストの抽出
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルからテキストの列を抽出する方法を学習します。このガイドでは、コード例と説明を使用して各手順を詳しく説明します。
type: docs
weight: 150
url: /ja/net/programming-with-text/extract-columns-text/
---
## 導入

PDF ファイルで作業していて、特定の列形式でテキストを抽出する必要がありますか? 請求書、レポート、または構造化されたドキュメントを処理する場合でも、PDF からテキストを正確に抽出するのは難しい場合があります。ここで、Aspose.PDF for .NET が介入してプロセスを簡素化します。このチュートリアルでは、PDF ファイルからテキストの列を簡単に抽出する方法を説明します。 

## 前提条件

コードに進む前に、必要な基本的な事項について説明しましょう。

-  Aspose.PDF for .NET: Aspose.PDF for .NETの最新バージョンがインストールされていることを確認してください。そうでない場合は、[ここからダウンロード](https://releases.aspose.com/pdf/net/).
- 開発環境: コードを操作するには、Visual Studio または別の .NET 開発環境が必要です。
- PDF ドキュメント: サンプルの PDF ドキュメントを用意してください。できればテキストの列があるものがよいでしょう。そこからテキストを抽出するからです。

 Aspose.PDF for .NETをまだインストールしていない場合は、[無料トライアル](https://releases.aspose.com/)または[ライセンスを購入する](https://purchase.aspose.com/buy)フル機能をご利用いただけます。[一時ライセンス](https://purchase.aspose.com/temporary-license)必要であれば。

## 名前空間のインポート

プロジェクトで Aspose.PDF for .NET を使用するには、次の名前空間をインポートする必要があります。

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

## ステップバイステップガイド: PDF からテキストの列を抽出する

それでは、コードの各部分を分解して、その仕組みをよりよく理解しましょう。プロセスの各セグメントを説明しながら、ステップごとに進めていきましょう。

## ステップ1: PDFドキュメントを読み込む

まず最初にPDFファイルを読み込みます。`Document`オブジェクト。これが Aspose.PDF がドキュメントと対話する方法です。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

このステップでは、PDF文書が保存されるディレクトリを定義するだけです。`"YOUR DOCUMENT DIRECTORY"`ローカルPDFファイルへのパスを入力します。`Document`オブジェクトは PDF をメモリに読み込み、さらに処理するためにアクセスできるようにします。

## ステップ2: テキストフラグメント吸収装置を設定する

次に、`TextFragmentAbsorber` PDF ファイルからすべてのテキストを吸収またはキャプチャします。このアブソーバー クラスは、PDF 内の特定の領域からテキストの断片を抽出するように設計されており、テキストの列を抽出するのに最適です。

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
```

ここでは、`TextFragmentAbsorber`これをPDFのすべてのページに適用するには、`Accept()` 。`TextFragmentCollection`抽出されたテキストを保存し、このコレクションから必要に応じてテキストを操作または抽出できます。

## ステップ3: 抽出したテキストのフォントサイズを調整する

テキストの断片をキャプチャしたら、特に元のテキストが大きすぎる場合は、フォント サイズを縮小する必要があります。この例では、フォント サイズを 70% 縮小しています。

```csharp
foreach (TextFragment tf in tfc)
{
    //フォントサイズを70%縮小
    tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

このコードは各`TextFragment`コレクション内のテキストが削除され、フォント サイズが 70% 縮小されます。フォント サイズを調整すると、特にさまざまな目的に合わせて書式設定する場合に、抽出したテキストを管理しやすくなります。

## ステップ4: ドキュメントをメモリストリームに保存する

テキストを変更した後、PDFを`MemoryStream`これにより、ドキュメントをディスクに書き戻すことなく、メモリ内に保持してさらに処理することができます。

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
```

ここでは、PDF をメモリ ストリームに保存し、ドキュメントを再読み込みします。この方法は、大きなファイルを操作していて、不要なディスク操作を避けたい場合に便利です。

## ステップ5: Text Absorberを使用してすべてのテキストを抽出する

PDFの準備ができたので、次はテキストを抽出します。`TextAbsorber`ドキュメントからすべてのテキストを取得します。

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
```

このステップでは、`TextAbsorber` PDFからすべてのテキストを吸収し、抽出されたテキストは`extractedText`文字列。ここで魔法が起こります。テキストの列がプレーンテキスト形式になります。

## ステップ6: 抽出したテキストをファイルに保存する

最後に、抽出したテキストを`.txt`簡単にアクセスしてさらに使用できるファイル。

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

このコードは抽出したテキストを新しい`.txt`ファイルを作成し、指定したディレクトリに保存します。プロセスが成功したことを確認するメッセージがコンソールに表示されます。

## 結論

これで完了です。Aspose.PDF for .NET を使用して PDF ファイルからテキストの列を抽出するのは、想像以上に簡単です。わずか数行のコードで、PDF を読み込み、特定のテキストを抽出し、書式を調整し、結果をテキスト ファイルに保存できます。

この手法は、表、レポート、列に整理されたコンテンツなどの構造化ドキュメントを処理する場合に非常に便利です。データ抽出を自動化する必要がある場合でも、大量のドキュメントを処理する必要がある場合でも、Aspose.PDF はそれを効率的に実行するためのツールを提供します。

## よくある質問

### PDF の特定のページからテキストを抽出できますか?  
はい！変更することができます`TextFragmentAbsorber`特定のページをターゲットにするには`pdfDocument.Pages[pageIndex].Accept(tfa);`方法。

### 複数列の PDF で 1 つの列からのみテキストを抽出することは可能ですか?  
はい、ただし、テキストフラグメントの座標を次のように操作する必要があります。`TextFragment.Rectangle`ドキュメントの特定の領域をターゲットにします。

### テキスト抽出の精度を向上させるにはどうすればよいですか?  
精度を上げるには、PDFの構造が明確に定義されていることを確認し、複雑なレイアウトの文書は避けてください。`TextFragmentAbsorber`フォント スタイル、サイズ、または領域に基づいてテキストを抽出します。

### Aspose.PDF はスキャンされたドキュメントからのテキスト抽出をサポートしていますか?  
はい、ただし OCR (光学式文字認識) テクノロジを使用する必要があります。Aspose にはそのためのツールも用意されています。

### 何千ページもの大きな PDF ファイルをどのように処理すればよいでしょうか?  
大きな PDF の場合は、メモリ使用量の増加を避けるために、一度に数ページからテキストを抽出してドキュメントをチャンク単位で処理します。