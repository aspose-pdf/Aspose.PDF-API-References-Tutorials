---
title: PDFファイル内の正規表現を検索
linktitle: PDFファイル内の正規表現を検索
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、PDF ファイル内の正規表現を使用してテキストを検索および取得する方法を学習します。
type: docs
weight: 440
url: /ja/net/programming-with-text/search-regular-expression/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して、PDF ファイル内の正規表現に一致するテキストを検索および取得する方法について説明します。提供されている C# ソース コードは、プロセスを段階的に示しています。

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
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

必ず交換してください`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを置き換えます。

## ステップ 4: 正規表現で検索する

を作成します`TextFragmentAbsorber`オブジェクトを作成し、パターンに一致するすべてのフレーズを検索する正規表現パターンを設定します。

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // 1999年から2000年のように
```

交換する`"\\d{4}-\\d{4}"`希望の正規表現パターンを使用します。

## ステップ 5: テキスト検索オプションを設定する

を作成します`TextSearchOptions`オブジェクトを作成し、それを`TextSearchOptions`の財産`TextFragmentAbsorber`正規表現の使用を有効にするオブジェクト:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

## ステップ 6: すべてのページを検索する

ドキュメントのすべてのページに対して吸収体を受け入れます。

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## ステップ 7: 抽出されたテキスト断片を取得する

を使用して、抽出されたテキストの断片を取得します。`TextFragments`の財産`TextFragmentAbsorber`物体：

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## ステップ 8: テキストの断片をループする

取得したテキスト フラグメントをループし、そのプロパティにアクセスします。

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

### Aspose.PDF for .NET を使用した検索正規表現のサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開いた文書
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
//TextAbsorber オブジェクトを作成して、正規表現に一致するすべてのフレーズを検索します
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // 1999年から2000年のように
//テキスト検索オプションを設定して正規表現の使用を指定する
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
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

おめでとう！ Aspose.PDF for .NET を使用して、PDF ドキュメント内の正規表現に一致するテキストを検索して取得する方法を学習しました。このチュートリアルでは、ドキュメントの読み込みから抽出されたテキスト フラグメントへのアクセスまで、段階的なガイドを提供しました。このコードを独自の C# プロジェクトに組み込んで、PDF ファイル内で高度なテキスト検索を実行できるようになりました。

### よくある質問

#### Q: 「PDF ファイル内の正規表現を検索」チュートリアルの目的は何ですか?

A: 「PDF ファイル内の正規表現を検索」チュートリアルは、.NET 用の Aspose.PDF ライブラリを使用して、PDF ファイル内の指定された正規表現パターンに一致するテキストを検索および抽出する方法を紹介することを目的としています。このチュートリアルでは、プロセスをデモンストレーションするための包括的なガイダンスとサンプル C# コードが提供されます。

#### Q: このチュートリアルは、PDF ドキュメント内で正規表現を使用したテキストの検索にどのように役立ちますか?

A: このチュートリアルでは、Aspose.PDF ライブラリを使用して、正規表現パターンに基づいて PDF ドキュメント内のテキスト検索を実行するための段階的なアプローチを説明します。プロジェクトの設定、PDF ドキュメントのロード、正規表現パターンの定義、一致するテキスト フラグメントの取得方法について詳しく説明します。

#### Q: このチュートリアルを実行するための前提条件は何ですか?

A: このチュートリアルを開始する前に、C# プログラミング言語の基本を理解しておく必要があります。さらに、Aspose.PDF for .NET ライブラリをインストールする必要があります。 Aspose Web サイトから入手することも、NuGet を使用してプロジェクトに統合することもできます。

#### Q: このチュートリアルに従うようにプロジェクトを設定するにはどうすればよいですか?

A: まず、お好みの統合開発環境 (IDE) で新しい C# プロジェクトを作成し、Aspose.PDF for .NET ライブラリへの参照を追加します。これにより、プロジェクト内でライブラリの機能を活用できるようになります。

#### Q: 正規表現を使用して PDF ドキュメント内のテキストを検索できますか?

 A: はい、このチュートリアルでは、正規表現を使用して PDF ドキュメントからテキストを検索および抽出する方法を説明します。それには、`TextFragmentAbsorber`クラスを指定し、正規表現パターンを指定して、指定されたパターンに一致するフレーズを検索します。

#### Q: テキスト検索の正規表現パターンはどのように定義すればよいですか?

 A: テキスト検索の正規表現パターンを定義するには、`TextFragmentAbsorber`オブジェクトを作成し、`Text`パラメータ。デフォルトのパターンを置き換える`"\\d{4}-\\d{4}"`チュートリアルのコード内で、必要な正規表現パターンを使用します。

#### Q: テキスト検索で正規表現の使用を有効にするにはどうすればよいですか?

 A: 正規表現の使用は、`TextSearchOptions`オブジェクトを作成し、その値を`true`。このオブジェクトを`TextSearchOptions`の財産`TextFragmentAbsorber`実例。これにより、テキスト検索中に正規表現パターンが確実に適用されます。

#### Q: 正規表現パターンに一致するテキストの断片を取得できますか?

 A: もちろんです。 PDF ドキュメントに正規表現検索を適用した後、抽出されたテキストの断片を次のコマンドを使用して取得できます。`TextFragments`の財産`TextFragmentAbsorber`物体。これらのテキスト フラグメントには、指定された正規表現パターンに一致するテキスト セグメントが含まれています。

#### Q: 取得したテキスト断片から何にアクセスできますか?

A: 取得したテキスト フラグメントから、一致したテキストの内容、位置 (X および Y 座標)、フォント情報 (名前、サイズ、色) などのさまざまなプロパティにアクセスできます。チュートリアルのループ内のサンプル コードは、これらのプロパティにアクセスして表示する方法を示しています。

#### Q: 抽出されたテキスト断片に対するアクションをカスタマイズするにはどうすればよいですか?

A: テキスト フラグメントを抽出したら、ループ内のコードをカスタマイズして、各テキスト フラグメントに対して追加のアクションを実行できます。これには、抽出されたテキストの保存、パターンの分析、要件に基づいた書式変更の実装などが含まれます。