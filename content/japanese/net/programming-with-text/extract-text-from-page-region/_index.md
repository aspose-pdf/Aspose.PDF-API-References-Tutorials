---
title: PDF ファイルのページ領域からテキストを抽出する
linktitle: PDF ファイルのページ領域からテキストを抽出する
second_title: Aspose.PDF for .NET API リファレンス
description: このステップバイステップ ガイドでは、Aspose.PDF for .NET を使用して PDF 内の特定の領域からテキストを抽出する方法を学習します。ドキュメントからテキストを効率的に収集して保存します。
type: docs
weight: 190
url: /ja/net/programming-with-text/extract-text-from-page-region/
---
## 導入

PDF を操作する場合、フォーム、テーブル、またはドキュメントの特定のセクションからデータを取得するなど、特定のコンテンツを抽出する必要がある場合がよくあります。このチュートリアルでは、Aspose.PDF for .NET を使用して PDF の特定の領域からテキストを抽出する方法について説明します。ドキュメント全体を精査するのではなく、テキストが存在する場所を正確に特定し、効率的に抽出します。

## 前提条件

コードに進む前に、次の項目が揃っていることを確認してください。

1.  Aspose.PDF for .NET: まだダウンロードしていない場合は、Aspose.PDF for .NET ライブラリをダウンロードしてインストールします。[Aspose.PDF for .NET をダウンロード](https://releases.aspose.com/pdf/net/).
2. IDE: Visual Studio などの任意の .NET 開発環境。
3. .NET Framework: プロジェクトが適切な .NET Framework で設定されていることを確認します。
4. PDF ドキュメント: テキストを抽出するサンプル PDF。

忘れないでください[無料トライアルを受ける](https://releases.aspose.com/)Aspose.PDFを使用するか、[一時ライセンス](https://purchase.aspose.com/temporary-license/)完全な機能を実現します。

## 必要なパッケージのインポート

Aspose.PDF for .NET の使用を開始するには、必要な名前空間をプロジェクトにインポートする必要があります。これらのパッケージは、PDF ドキュメントの処理に必要なクラスとメソッドを提供します。

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

## ステップ1: ドキュメントディレクトリの設定とPDFの読み込み

最初のステップは、PDF ファイルの場所を指定してプロジェクトに読み込むことです。操作する PDF ファイルへのローカル ディレクトリ パスを使用できます。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF文書を開く
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

この手順により、PDFファイルが正しく読み込まれ、作業の準備が整います。`Document` Aspose.PDF ライブラリのクラスを使用すると、PDF ファイルを操作できます。

## ステップ2: 抽出用にテキストアブソーバーを初期化する

このステップでは、`TextAbsorber`PDF文書からテキストを抽出するために設計されたオブジェクトです。`TextAbsorber`柔軟性があり、特定の地域やページに焦点を当てるようにカスタマイズできます。

```csharp
//テキストを抽出するためのTextAbsorberオブジェクトを作成する
TextAbsorber absorber = new TextAbsorber();
```

の`TextAbsorber`クラスは、指定した境界内のすべてのテキストをキャプチャする強力なツールです。

## ステップ3: テキストを抽出する領域を定義する

ここで魔法が起こります。ページ全体からテキストを取得する代わりに、ページの特定の長方形領域に抽出を制限できます。これは、コンテンツがどこにあるかを正確に知っている場合に最適です。

```csharp
//テキスト抽出を特定の領域に制限する
absorber.TextSearchOptions.LimitToPageBounds = true;
absorber.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
```

の`Rectangle`オブジェクトを使用すると、テキストを抽出する領域の座標（ポイント単位）を定義できます。`TextSearchOptions.LimitToPageBounds`指定された四角形内のテキストのみが抽出されるようにします。

## ステップ4：希望のページでアブソーバーを受け入れる

地域を設定したら、次のステップは`TextAbsorber`テキストを抽出したい特定のページを選択します。ここでは、PDF の最初のページに焦点を当てます。

```csharp
//最初のページの吸収剤を受け入れる
pdfDocument.Pages[1].Accept(absorber);
```

電話をかけることで`Accept`ページ上のメソッドでは、Aspose.PDF にアブソーバーを実行して定義された領域からテキストを収集するように指示します。

## ステップ5: 抽出したテキストを取得して保存する

アブソーバーが仕事を終えたら、抽出したテキストを収集して保存します。このステップでは、テキストを取得して、`.txt`ファイル。

```csharp
//抽出したテキストを取得する
string extractedText = absorber.Text;

//抽出したテキストを保存するためのライターを作成する
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");

//テキストをファイルに書き込む
tw.WriteLine(extractedText);

//ストリームを閉じる
tw.Close();
```

ここでは、`TextWriter`クラスは、抽出されたテキストをテキスト ファイルに書き込むために使用されます。これにより、抽出されたコンテンツが後で使用するために安全に保存されます。

## 結論

 PDFドキュメント内の特定の領域からテキストを抽出することは、特にフォームや表などの構造化されたコンテンツを扱う場合に非常に便利です。Aspose.PDF for .NETを使用すると、わずか数行のコードでこのタスクを実現できます。領域を定義し、`TextAbsorber`抽出したテキストを保存することで、PDF から抽出される内容を完全に制御できます。

小規模なプロジェクトに取り組んでいる場合でも、大規模なドキュメントを管理している場合でも、この方法を使用すると、ドキュメント全体を調べなくても PDF から関連データを効率的に抽出できます。

## よくある質問

### 一度に複数のページからテキストを抽出できますか?
はい、繰り返して`Pages`コレクションの`pdfDocument`、適用することができます`TextAbsorber`複数のページに。

### テキストが PDF の別の領域内にある場合はどうなりますか?
簡単に調整できます`Rectangle`テキストが配置されている領域と一致する座標。

### これはスキャンされた PDF でも機能しますか?
いいえ、スキャンした PDF をテキストに変換するには OCR (光学式文字認識) が必要です。Aspose.PDF には OCR 機能も備わっています。

### 特定のキーワードに基づいてテキストを抽出する方法はありますか?
はい、使えます`TextFragmentAbsorber`キーワードベースのテキスト抽出用。

### 暗号化された PDF からテキストを抽出するにはどうすればよいですか?
まず正しいパスワードを入力して PDF を復号化し、その後テキストの抽出を続行する必要があります。