---
title: 検索してテキストをすべて取得
linktitle: 検索してテキストをすべて取得
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ドキュメントのすべてのページからテキストを検索して取得する方法を学習します。
type: docs
weight: 420
url: /ja/net/programming-with-text/search-and-get-text-all/
---
## 導入

PDF から特定のテキストを抽出したいと思ったことはありませんか? PDF は、ロックされたコンテナのように感じられることがあり、必要な情報を取得するのが困難です。しかし、朗報があります。Aspose.PDF for .NET を使用すると、あらゆる PDF からテキストを簡単に検索して取得できます。この強力なライブラリには、.NET アプリケーションで PDF を操作するために必要なものがすべて用意されており、テキスト抽出が簡単になります。このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルからテキストを検索して抽出するプロセスを順を追って説明します。テキスト分析ツールを構築している場合でも、PDF レポートからのデータ抽出を自動化する必要がある場合でも、このチュートリアルは最適です。

## 前提条件

コードに進む前に、すべてが設定されていることを確認しましょう。

1. Aspose.PDF for .NET: Aspose.PDF for .NETをダウンロードしてインストールする必要があります。ダウンロードページから入手できます。[ここ](https://releases.aspose.com/pdf/net/).
2. .NET 環境: 開発マシンに .NET Framework または .NET Core が設定されていることを確認します。
3. 基本的な C## の知識: C# と .NET プロジェクトの操作についてある程度の知識があることが推奨されます。
4.  PDF文書: テキストを抽出するサンプルPDFファイル。この例では、`SearchAndGetTextFromAll.pdf`.

## パッケージのインポート

コードを記述する前に、Aspose.PDF を操作するために必要な名前空間をプロジェクトにインポートする必要があります。

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

これらの名前空間は、PDF のドキュメント オブジェクト モデルへのアクセスを提供し、ファイル内のテキストを操作できるようにします。

簡単に実行できるように、プロセスを簡単なステップに分解してみましょう。

## ステップ1: ドキュメントディレクトリを設定する

まず最初に、PDF が保存されているディレクトリへのパスを指定する必要があります。これにより、アプリケーションはテキストを抽出するファイルを見つけやすくなります。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

- の`dataDir`変数は、`SearchAndGetTextFromAll.pdf`ファイルが保存されます。
- 交換する`"YOUR DOCUMENT DIRECTORY"`マシン上の実際のパスを使用します。

## ステップ2: PDFドキュメントを開く

次に、Aspose.PDFの`Document`物体。

```csharp
//ドキュメントを開く
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

- 新しいインスタンスを作成します`Document`PDF の完全なファイル パスを渡すことでクラスを作成します。
- これにより、PDF がメモリに読み込まれ、処理の準備が整います。

## ステップ3: テキストアブソーバーを作成する

の`TextFragmentAbsorber`オブジェクトは、PDF 内の特定のテキストを検索するために使用されます。この場合、「テキスト」という単語を検索します。

```csharp
//入力された検索フレーズのすべてのインスタンスを検索する TextAbsorber オブジェクトを作成します。
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

- の`TextFragmentAbsorber`文字列で初期化される`"text"`これは、PDF ドキュメント内で「テキスト」という単語の出現を検索することを意味します。

## ステップ4: すべてのページでアブソーバーを受け入れる

ここで、PDF ドキュメントにアブソーバーを受け入れ、すべてのページでテキストを検索するように指示します。

```csharp
//すべてのページの吸収剤を受け入れる
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

- の`Accept`メソッドはドキュメントのページに適用されます。これにより、指定されたテキストがすべてのページで検索されます。

## ステップ5: テキストフラグメントの抽出

アブソーバーが文書をスキャンすると、抽出されたテキストの断片を取得できます。

```csharp
//抽出されたテキストフラグメントを取得する
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- の`TextFragments`の財産`TextFragmentAbsorber`検索語に一致するすべてのテキストフラグメントのコレクションを返します。

## ステップ6: テキストフラグメントをループする

テキストフラグメントのコレクションができたので、それらをループして詳細を抽出します。

```csharp
//フラグメントをループする
foreach (TextFragment textFragment in textFragmentCollection)
{
    Console.WriteLine("Text : {0} ", textFragment.Text);
    Console.WriteLine("Position : {0} ", textFragment.Position);
    Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
    Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
    Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
    Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
    Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
    Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
    Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
    Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

- の`foreach`ループはそれぞれを繰り返す`TextFragment`コレクション内。
- 実際のテキスト、ページ上の位置、フォントの詳細、フォント サイズなど、各フラグメントのさまざまなプロパティを印刷します。
- の`XIndent`そして`YIndent`プロパティは、PDF 内のテキスト フラグメントの正確な座標を示します。

## 結論

これで完了です。わずか数行のコードで、Aspose.PDF for .NET を使用して PDF からテキストを検索し、抽出することができました。Aspose.PDF の柔軟性により、さまざまな方法で PDF を操作できるため、.NET 環境で堅牢な PDF ソリューションを必要とする開発者にとって最適な選択肢となります。この例を簡単に拡張して、他の単語を検索したり、詳細を抽出したり、必要に応じて PDF コンテンツを操作したりすることもできます。このガイドが、PDF を操作するための明確でわかりやすいアプローチを提供できたことを願っています。ぜひ、ご自分の PDF で試してみてください。

## よくある質問

### 一度に複数の単語を検索できますか?  
はい、変更できます`TextFragmentAbsorber`検索文字列を調整して複数のフレーズを検索します。

### テキストが複数行にまたがる場合はどうなりますか?  
Aspose.PDF は、複数行にまたがるテキストでも認識して抽出します。これらのフラグメントは個別に処理できます。

### 抽出したテキストをファイルに保存するにはどうすればよいですか?  
抽出したテキストは、次のような標準のC#ファイルI/O操作を使用してファイルに書き込むことができます。`StreamWriter`.

### Aspose.PDF はスキャンされた PDF からのテキスト抽出をサポートしていますか?  
Aspose.PDF は OCR をサポートしていません。スキャンされた PDF の場合、テキストを認識するには OCR ツールが必要になります。

### 暗号化された PDF をどのように処理すればよいですか?  
PDF がパスワードで保護されている場合は、ドキュメントを読み込むときにパスワードを入力することで、Aspose.PDF を使用してロックを解除できます。