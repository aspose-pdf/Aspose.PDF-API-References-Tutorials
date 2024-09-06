---
title: PDF ファイル内のテキスト セグメント ページを検索
linktitle: PDF ファイル内のテキスト セグメント ページを検索
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、PDF ファイルのページ上のテキスト セグメントを検索し、そのプロパティを取得する方法を学習します。
type: docs
weight: 470
url: /ja/net/programming-with-text/search-text-segments-page/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルのページ上の特定のテキスト セグメントを検索し、そのプロパティを取得する方法について説明します。提供されている C# ソース コードは、プロセスを段階的に示しています。

## 前提条件

チュートリアルを進める前に、次のものを用意してください。

- C# プログラミング言語に関する基本的な知識。
- Aspose.PDF for .NET ライブラリがインストールされています。Aspose Web サイトから入手するか、NuGet を使用してプロジェクトにインストールできます。

## ステップ1: プロジェクトを設定する

まず、好みの統合開発環境 (IDE) で新しい C# プロジェクトを作成し、Aspose.PDF for .NET ライブラリへの参照を追加します。

## ステップ2: 必要な名前空間をインポートする

必要な名前空間をインポートするには、C# ファイルの先頭に次の using ディレクティブを追加します。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## ステップ3: ドキュメントディレクトリへのパスを設定する

ドキュメントディレクトリへのパスを設定するには、`dataDir`変数：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。

## ステップ4: PDF文書を読み込む

 PDF文書を読み込むには、`Document`クラス：

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

交換する`"SearchTextSegmentsPage.pdf"` PDF ファイルの実際の名前を入力します。

## ステップ5: TextFragmentAbsorberを作成する

作成する`TextFragmentAbsorber`入力された検索フレーズのすべてのインスタンスを検索するオブジェクト:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

交換する`"text"`希望する検索フレーズを入力します。

## ステップ6: 特定のページのアブソーバーを受け入れる

ドキュメントの目的のページの吸収剤を受け入れます。

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

交換する`2`希望するページ番号（1 から始まるインデックス）を指定します。

## ステップ7: 抽出したテキストセグメントを取得する

抽出したテキストセグメントを取得するには、`TextFragments`の財産`TextFragmentAbsorber`物体：

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## ステップ8: テキストセグメントをループする

取得したテキスト セグメントをループし、そのプロパティにアクセスします。

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

必要に応じて、ループ内のコードを変更して、各テキスト セグメントに対してさらにアクションを実行します。

### Aspose.PDF for .NET を使用したテキスト セグメント検索ページのサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントを開く
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
//入力された検索フレーズのすべてのインスタンスを検索する TextAbsorber オブジェクトを作成します。
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
//すべてのページの吸収剤を受け入れる
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
//抽出されたテキストフラグメントを取得する
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
//フラグメントをループする
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ",
		textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ",
		textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}",
		textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ",
		textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ",
		textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ",
		textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ",
		textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ",
		textSegment.TextState.ForegroundColor);
	}
}
```

## 結論

おめでとうございます! Aspose.PDF for .NET を使用して PDF ドキュメントのページ上の特定のテキスト セグメントを検索する方法を学習しました。このチュートリアルでは、ドキュメントの読み込みから抽出されたテキスト セグメントへのアクセスまで、ステップ バイ ステップで説明しました。これで、このコードを独自の C# プロジェクトに組み込んで、PDF ファイルで高度なテキスト セグメント検索を実行できます。

### よくある質問

#### Q: 「PDF ファイル内のテキスト セグメント ページの検索」チュートリアルの目的は何ですか?

A: 「PDF ファイル内のテキスト セグメント ページの検索」チュートリアルでは、.NET 用の Aspose.PDF ライブラリを使用して PDF ドキュメントの特定のページにある特定のテキスト セグメントを検索する方法についての包括的なガイドを提供します。プロジェクトの設定、PDF ドキュメントの読み込み、テキスト セグメントの検索、C# コードを使用したプロパティの取得のプロセスについて説明します。

#### Q: このチュートリアルは、PDF ドキュメント内の特定のテキスト セグメントの検索にどのように役立ちますか?

A: このチュートリアルでは、PDF ドキュメントの特定のページにある特定のテキスト セグメントを見つけて抽出するプロセスについて説明します。提供されている手順とコード サンプルに従うことで、ユーザーは目的のテキスト セグメントを効果的に検索し、そのプロパティに関する情報を取得できます。

#### Q: このチュートリアルを実行するために必要な前提条件は何ですか?

A: チュートリアルを始める前に、C# プログラミング言語の基礎を理解しておく必要があります。また、Aspose.PDF for .NET ライブラリがインストールされている必要があります。Aspose Web サイトから入手するか、NuGet を使用してプロジェクトにインストールできます。

#### Q: このチュートリアルに従うためにプロジェクトを設定するにはどうすればよいですか?

A: まず、お好みの統合開発環境 (IDE) で新しい C# プロジェクトを作成し、Aspose.PDF for .NET ライブラリへの参照を追加します。これにより、ライブラリの機能を利用して PDF ドキュメントを検索および操作できるようになります。

#### Q: このチュートリアルを使用して、PDF の任意のページ上の特定のテキスト セグメントを検索できますか?

A: はい、このチュートリアルでは、PDF ドキュメントの選択したページで特定のテキスト セグメントを検索する方法について説明します。プロジェクトの設定、PDF の読み込み、Aspose.PDF ライブラリを使用して目的のテキスト セグメントのプロパティを検索および取得する方法をユーザーに案内します。

#### Q: このチュートリアルで検索したいテキストを指定するにはどうすればよいですか?

 A: 検索したいテキストを指定するには、`TextFragmentAbsorber`オブジェクトを検索し、その検索パラメータを`Text`プロパティ。デフォルトを置き換えます`"text"`チュートリアルのコードに、希望する検索フレーズを入力します。

#### Q: 抽出されたテキスト セグメントのプロパティを取得するにはどうすればよいですか?

受け入れた後`TextFragmentAbsorber`PDFの特定のページについては、`TextFragments`アブソーバー オブジェクトのプロパティ。これにより、それぞれ複数のテキスト セグメントを含むテキスト フラグメントのコレクションにアクセスできます。

#### Q: 各テキスト セグメントで追加のアクションを実行するようにコードをカスタマイズできますか?

A: もちろんです。チュートリアルのサンプル コードには、取得したテキスト セグメントを反復処理するループが用意されています。このループ内のコードをカスタマイズして、プロジェクトの要件に基づいて各テキスト セグメントで追加のアクションを実行できます。

#### Q: テキスト セグメントを抽出した後、変更した PDF ドキュメントを保存するにはどうすればよいですか?

A: このチュートリアルでは、主にテキスト セグメントの検索とそのプロパティの取得に焦点を当てています。PDF に変更を加える場合は、他の Aspose.PDF ドキュメントを参照して、特定のニーズに基づいてドキュメントを操作および保存する方法を学習してください。