---
title: PDF ファイル内の正規表現を検索する
linktitle: PDF ファイル内の正規表現を検索する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、PDF ファイル内の正規表現を使用してテキストを検索および取得する方法を学習します。
type: docs
weight: 440
url: /ja/net/programming-with-text/search-regular-expression/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイル内の正規表現に一致するテキストを検索および取得する方法について説明します。提供されている C# ソース コードでは、プロセスを段階的に示しています。

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
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

必ず交換してください`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。

## ステップ4: 正規表現で検索する

作成する`TextFragmentAbsorber`オブジェクトを作成し、正規表現パターンを設定して、パターンに一致するすべてのフレーズを検索します。

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // 1999-2000年のように
```

交換する`"\\d{4}-\\d{4}"`希望する正規表現パターンを使用します。

## ステップ5: テキスト検索オプションを設定する

作成する`TextSearchOptions`オブジェクトに設定し、`TextSearchOptions`の財産`TextFragmentAbsorber`正規表現の使用を有効にするオブジェクト:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

## ステップ6: すべてのページを検索する

ドキュメントのすべてのページの吸収剤を受け入れます。

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## ステップ7: 抽出されたテキストフラグメントを取得する

抽出したテキストフラグメントを取得するには、`TextFragments`の財産`TextFragmentAbsorber`物体：

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## ステップ8: テキストフラグメントをループする

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

ループ内のコードを変更して、各テキスト フラグメントに対してさらにアクションを実行できます。

### Aspose.PDF for .NET を使用した正規表現検索のサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントを開く
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
//正規表現に一致するすべてのフレーズを見つけるためにTextAbsorberオブジェクトを作成します。
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // 1999-2000年のように
//正規表現の使用を指定するためのテキスト検索オプションを設定します
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
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

おめでとうございます! Aspose.PDF for .NET を使用して、PDF ドキュメント内の正規表現に一致するテキストを検索および取得する方法を学習しました。このチュートリアルでは、ドキュメントの読み込みから抽出されたテキスト フラグメントへのアクセスまで、ステップ バイ ステップで説明しました。これで、このコードを独自の C# プロジェクトに組み込んで、PDF ファイル内で高度なテキスト検索を実行できます。

### よくある質問

#### Q: 「PDF ファイル内の正規表現の検索」チュートリアルの目的は何ですか?

A: 「PDF ファイル内の正規表現の検索」チュートリアルの目的は、.NET 用の Aspose.PDF ライブラリを使用して、PDF ファイル内で指定された正規表現パターンに一致するテキストを検索および抽出する方法を紹介することです。このチュートリアルでは、プロセスを示す包括的なガイダンスとサンプル C# コードが提供されます。

#### Q: このチュートリアルは、PDF ドキュメント内で正規表現を使用してテキストを検索するのにどのように役立ちますか?

A: このチュートリアルでは、Aspose.PDF ライブラリを使用して、正規表現パターンに基づいて PDF ドキュメント内でテキスト検索を実行する方法を段階的に説明します。プロジェクトの設定方法、PDF ドキュメントの読み込み方法、正規表現パターンの定義方法、一致するテキスト フラグメントの取得方法について詳しく説明します。

#### Q: このチュートリアルに従うための前提条件は何ですか?

A: このチュートリアルを始める前に、C# プログラミング言語の基礎を理解している必要があります。また、Aspose.PDF for .NET ライブラリがインストールされている必要があります。Aspose Web サイトから入手するか、NuGet を使用してプロジェクトに統合することができます。

#### Q: このチュートリアルに従うためにプロジェクトを設定するにはどうすればよいですか?

A: まず、お好みの統合開発環境 (IDE) で新しい C# プロジェクトを作成し、Aspose.PDF for .NET ライブラリへの参照を追加します。これにより、プロジェクト内でライブラリの機能を活用できるようになります。

#### Q: 正規表現を使用して PDF ドキュメント内のテキストを検索できますか?

 A: はい、このチュートリアルでは、正規表現を使用してPDF文書からテキストを検索および抽出する方法を説明します。`TextFragmentAbsorber`クラスと正規表現パターンを指定して、指定されたパターンに一致するフレーズを検索します。

#### Q: テキスト検索の正規表現パターンを定義するにはどうすればよいですか?

 A: テキスト検索の正規表現パターンを定義するには、`TextFragmentAbsorber`オブジェクトを作成し、そのパターンを`Text`パラメータ。デフォルトのパターンを置き換えます`"\\d{4}-\\d{4}"`チュートリアルのコードに、希望する正規表現パターンを入力します。

#### Q: テキスト検索で正規表現を使用できるようにするにはどうすればいいですか?

 A: 正規表現の使用は、`TextSearchOptions`オブジェクトとその値を設定する`true`このオブジェクトを`TextSearchOptions`の財産`TextFragmentAbsorber`インスタンス。これにより、テキスト検索中に正規表現パターンが適用されるようになります。

#### Q: 正規表現パターンに一致するテキストフラグメントを取得できますか?

 A: もちろんです。PDF文書に正規表現検索を適用した後、抽出されたテキストフラグメントを`TextFragments`の財産`TextFragmentAbsorber`オブジェクト。これらのテキスト フラグメントには、指定された正規表現パターンに一致するテキスト セグメントが含まれます。

#### Q: 取得したテキストフラグメントから何にアクセスできますか?

A: 取得したテキスト フラグメントから、一致したテキスト コンテンツ、位置 (X 座標と Y 座標)、フォント情報 (名前、サイズ、色) などのさまざまなプロパティにアクセスできます。チュートリアルのループ内のサンプル コードでは、これらのプロパティにアクセスして表示する方法を示しています。

#### Q: 抽出されたテキストフラグメントに対するアクションをカスタマイズするにはどうすればよいですか?

A: テキスト フラグメントを抽出したら、ループ内のコードをカスタマイズして、各テキスト フラグメントに対して追加のアクションを実行できます。これには、抽出したテキストの保存、パターンの分析、要件に基づいた書式設定の変更の実装などが含まれます。