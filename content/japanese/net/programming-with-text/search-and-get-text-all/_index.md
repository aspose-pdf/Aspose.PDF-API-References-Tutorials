---
title: すべてのテキストを検索して取得する
linktitle: すべてのテキストを検索して取得する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ドキュメントのすべてのページからテキストを検索して取得する方法を学びます。
type: docs
weight: 420
url: /ja/net/programming-with-text/search-and-get-text-all/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントのすべてのページからテキストを検索して取得する方法について説明します。提供されている C# ソース コードは、プロセスを段階的に示しています。

## 前提条件

チュートリアルを進める前に、次のものが揃っていることを確認してください。

- C# プログラミング言語の基本的な知識。
- Aspose.PDF for .NET ライブラリがインストールされています。 Aspose Web サイトから入手するか、NuGet を使用してプロジェクトにインストールできます。

## ステップ 1: プロジェクトをセットアップする

まず、好みの統合開発環境 (IDE) で新しい C# プロジェクトを作成し、Aspose.PDF for .NET ライブラリへの参照を追加します。

## ステップ 2: 必要な名前空間をインポートする

C# ファイルの先頭に次の using ディレクティブを追加して、必要な名前空間をインポートします。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## ステップ 3: PDF ドキュメントをロードする

 PDF ドキュメント ディレクトリへのパスを設定し、`Document`クラス：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

必ず交換してください`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを置き換えます。

## ステップ 4: テキストを検索して抽出する

を作成します`TextFragmentAbsorber`オブジェクトを使用して、入力検索フレーズのすべてのインスタンスを検索します。

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

交換する`"text"`検索したい実際のテキストを入力します。

## ステップ 5: すべてのページで検索する

ドキュメントのすべてのページに対して吸収体を受け入れます。

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## ステップ 6: 抽出されたテキスト断片を取得する

を使用して、抽出されたテキストの断片を取得します。`TextFragments`の財産`TextFragmentAbsorber`物体：

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## ステップ 7: テキストの断片をループする

getd テキスト フラグメントをループし、そのプロパティにアクセスします。

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
    Console.WriteLine("Text: {0} ", textFragment.Text);
    Console.WriteLine("Position: {0} ", textFragment.Position);
    Console.WriteLine("XIndent: {0} ", textFragment.Position.XIndent);
    Console.WriteLine("YIndent: {0} ", textFragment.Position.YIndent);
    Console.WriteLine("Font - Name: {0}", textFragment.TextState.Font.FontName);
    Console.WriteLine("Font - IsAccessible: {0} ", textFragment.TextState.Font.IsAccessible);
    Console.WriteLine("Font - IsEmbedded: {0} ", textFragment.TextState.Font.IsEmbedded);
    Console.WriteLine("Font - IsSubset: {0} ", textFragment.TextState.Font.IsSubset);
    Console.WriteLine("Font Size: {0} ", textFragment.TextState.FontSize);
    Console.WriteLine("Foreground Color: {0} ", textFragment.TextState.ForegroundColor);
}
```

ループ内のコードを変更して、各テキスト断片に対してさらにアクションを実行できます。

### Aspose.PDF for .NET を使用した Search And Get Text All のサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開いた文書
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
//TextAbsorber オブジェクトを作成して、入力検索フレーズのすべてのインスタンスを検索します
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
//すべてのページに吸収体を受け入れる
pdfDocument.Pages.Accept(textFragmentAbsorber);
//抽出されたテキスト断片を取得する
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
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

## 結論

おめでとう！ Aspose.PDF for .NET を使用して、PDF ドキュメントのすべてのページからテキストを検索して取得する方法を学習しました。このチュートリアルでは、ドキュメントの読み込みから抽出されたテキスト フラグメントへのアクセスまで、段階的なガイドを提供しました。このコードを独自の C# プロジェクトに組み込んで、PDF ファイル内のテキスト コンテンツを分析および処理できるようになりました。

### よくある質問

#### Q: 「検索してテキストをすべて取得」チュートリアルの目的は何ですか?

A: 「すべてのテキストを検索して取得」チュートリアルでは、.NET の Aspose.PDF ライブラリを利用して、PDF ドキュメントのすべてのページからテキストを検索および抽出する方法を示します。このチュートリアルでは、テキストの検索と取得を実行するための段階的な手順とサンプル C# コードを提供します。

#### Q: このチュートリアルは PDF ドキュメントからテキストを抽出する際にどのように役立ちますか?

A: このチュートリアルでは、PDF ドキュメントのすべてのページからテキストを抽出するプロセスを説明します。 Aspose.PDF ライブラリを使用して、特定のテキスト フレーズを検索し、位置、フォント プロパティ、色などの関連情報を取得します。

#### Q: このチュートリアルを実行するための前提条件は何ですか?

A: このチュートリアルを開始する前に、C# プログラミング言語の基本を理解しておく必要があります。さらに、Aspose.PDF for .NET ライブラリをインストールする必要があります。 Aspose Web サイトから入手することも、NuGet を使用してプロジェクトに統合することもできます。

#### Q: このチュートリアルに従うようにプロジェクトを設定するにはどうすればよいですか?

A: まず、お好みの統合開発環境 (IDE) で新しい C# プロジェクトを作成し、Aspose.PDF for .NET ライブラリへの参照を追加します。これにより、プロジェクト内のライブラリの機能にアクセスできるようになります。

#### Q: PDF ドキュメント内の特定のテキストを検索するにはどうすればよいですか?

A: を使用できます。`TextFragmentAbsorber`PDF ドキュメント内の特定の検索フレーズのインスタンスを検索するクラス。このクラスのインスタンスを作成し、ターゲット テキストを指定すると、そのテキストの出現箇所をすべてキャプチャできます。

#### Q: PDF ドキュメントの全ページにわたってテキストを検索できますか?

 A: はい、このチュートリアルでは、PDF ドキュメントのすべてのページにわたってテキストを検索する方法を示します。の`pdfDocument.Pages.Accept(textFragmentAbsorber)`メソッドを使用してすべてのページのアブソーバーを受け入れることで、すべてのページで目的のテキストを検索できるようになります。

#### Q: 抽出されたテキスト断片にアクセスするにはどうすればよいですか?

 A: テキストを検索した後、抽出されたテキストの断片にアクセスするには、`TextFragments`の財産`TextFragmentAbsorber`物体。このプロパティは、次のコレクションへのアクセスを提供します。`TextFragment`抽出されたテキストと関連情報を含むオブジェクト。

#### Q: 抽出されたテキスト断片からどのような情報を取得できますか?

A: 抽出されたテキストの断片から、実際のテキストの内容、位置 (X および Y 座標)、フォント情報 (名前、サイズ、色など) などのさまざまな詳細を取得できます。チュートリアルのサンプル コードでは、これらの詳細にアクセスして印刷する方法を示します。

#### Q: 抽出されたテキストの断片に対してさらにアクションを実行できますか?

A: もちろんです。テキスト フラグメントを抽出したら、ループ内のコードを変更して各フラグメントに対してカスタム アクションを実行できます。これには、抽出されたテキストの保存、テキスト パターンの分析、または書式変更の適用が含まれる場合があります。