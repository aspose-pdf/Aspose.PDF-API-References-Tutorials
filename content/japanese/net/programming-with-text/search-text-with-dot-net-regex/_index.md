---
title: Dot Net Regex を使用したテキストの検索
linktitle: Dot Net Regex を使用したテキストの検索
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、PDF ドキュメント内で .NET 正規表現を使用してテキストを検索する方法を学習します。
type: docs
weight: 480
url: /ja/net/programming-with-text/search-text-with-dot-net-regex/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して、PDF ドキュメント内の .NET 正規表現を使用してテキストを検索する方法について説明します。提供されている C# ソース コードは、プロセスを段階的に示しています。

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

## ステップ 4: .NET Regex オブジェクトを作成する

を作成します`.NET Regex`検索パターンを定義するオブジェクト:

```csharp
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
```

交換する`@"[\S]+"`希望の正規表現パターンを使用します。

## ステップ 5: PDF ドキュメントをロードする

次のコマンドを使用して PDF ドキュメントをロードします。`Document`クラス：

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
```

交換する`"SearchTextRegex.pdf"` PDF ファイルの実際の名前を付けます。

## ステップ 6: 特定のページを取得する

ドキュメントの目的のページを取得します。

```csharp
Page page = document.Pages[1];
```

交換する`1`目的のページ番号 (1 から始まるインデックス) を付けます。

## ステップ 7: TextFragmentAbsorber を作成する

を作成します`TextFragmentAbsorber`オブジェクトを使用して、入力正規表現のすべてのインスタンスを検索します。

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
```

## ステップ 8: ページのアブソーバーを受け入れる

ページのアブソーバーを受け入れます。

```csharp
page.Accept(textFragmentAbsorber);
```

## ステップ 9: 抽出されたテキスト断片を取得する

を使用して、抽出されたテキストの断片を取得します。`TextFragments`の財産`TextFragmentAbsorber`物体：

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## ステップ 10: テキストの断片をループする

取得したテキストの断片をループし、必要なアクションを実行します。

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

必要に応じて、ループ内のコードを変更して、各テキスト断片に対してさらにアクションを実行します。

### Aspose.PDF for .NET を使用した Dot Net Regex によるテキスト検索のサンプル ソース コード 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
//すべての単語を検索する Regex オブジェクトを作成する
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
//開いた文書
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
//特定のページを取得する
Page page = document.Pages[1];
//TextAbsorber オブジェクトを作成して、入力正規表現のすべてのインスタンスを検索します
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
//ページのアブソーバーを受け入れる
page.Accept(textFragmentAbsorber);
//抽出されたテキスト断片を取得する
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
//フラグメントをループする
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

## 結論

おめでとう！ Aspose.PDF for .NET を使用して、PDF ドキュメント内で .NET 正規表現を使用してテキストを検索する方法を学習しました。このチュートリアルでは、プロジェクトの設定から抽出されたテキスト フラグメントへのアクセスまで、段階的なガイドを提供しました。このコードを独自の C# プロジェクトに組み込んで、PDF ファイル内で高度なテキスト検索を実行できるようになりました。

### よくある質問

#### Q: 「Dot Net Regex を使用してテキストを検索」チュートリアルの目的は何ですか?

A: 「Dot Net Regex を使用したテキストの検索」チュートリアルは、.NET の Aspose.PDF ライブラリを使用して、.NET 正規表現を使用して PDF ドキュメント内のテキストを検索する方法をユーザーにガイドすることを目的としています。このチュートリアルでは、プロセスをデモンストレーションするための段階的な手順と C# コード サンプルが提供されます。

#### Q: このチュートリアルは、PDF 内の .NET 正規表現を使用したテキストの検索にどのように役立ちますか?

A: このチュートリアルは、Aspose.PDF for .NET の機能を活用して、PDF ドキュメント内の .NET 正規表現を使用してテキストを検索する方法をユーザーが理解するのに役立ちます。提供されている手順とコード例に従うことで、ユーザーは、指定した正規表現に一致するテキスト パターンを効果的に検索できます。

#### Q: このチュートリアルに従うにはどのような前提条件が必要ですか?

A: チュートリアルを開始する前に、C# プログラミング言語の基本を理解しておく必要があります。さらに、Aspose.PDF for .NET ライブラリをインストールする必要があります。 Aspose Web サイトから入手するか、NuGet を使用してプロジェクトにインストールできます。

#### Q: このチュートリアルに従うようにプロジェクトを設定するにはどうすればよいですか?

A: まず、お好みの統合開発環境 (IDE) で新しい C# プロジェクトを作成し、Aspose.PDF for .NET ライブラリへの参照を追加します。これにより、PDF ドキュメントの検索や操作にライブラリの機能を利用できるようになります。

#### Q: このチュートリアルを使用して、.NET 正規表現を使用して特定の種類のテキストを検索できますか?

 A: はい、このチュートリアルでは、PDF ドキュメント内で .NET 正規表現を使用してテキストを検索する方法について説明します。カスタマイズできます`.NET Regex`オブジェクトを使用して、使用する特定の検索パターンを定義します。

#### Q: このチュートリアルで検索する .NET 正規表現パターンを指定するにはどうすればよいですか?

 A: 検索する .NET 正規表現パターンを指定するには、`.NET Regex`オブジェクトを取得し、適切な正規表現構文を使用してそのパターンを設定します。デフォルトを置き換える`@"[\S]+"`チュートリアルのコードに希望の正規表現を追加します。

#### Q: 抽出されたテキスト断片のプロパティを取得するにはどうすればよいですか?

 A: 同意した後、`TextFragmentAbsorber` PDF の特定のページについては、抽出されたテキストの断片を次のコマンドを使用して取得できます。`TextFragments`吸収体オブジェクトのプロパティ。これにより、指定された .NET 正規表現に一致するテキスト フラグメントのコレクションへのアクセスが提供されます。

#### Q: 抽出された各テキスト断片に対して追加のアクションを実行するようにコードをカスタマイズできますか?

A: 確かに。チュートリアルのサンプル コードには、取得したテキスト フラグメントを反復処理するループが含まれています。このループ内のコードをカスタマイズして、プロジェクトの要件に基づいて、抽出された各テキスト断片に対して追加のアクションを実行できます。

#### Q: テキストの断片を抽出した後、変更した PDF ドキュメントを保存するにはどうすればよいですか?

A: このチュートリアルは主に、.NET 正規表現を使用したテキストの検索とテキストのフラグメントの取得に焦点を当てています。 PDF に変更を加えたい場合は、他の Aspose.PDF ドキュメントを参照して、特定のニーズに基づいてドキュメントを操作および保存する方法を学ぶことができます。