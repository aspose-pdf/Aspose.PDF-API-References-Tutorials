---
title: PDF ファイル内のテキスト ページを検索して取得する
linktitle: PDF ファイル内のテキスト ページを検索して取得する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、PDF ファイルの特定のページからテキストを検索して取得する方法を学びます。
type: docs
weight: 430
url: /ja/net/programming-with-text/search-and-get-text-page/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイル内の特定のページからテキストを検索して取得する方法について説明します。提供されている C# ソース コードは、プロセスを段階的に示しています。

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

必ず交換してください`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを置き換えます。

## ステップ 4: ページからテキストを検索して抽出する

を作成します`TextFragmentAbsorber`オブジェクトを使用して、特定のページ上の入力検索フレーズのすべてのインスタンスを検索します。

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

交換する`"Figure"`検索したい実際のテキストを入力します。

## ステップ 5: 特定のページで検索する

ドキュメントの特定のページのアブソーバを受け入れます。

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## ステップ 6: 抽出されたテキスト断片を取得する

を使用して、抽出されたテキストの断片を取得します。`TextFragments`の財産`TextFragmentAbsorber`物体：

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## ステップ 7: テキストの断片とセグメントをループする

getd テキスト フラグメントとそのセグメントをループし、そのプロパティにアクセスします。

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text: {0} ", textSegment.Text);
		Console.WriteLine("Position: {0} ", textSegment.Position);
		Console.WriteLine("XIndent: {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent: {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name: {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible: {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded: {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset: {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size: {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color: {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

ループ内のコードを変更して、各テキスト セグメントに対してさらにアクションを実行できます。

### Aspose.PDF for .NET を使用した検索とテキスト ページのサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開いた文書
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
//TextAbsorber オブジェクトを作成して、入力検索フレーズのすべてのインスタンスを検索します
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
//すべてのページに吸収体を受け入れる
pdfDocument.Pages.Accept(textFragmentAbsorber);
//抽出されたテキスト断片を取得する
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
//フラグメントをループする
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

## 結論

おめでとう！ Aspose.PDF for .NET を使用して、PDF ドキュメントの特定のページからテキストを検索して取得する方法を学習しました。このチュートリアルでは、ドキュメントの読み込みから抽出されたテキスト セグメントへのアクセスまで、段階的なガイドを提供しました。組み込むことができるようになりました

### よくある質問

#### Q: 「テキスト ページの検索と取得」チュートリアルの目的は何ですか?

A: 「テキスト ページの検索と取得」チュートリアルは、.NET 用の Aspose.PDF ライブラリを使用して、PDF ファイル内の特定のページからテキストを検索および取得する方法を説明するように設計されています。このチュートリアルでは、プロセスをデモンストレーションするための詳細な手順とサンプル C# コードが提供されます。

#### Q: このチュートリアルは、PDF ドキュメントの特定のページからテキストを抽出するのにどのように役立ちますか?

A: このチュートリアルでは、Aspose.PDF ライブラリを使用して PDF ドキュメントの特定のページからテキストを抽出するプロセスを説明します。必要な手順の概要を説明し、選択したページで指定したテキスト フレーズを検索し、関連するテキスト セグメントを取得するための C# コードを提供します。

#### Q: このチュートリアルを実行するための前提条件は何ですか?

A: このチュートリアルを開始する前に、C# プログラミング言語の基本を理解しておく必要があります。さらに、Aspose.PDF for .NET ライブラリをインストールする必要があります。 Aspose Web サイトから入手することも、NuGet を使用してプロジェクトに統合することもできます。

#### Q: このチュートリアルに従うようにプロジェクトを設定するにはどうすればよいですか?

A: まず、お好みの統合開発環境 (IDE) で新しい C# プロジェクトを作成し、Aspose.PDF for .NET ライブラリへの参照を追加します。これにより、プロジェクトでライブラリの機能を利用できるようになります。

#### Q: PDF ドキュメントの特定のページのテキストを検索できますか?

A: はい、このチュートリアルでは、PDF ドキュメントの特定のページ上のテキストを検索する方法を説明します。それには、`TextFragmentAbsorber`クラスを使用して、選択したページ上の特定のテキストフレーズのインスタンスを見つけます。

#### Q: 特定のページから抽出されたテキストセグメントにアクセスするにはどうすればよいですか?

 A: 指定されたページでテキストを検索した後、抽出されたテキストセグメントにアクセスできます。`TextSegments`の財産`TextFragment`物体。このプロパティは、次のコレクションへのアクセスを提供します。`TextSegment`抽出されたテキストと関連情報を含むオブジェクト。

#### Q: 抽出されたテキストセグメントからどのような情報を取得できますか?

A: 抽出されたテキスト セグメントから、テキストの内容、位置 (X および Y 座標)、フォント情報 (名前、サイズ、色など) などのさまざまな詳細を取得できます。チュートリアルのサンプル コードでは、テキスト セグメントごとにこれらの詳細にアクセスして印刷する方法を示します。

#### Q: 抽出されたテキストセグメントに対してカスタムアクションを実行できますか?

A: 確かに。テキストセグメントを抽出したら、ループ内のコードをカスタマイズして、各セグメントに対して追加のアクションを実行できます。これには、抽出されたテキストの保存、テキスト パターンの分析、または書式変更の適用が含まれる場合があります。