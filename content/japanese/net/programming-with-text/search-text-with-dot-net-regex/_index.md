---
title: ドットネット正規表現でテキストを検索する
linktitle: ドットネット正規表現でテキストを検索する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、PDF ドキュメント内で .NET 正規表現を使用してテキストを検索する方法を学習します。
type: docs
weight: 480
url: /ja/net/programming-with-text/search-text-with-dot-net-regex/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内の .NET 正規表現でテキストを検索する方法について説明します。提供されている C# ソース コードでは、プロセスを段階的に示しています。

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

## ステップ4: .NET Regexオブジェクトを作成する

作成する`.NET Regex`検索パターンを定義するオブジェクト:

```csharp
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
```

交換する`@"[\S]+"`希望する正規表現パターンを使用します。

## ステップ5: PDF文書を読み込む

 PDF文書を読み込むには、`Document`クラス：

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
```

交換する`"SearchTextRegex.pdf"` PDF ファイルの実際の名前を入力します。

## ステップ6: 特定のページを取得する

ドキュメントの目的のページを取得します。

```csharp
Page page = document.Pages[1];
```

交換する`1`希望するページ番号（1 から始まるインデックス）を指定します。

## ステップ7: TextFragmentAbsorberを作成する

作成する`TextFragmentAbsorber`入力正規表現のすべてのインスタンスを検索するオブジェクト:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
```

## ステップ8: ページの吸収剤を受け入れる

ページの吸収剤を受け入れます:

```csharp
page.Accept(textFragmentAbsorber);
```

## ステップ9: 抽出したテキストフラグメントを取得する

抽出したテキストフラグメントを取得するには、`TextFragments`の財産`TextFragmentAbsorber`物体：

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## ステップ10: テキストフラグメントをループする

取得したテキスト フラグメントをループし、必要なアクションを実行します。

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

必要に応じて、ループ内のコードを変更して、各テキスト フラグメントに対してさらにアクションを実行します。

### Aspose.PDF for .NET を使用して Dot Net Regex でテキストを検索するためのサンプル ソース コード 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
//すべての単語を検索するための正規表現オブジェクトを作成する
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
//ドキュメントを開く
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
//特定のページを取得する
Page page = document.Pages[1];
//入力正規表現のすべてのインスタンスを見つけるために TextAbsorber オブジェクトを作成します。
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
//ページの吸収剤を受け入れる
page.Accept(textFragmentAbsorber);
//抽出されたテキストフラグメントを取得する
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
//フラグメントをループする
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

## 結論

おめでとうございます! Aspose.PDF for .NET を使用して、PDF ドキュメント内で .NET 正規表現を使用してテキストを検索する方法を学習しました。このチュートリアルでは、プロジェクトのセットアップから抽出されたテキスト フラグメントへのアクセスまで、ステップ バイ ステップのガイドを提供しました。これで、このコードを独自の C# プロジェクトに組み込んで、PDF ファイルで高度なテキスト検索を実行できます。

### よくある質問

#### Q: 「ドットネット正規表現によるテキスト検索」チュートリアルの目的は何ですか?

A: 「ドット ネット正規表現を使用したテキストの検索」チュートリアルは、.NET 用の Aspose.PDF ライブラリを使用して、.NET 正規表現で PDF ドキュメント内のテキストを検索する方法をユーザーに説明することを目的としています。このチュートリアルでは、プロセスを示す手順と C# コード サンプルが段階的に提供されます。

#### Q: このチュートリアルは、PDF で .NET 正規表現を使用してテキストを検索するのにどのように役立ちますか?

A: このチュートリアルは、Aspose.PDF for .NET の機能を活用して、PDF ドキュメント内で .NET 正規表現を使用してテキストを検索する方法をユーザーが理解するのに役立ちます。提供されている手順とコード例に従うことで、ユーザーは指定した正規表現に一致するテキスト パターンを効果的に検索できます。

#### Q: このチュートリアルを実行するために必要な前提条件は何ですか?

A: チュートリアルを始める前に、C# プログラミング言語の基礎を理解しておく必要があります。また、Aspose.PDF for .NET ライブラリがインストールされている必要があります。Aspose Web サイトから入手するか、NuGet を使用してプロジェクトにインストールできます。

#### Q: このチュートリアルに従うためにプロジェクトを設定するにはどうすればよいですか?

A: まず、お好みの統合開発環境 (IDE) で新しい C# プロジェクトを作成し、Aspose.PDF for .NET ライブラリへの参照を追加します。これにより、ライブラリの機能を利用して PDF ドキュメントを検索および操作できるようになります。

#### Q: このチュートリアルを使用して、.NET 正規表現を使用して特定の種類のテキストを検索できますか?

 A: はい、このチュートリアルでは、PDF文書内で.NET正規表現を使用してテキストを検索する方法について説明します。`.NET Regex`使用したい特定の検索パターンを定義するオブジェクト。

#### Q: このチュートリアルで検索する .NET 正規表現パターンを指定するにはどうすればよいですか?

 A: 検索したい.NET正規表現パターンを指定するには、`.NET Regex`オブジェクトを作成し、適切な正規表現構文を使用してパターンを設定します。デフォルトの`@"[\S]+"`チュートリアルのコードに、希望する正規表現を入力します。

#### Q: 抽出されたテキストフラグメントのプロパティを取得するにはどうすればよいですか?

 A: 同意した後`TextFragmentAbsorber`PDFの特定のページについては、`TextFragments`アブソーバー オブジェクトのプロパティ。これにより、指定された .NET 正規表現に一致するテキスト フラグメントのコレクションにアクセスできます。

#### Q: 抽出されたテキストフラグメントごとに追加のアクションを実行するようにコードをカスタマイズできますか?

A: もちろんです。チュートリアルのサンプル コードには、取得したテキスト フラグメントを反復処理するループが含まれています。このループ内のコードをカスタマイズして、プロジェクトの要件に基づいて、抽出された各テキスト フラグメントに対して追加のアクションを実行できます。

#### Q: テキストフラグメントを抽出した後、変更した PDF ドキュメントを保存するにはどうすればよいですか?

A: このチュートリアルでは、主に .NET 正規表現を使用したテキストの検索とテキスト フラグメントの取得に焦点を当てています。PDF に変更を加える場合は、他の Aspose.PDF ドキュメントを参照して、特定のニーズに基づいてドキュメントを操作および保存する方法を学習できます。