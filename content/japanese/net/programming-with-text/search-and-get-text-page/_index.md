---
title: PDF ファイル内のテキスト ページを検索して取得する
linktitle: PDF ファイル内のテキスト ページを検索して取得する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内の特定のページからテキストを検索して取得する方法を学習します。
type: docs
weight: 430
url: /ja/net/programming-with-text/search-and-get-text-page/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイル内の特定のページからテキストを検索して取得する方法について説明します。提供されている C# ソース コードは、プロセスを段階的に示しています。

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

## ステップ3: PDF文書を読み込む

PDFドキュメントディレクトリへのパスを設定し、`Document`クラス：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

必ず交換してください`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。

## ステップ4: ページからテキストを検索して抽出する

作成する`TextFragmentAbsorber`特定のページ上で入力された検索フレーズのすべてのインスタンスを検索するオブジェクト:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

交換する`"Figure"`検索したい実際のテキストを入力します。

## ステップ5: 特定のページを検索する

ドキュメントの特定のページのアブソーバーを受け入れます。

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## ステップ6: 抽出されたテキストフラグメントを取得する

抽出したテキストフラグメントを取得するには、`TextFragments`の財産`TextFragmentAbsorber`物体：

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## ステップ7: テキストの断片とセグメントをループする

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

### Aspose.PDF for .NET を使用したテキスト検索および取得ページのサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントを開く
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
//入力された検索フレーズのすべてのインスタンスを検索する TextAbsorber オブジェクトを作成します。
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
//すべてのページの吸収剤を受け入れる
pdfDocument.Pages.Accept(textFragmentAbsorber);
//抽出されたテキストフラグメントを取得する
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

おめでとうございます！Aspose.PDF for .NETを使用してPDFドキュメントの特定のページからテキストを検索して取得する方法を学習しました。このチュートリアルでは、ドキュメントの読み込みから抽出されたテキストセグメントへのアクセスまで、ステップバイステップのガイドを提供しました。これで、

### よくある質問

#### Q: 「検索してテキストを取得するページ」チュートリアルの目的は何ですか?

A: 「テキスト ページの検索と取得」チュートリアルは、.NET 用の Aspose.PDF ライブラリを使用して PDF ファイル内の特定のページからテキストを検索して取得する方法を説明するために設計されています。このチュートリアルでは、プロセスを示す詳細な手順とサンプル C# コードが提供されています。

#### Q: このチュートリアルは、PDF ドキュメント内の特定のページからテキストを抽出するのにどのように役立ちますか?

A: このチュートリアルでは、Aspose.PDF ライブラリを使用して PDF ドキュメントの特定のページからテキストを抽出するプロセスについて説明します。必要な手順の概要を示し、選択したページで指定されたテキスト フレーズを検索し、関連するテキスト セグメントを取得するための C# コードを提供します。

#### Q: このチュートリアルに従うための前提条件は何ですか?

A: このチュートリアルを始める前に、C# プログラミング言語の基礎を理解している必要があります。また、Aspose.PDF for .NET ライブラリがインストールされている必要があります。Aspose Web サイトから入手するか、NuGet を使用してプロジェクトに統合することができます。

#### Q: このチュートリアルに従うためにプロジェクトを設定するにはどうすればよいですか?

A: まず、お好みの統合開発環境 (IDE) で新しい C# プロジェクトを作成し、Aspose.PDF for .NET ライブラリへの参照を追加します。これにより、プロジェクトでライブラリの機能を利用できるようになります。

#### Q: PDF ドキュメントの特定のページでテキストを検索できますか?

A: はい、このチュートリアルではPDF文書の特定のページでテキストを検索する方法を説明します。`TextFragmentAbsorber`選択したページ上の特定のテキスト フレーズのインスタンスを検索するクラス。

#### Q: 特定のページから抽出されたテキスト セグメントにアクセスするにはどうすればよいですか?

 A: 指定されたページでテキストを検索した後、抽出されたテキストセグメントにアクセスできます。`TextSegments`の財産`TextFragment`オブジェクト。このプロパティは、`TextSegment`抽出されたテキストと関連情報を含むオブジェクト。

#### Q: 抽出されたテキストセグメントからどのような情報を取得できますか?

A: 抽出されたテキスト セグメントから、テキストの内容、位置 (X 座標と Y 座標)、フォント情報 (名前、サイズ、色など) など、さまざまな詳細を取得できます。チュートリアルのサンプル コードでは、各テキスト セグメントのこれらの詳細にアクセスして印刷する方法を示しています。

#### Q: 抽出されたテキスト セグメントに対してカスタム アクションを実行できますか?

A: もちろんです。テキスト セグメントを抽出したら、ループ内のコードをカスタマイズして、各セグメントに対して追加のアクションを実行できます。これには、抽出したテキストの保存、テキスト パターンの分析、書式変更の適用などが含まれます。