---
title: PDF ファイル内のテキストセグメントページを検索
linktitle: PDF ファイル内のテキストセグメントページを検索
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、PDF ファイル内のページ上のテキスト セグメントを検索し、そのプロパティを取得する方法を学びます。
type: docs
weight: 470
url: /ja/net/programming-with-text/search-text-segments-page/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルのページ上の特定のテキスト セグメントを検索し、そのプロパティを取得する方法について説明します。提供されている C# ソース コードは、プロセスを段階的に示しています。

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

## ステップ 3: ドキュメント ディレクトリへのパスを設定する

を使用してドキュメント ディレクトリへのパスを設定します。`dataDir`変数：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを置き換えます。

## ステップ 4: PDF ドキュメントをロードする

次のコマンドを使用して PDF ドキュメントをロードします。`Document`クラス：

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

交換する`"SearchTextSegmentsPage.pdf"` PDF ファイルの実際の名前を付けます。

## ステップ 5: TextFragmentAbsorber を作成する

を作成します`TextFragmentAbsorber`オブジェクトを使用して、入力検索フレーズのすべてのインスタンスを検索します。

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

交換する`"text"`希望の検索フレーズを入力してください。

## ステップ 6: 特定のページのアブソーバーを受け入れる

ドキュメントの目的のページの吸収体を受け入れます。

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

交換する`2`目的のページ番号 (1 から始まるインデックス) を付けます。

## ステップ 7: 抽出されたテキストセグメントを取得する

を使用して、抽出されたテキストセグメントを取得します。`TextFragments`の財産`TextFragmentAbsorber`物体：

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## ステップ 8: テキストセグメントをループする

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

### Aspose.PDF for .NET を使用したテキスト セグメントの検索ページのサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開いた文書
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
//TextAbsorber オブジェクトを作成して、入力検索フレーズのすべてのインスタンスを検索します
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
//すべてのページに吸収体を受け入れる
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
//抽出されたテキスト断片を取得する
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

おめでとう！ Aspose.PDF for .NET を使用して PDF ドキュメントのページ上の特定のテキスト セグメントを検索する方法を学習しました。このチュートリアルでは、ドキュメントの読み込みから抽出されたテキスト セグメントへのアクセスまで、段階的なガイドを提供しました。このコードを独自の C# プロジェクトに組み込んで、PDF ファイル内で高度なテキスト セグメント検索を実行できるようになりました。

### よくある質問

#### Q: 「PDF ファイル内のテキストセグメントページを検索」チュートリアルの目的は何ですか?

A: 「PDF ファイル内のテキスト セグメント ページの検索」チュートリアルでは、.NET の Aspose.PDF ライブラリを利用して、PDF ドキュメントの特定のページ上の特定のテキスト セグメントを検索する方法についての包括的なガイドを提供します。プロジェクトのセットアップ、PDF ドキュメントのロード、テキスト セグメントの検索、C# コードを使用したプロパティの取得のプロセスについて説明します。

#### Q: このチュートリアルは、PDF ドキュメント内の特定のテキストセグメントの検索にどのように役立ちますか?

A: このチュートリアルでは、PDF ドキュメントの特定のページにある特定のテキスト セグメントを検索して抽出するプロセスを説明します。提供された手順とコード サンプルに従うことで、ユーザーは目的のテキスト セグメントを効果的に検索し、そのプロパティに関する情報を取得できます。

#### Q: このチュートリアルに従うにはどのような前提条件が必要ですか?

A: チュートリアルを開始する前に、C# プログラミング言語の基本を理解しておく必要があります。さらに、Aspose.PDF for .NET ライブラリをインストールする必要があります。 Aspose Web サイトから入手するか、NuGet を使用してプロジェクトにインストールできます。

#### Q: このチュートリアルに従うようにプロジェクトを設定するにはどうすればよいですか?

A: まず、お好みの統合開発環境 (IDE) で新しい C# プロジェクトを作成し、Aspose.PDF for .NET ライブラリへの参照を追加します。これにより、PDF ドキュメントの検索や操作にライブラリの機能を利用できるようになります。

#### Q: このチュートリアルを使用して、PDF の任意のページにある特定のテキスト セグメントを検索できますか?

A: はい、このチュートリアルでは、PDF ドキュメントの選択したページ上の特定のテキスト セグメントを検索する方法について説明します。このガイドでは、プロジェクトのセットアップ、PDF のロード、Aspose.PDF ライブラリを使用して目的のテキスト セグメントのプロパティを見つけて取得する方法をユーザーに説明します。

#### Q: このチュートリアルで検索するテキストを指定するにはどうすればよいですか?

 A: 検索するテキストを指定するには、`TextFragmentAbsorber`オブジェクトを作成し、`Text`財産。デフォルトを置き換える`"text"`チュートリアルのコードに希望の検索フレーズを入力します。

#### Q: 抽出されたテキストセグメントのプロパティを取得するにはどうすればよいですか?

承諾した上で、`TextFragmentAbsorber` PDF の特定のページについては、抽出されたテキスト セグメントを次のコマンドを使用して取得できます。`TextFragments`吸収体オブジェクトのプロパティ。これにより、それぞれに複数のテキスト セグメントが含まれるテキスト フラグメントのコレクションへのアクセスが提供されます。

#### Q: 各テキストセグメントに対して追加のアクションを実行するようにコードをカスタマイズできますか?

A: もちろんです。チュートリアルのサンプル コードには、取得したテキスト セグメントを反復処理するループが用意されています。このループ内のコードをカスタマイズして、プロジェクトの要件に基づいて各テキスト セグメントに対して追加のアクションを実行できます。

#### Q: テキストセグメントを抽出した後、変更した PDF ドキュメントを保存するにはどうすればよいですか?

A: このチュートリアルは主に、テキスト セグメントの検索とそのプロパティの取得に焦点を当てています。 PDF に変更を加えたい場合は、他の Aspose.PDF ドキュメントを参照して、特定のニーズに基づいてドキュメントを操作および保存する方法を学ぶことができます。