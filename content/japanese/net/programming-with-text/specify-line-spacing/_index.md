---
title: PDF ファイルの行間を指定する
linktitle: PDF ファイルの行間を指定する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルの行間隔を指定する方法を学びます。
type: docs
weight: 510
url: /ja/net/programming-with-text/specify-line-spacing/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルの行間を指定する方法を説明します。提供されている C# ソース コードは、プロセスを段階的に示しています。

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
using System.IO;
```

## ステップ 3: ドキュメント ディレクトリへのパスを設定する

を使用してドキュメント ディレクトリへのパスを設定します。`dataDir`変数：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを置き換えます。

## ステップ 4: 入力 PDF ファイルをロードする

を使用して入力 PDF ファイルをロードします。`Document`クラス：

```csharp
Document doc = new Document();
```

## ステップ 5: TextFormattingOptions を作成する

を作成します`TextFormattingOptions`オブジェクトを選択し、行間隔モードを に設定します。`FullSize`:

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

## ステップ 6: TextFragment を作成する

を作成します`TextFragment`オブジェクトを指定し、テキストの内容を指定します。

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

## ステップ 7: フォント ファイルをロードする (オプション)

テキストに特定のフォントを使用したい場合は、TrueType フォント ファイルを`FileStream`物体：

```csharp
string fontFile = dataDir + "HPSimplified.TTF";
using (FileStream fontStream = File.OpenRead(fontFile))
{
    textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
}
```

交換する`"HPSimplified.TTF"`実際のフォントファイル名を使用します。

## ステップ 8: テキストの位置と行間隔を指定する

テキストフラグメントの位置を設定し、`TextFormattingOptions`に`TextState.FormattingOptions`財産：

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

## ステップ 9: ドキュメントにテキストを追加する

テキストフラグメントをドキュメントに追加するには、テキストフラグメントを`TextBuilder`またはページの直接`Paragraphs`コレクション：

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

## ステップ 10: 結果の PDF ドキュメントを保存する

変更した PDF ドキュメントを保存します。

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

必ず交換してください`"SpecifyLineSpacing_out.pdf"`希望の出力ファイル名を付けます。

### Aspose.PDF for .NET を使用した行間隔の指定のサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
//入力PDFファイルを読み込みます
Document doc = new Document();
//LineSpacingMode.FullSize を使用して TextFormattingOptions を作成する
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
//文書の最初のページのテキストビルダーオブジェクトを作成する
//TextBuilder textBuilder = new TextBuilder(doc.Pages[1]);
//サンプル文字列を使用してテキストフラグメントを作成する
TextFragment textFragment = new TextFragment("Hello world");
if (fontFile != "")
{
	//TrueType フォントをストリーム オブジェクトにロードします。
	using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
	{
		//文字列のフォント名を設定します
		textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
		//テキストフラグメントの位置を指定します
		textFragment.Position = new Position(100, 600);
		//現在のフラグメントの TextFormattingOptions を事前定義済み (LineSpacingMode.FullSize を指す) に設定します。
		textFragment.TextState.FormattingOptions = formattingOptions;
		// PDF ファイルの上に配置できるようにテキストを TextBuilder に追加します。
		//textBuilder.AppendText(textFragment);
		var page = doc.Pages.Add();
		page.Paragraphs.Add(textFragment);
	}
	dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
	//結果の PDF ドキュメントを保存する
	doc.Save(dataDir);
}
```

## 結論

おめでとう！ Aspose.PDF for .NET を使用して PDF ドキュメントの行間隔を指定する方法を学習しました。このチュートリアルでは、プロジェクトのセットアップから変更したドキュメントの保存までのステップバイステップのガイドを提供しました。このコードを独自の C# プロジェクトに組み込んで、PDF ファイル内のテキストの行間隔をカスタマイズできるようになりました。

### よくある質問

#### Q: 「PDF ファイルの行間隔を指定する」チュートリアルの目的は何ですか?

A: 「PDF ファイルの行間隔を指定する」チュートリアルは、.NET 用の Aspose.PDF ライブラリを使用して PDF ドキュメント内のテキストの行間隔をカスタマイズする方法をユーザーにガイドすることを目的としています。このチュートリアルでは、プロセスをデモンストレーションするための段階的な手順と C# コード サンプルが提供されます。

#### Q: このチュートリアルは、PDF ドキュメント内の行間隔を指定する際にどのように役立ちますか?

A: このチュートリアルは、Aspose.PDF for .NET の機能を利用して PDF ドキュメント内のテキストの行間隔を指定する方法をユーザーが理解するのに役立ちます。提供されている手順とコード例に従うことで、ユーザーは好みに応じて行間隔を調整できます。

#### Q: このチュートリアルに従うにはどのような前提条件が必要ですか?

A: チュートリアルを開始する前に、C# プログラミング言語の基本を理解しておく必要があります。さらに、Aspose.PDF for .NET ライブラリをインストールする必要があります。 Aspose Web サイトから入手するか、NuGet を使用してプロジェクトにインストールできます。

#### Q: このチュートリアルに従うようにプロジェクトを設定するにはどうすればよいですか?

A: まず、お好みの統合開発環境 (IDE) で新しい C# プロジェクトを作成し、Aspose.PDF for .NET ライブラリへの参照を追加します。これにより、PDF ドキュメントの操作や行間隔のカスタマイズにライブラリの機能を利用できるようになります。

#### Q: このチュートリアルを使用して、あらゆる種類のテキストの行間隔を指定できますか?

A: はい、このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内のテキスト コンテンツの行間隔を指定する方法について説明します。提供されているコード サンプルを使用して、必要に応じてテキストの行間隔を調整できます。

#### Q: チュートリアルで行間モードを指定するにはどうすればよいですか?

 A: チュートリアルでは、`TextFormattingOptions`オブジェクトを設定し、`LineSpacing`財産を`TextFormattingOptions.LineSpacingMode.FullSize`。このモードでは、テキスト コンテンツの完全な行間隔を指定します。

#### Q: テキストに特定のフォントをロードするにはどうすればよいですか?

 A: テキスト コンテンツに特定のフォントを使用したい場合、チュートリアルでは、TrueType フォント ファイルを`FileStream`オブジェクトを作成し、それをフォントとして設定します。`TextFragment`。これにより、テキストのフォントと行間隔をカスタマイズできます。

#### Q: PDF ドキュメント内のテキストの位置をカスタマイズするにはどうすればよいですか?

 A: テキストの位置をカスタマイズするには、`TextFragment`オブジェクトを設定し、`Position`プロパティを目的の座標 (X および Y) に設定します。これにより、PDF ドキュメント内のテキストを配置する場所を制御できます。

#### Q: これらの行間隔の変更を既存の PDF ドキュメントに適用できますか?

 A: はい、既存の PDF ドキュメント内のテキストの行間隔を変更できます。チュートリアルでは、`TextFragment`指定された行間隔と位置でページに追加します。`Paragraphs`コレクション。