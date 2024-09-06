---
title: 検索してテキストをすべて取得
linktitle: 検索してテキストをすべて取得
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ドキュメントのすべてのページからテキストを検索して取得する方法を学習します。
type: docs
weight: 420
url: /ja/net/programming-with-text/search-and-get-text-all/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントのすべてのページからテキストを検索して取得する方法について説明します。提供されている C# ソース コードでは、プロセスを段階的に示しています。

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

必ず交換してください`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。

## ステップ4: テキストの検索と抽出

作成する`TextFragmentAbsorber`入力された検索フレーズのすべてのインスタンスを検索するオブジェクト:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

交換する`"text"`検索したい実際のテキストを入力します。

## ステップ5: すべてのページを検索する

ドキュメントのすべてのページの吸収剤を受け入れます。

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## ステップ6: 抽出されたテキストフラグメントを取得する

抽出したテキストフラグメントを取得するには、`TextFragments`の財産`TextFragmentAbsorber`物体：

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## ステップ7: テキストフラグメントをループする

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

ループ内のコードを変更して、各テキスト フラグメントに対してさらにアクションを実行できます。

### Aspose.PDF for .NET を使用してテキストをすべて検索して取得するためのサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントを開く
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
//入力された検索フレーズのすべてのインスタンスを検索する TextAbsorber オブジェクトを作成します。
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
//すべてのページの吸収剤を受け入れる
pdfDocument.Pages.Accept(textFragmentAbsorber);
//抽出されたテキストフラグメントを取得する
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

おめでとうございます! Aspose.PDF for .NET を使用して PDF ドキュメントのすべてのページからテキストを検索して取得する方法を学習しました。このチュートリアルでは、ドキュメントの読み込みから抽出されたテキスト フラグメントへのアクセスまで、ステップ バイ ステップで説明しました。これで、このコードを独自の C# プロジェクトに組み込んで、PDF ファイル内のテキスト コンテンツを分析および処理できるようになりました。

### よくある質問

#### Q: 「検索してテキストをすべて取得」チュートリアルの目的は何ですか?

A: 「すべてのテキストを検索して取得」チュートリアルでは、.NET 用の Aspose.PDF ライブラリを使用して PDF ドキュメントのすべてのページからテキストを検索して抽出する方法を説明します。このチュートリアルでは、テキストの検索と取得を実行するための手順を、サンプルの C# コードとともに段階的に説明します。

#### Q: このチュートリアルは、PDF ドキュメントからテキストを抽出するのにどのように役立ちますか?

A: このチュートリアルでは、PDF ドキュメントのすべてのページからテキストを抽出するプロセスについて説明します。Aspose.PDF ライブラリを使用して、特定のテキスト フレーズを検索し、位置、フォント プロパティ、色などの関連情報を取得します。

#### Q: このチュートリアルに従うための前提条件は何ですか?

A: このチュートリアルを始める前に、C# プログラミング言語の基礎を理解している必要があります。また、Aspose.PDF for .NET ライブラリがインストールされている必要があります。Aspose Web サイトから入手するか、NuGet を使用してプロジェクトに統合することができます。

#### Q: このチュートリアルに従うためにプロジェクトを設定するにはどうすればよいですか?

A: まず、お好みの統合開発環境 (IDE) で新しい C# プロジェクトを作成し、Aspose.PDF for .NET ライブラリへの参照を追加します。これにより、プロジェクトでライブラリの機能にアクセスできるようになります。

#### Q: PDF ドキュメント内の特定のテキストを検索するにはどうすればよいですか?

 A:`TextFragmentAbsorber`PDF ドキュメント内で特定の検索フレーズのインスタンスを検索するクラスです。このクラスのインスタンスを作成し、ターゲット テキストを指定すると、そのテキストのすべての出現をキャプチャできます。

#### Q: PDF ドキュメントの全ページでテキストを検索できますか?

 A: はい、チュートリアルではPDF文書の全ページにわたってテキストを検索する方法を紹介しています。`pdfDocument.Pages.Accept(textFragmentAbsorber)`このメソッドは、すべてのページのアブソーバーを受け入れるために使用され、すべてのページで目的のテキストを検索できるようにします。

#### Q: 抽出されたテキストフラグメントにアクセスするにはどうすればよいですか?

 A: テキストを検索した後、抽出されたテキストフラグメントにアクセスできます。`TextFragments`の財産`TextFragmentAbsorber`オブジェクト。このプロパティは、`TextFragment`抽出されたテキストと関連情報を含むオブジェクト。

#### Q: 抽出されたテキスト断片からどのような情報を取得できますか?

A: 抽出されたテキスト フラグメントから、実際のテキスト コンテンツ、位置 (X 座標と Y 座標)、フォント情報 (名前、サイズ、色など) など、さまざまな詳細を取得できます。チュートリアルのサンプル コードでは、これらの詳細にアクセスして印刷する方法を示しています。

#### Q: 抽出されたテキストフラグメントに対してさらにアクションを実行できますか?

A: もちろんです。テキストの断片を抽出したら、ループ内のコードを変更して、各断片に対してカスタム アクションを実行できます。これには、抽出したテキストの保存、テキスト パターンの分析、書式変更の適用などが含まれます。