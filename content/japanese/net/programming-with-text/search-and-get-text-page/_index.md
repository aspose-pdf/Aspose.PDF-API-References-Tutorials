---
title: PDF ファイル内のテキスト ページを検索して取得する
linktitle: PDF ファイル内のテキスト ページを検索して取得する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内の特定のページからテキストを検索して取得する方法を学習します。
type: docs
weight: 430
url: /ja/net/programming-with-text/search-and-get-text-page/
---
## 導入

PDF ドキュメント内の特定のテキストを検索し、それを抽出してさらに使用したいと思ったことはありませんか? ドキュメントを処理し、正確なデータ抽出を必要とするアプリを構築している場合や、PDF を効率的に解析する必要がある場合など、どのような場合でも、このチュートリアルは役に立ちます。このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイル内のページからテキストを検索して取得する方法について詳しく説明します。初心者でも熟練した開発者でも、このガイドでは会話形式で各ステップをわかりやすく説明します。準備はできましたか? さあ、始めましょう!

## 前提条件

コーディングを始める前に、必要なものがすべて揃っていることを確認しましょう。

1.  Aspose.PDF for .NETライブラリ:以下からダウンロードできます。[ここ](https://releases.aspose.com/pdf/net/)または同じリンクから無料試用版を入手してください。購入については、[Aspose ストア](https://purchase.aspose.com/buy).
2. .NET Framework: Visual Studio などの動作する .NET 開発環境が必要です。
3. PDFファイル: テキストを検索して抽出できるサンプルPDFファイルが必要です。このチュートリアルでは、ファイル名が`SearchAndGetTextPage.pdf`.

## パッケージのインポート

まず最初に、Aspose.PDF for .NET を操作するために必要な名前空間をインポートする必要があります。これらがコードの先頭に含まれていることを確認してください。

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System
```

前提条件について説明したので、コードをステップごとに分解してみましょう。各ステップはわかりやすく説明されているため、簡単に理解できます。

## ステップ1: ドキュメントディレクトリへのパスを設定する

PDF を操作する前に、PDF ドキュメントが保存されている場所へのパスを定義する必要があります。これにより、プログラムがファイルにアクセスできるようになります。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  dataDir: PDFファイルが保存されているフォルダへのパスです。`"YOUR DOCUMENT DIRECTORY"` PDF が配置されている実際のパスを入力します。

## ステップ2: PDFドキュメントを読み込む

次のステップは、PDF ドキュメントをメモリにロードして操作できるようにすることです。手順は次のとおりです。

```csharp
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

- Document: これは PDF ファイルを読み込む Aspose.PDF クラスです。
- pdfDocument: 読み込まれた後に PDF ファイルが保存される変数。

## ステップ3: テキスト吸収オブジェクトを作成する

の`TextFragmentAbsorber`クラスを使用すると、PDF 内の特定のテキストを検索できます。このクラスのインスタンスを作成し、指定された検索フレーズのすべてのインスタンスを検索してみましょう。

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

- TextFragmentAbsorber: このクラスは、PDF からテキストを検索して抽出する役割を担います。
- 「図」: PDF 内で検索する任意のテキストに置き換えます。

## ステップ4: PDF全体にテキストアブソーバーを適用する

テキスト吸収機能を設定したら、プログラムに PDF のすべてのページを検索するように指示する必要があります。

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

- Accept(): このメソッドは、PDF にテキスト アブソーバーを適用し、指定したテキストをすべてのページでスキャンします。

## ステップ5: 抽出したテキストを取得して反復処理する

PDF をスキャンしたので、結果を取得して表示します。抽出されたテキスト フラグメントをループします。

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- TextFragmentCollection: このコレクションには、テキスト アブソーバーによって検出されたテキスト フラグメントのすべてのインスタンスが保持されます。

## ステップ6: 各フラグメントをループしてデータを抽出する

次はループして`textFragmentCollection`各テキストセグメントの位置、フォントの詳細、色などのさまざまなプロパティを抽出します。

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

- TextFragment: 各フラグメントには、見つかったテキストの一部が含まれます。
- TextSegment: 各フラグメントには、テキストのさまざまな部分を表す複数のセグメントを含めることができます。
- TextState: テキストのフォント、サイズ、色に関する詳細な情報を提供します。

このループでは、実際のテキスト、その位置 (X 座標と Y 座標)、フォント、フォントが PDF に埋め込まれているかどうか、テキストの前景色などの詳細を出力します。

## 結論

これで完了です。Aspose.PDF for .NET を使用して PDF ファイルからテキストを検索し、抽出することができました。このライブラリの柔軟性は驚くほどです。大きなドキュメント内の特定のテキストを検索したり、抽出したり、そのプロパティを分析したりする必要がある場合でも、Aspose.PDF を使用すると簡単にできます。さらに、ここで説明したコードを使用すると、ニーズに合わせて調整できます。 

## よくある質問

### 一度に複数のフレーズを検索できますか?  
はい、複数のフレーズを検索するためにコードを変更することができます。`TextFragmentAbsorber`オブジェクト。

### 特定のページからテキストを抽出するにはどうすればよいですか?  
特定のページをターゲットにするには、`TextFragmentAbsorber`ドキュメント全体ではなく、1 つのページに分割します。例:`pdfDocument.Pages[1].Accept(textFragmentAbsorber);`.

### Aspose.PDF for .NET は無料ですか?  
 Aspose.PDFは商用製品ですが、[無料トライアル](https://releases.aspose.com/).

### Aspose.PDF を使用して PDF から画像を抽出できますか?  
はい、Aspose.PDFではテキストに加えて画像も抽出できます。[ドキュメント](https://reference.aspose.com/pdf/net/)詳細についてはこちらをご覧ください。

### さらにヘルプやサポートが必要な場合はどうすればいいですか?  
いつでもサポートを受けることができます[Aspose サポート フォーラム](https://forum.aspose.com/c/pdf/10).