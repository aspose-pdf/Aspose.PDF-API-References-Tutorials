---
title: PDFファイル内の行間隔を指定する
linktitle: PDFファイル内の行間隔を指定する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内の行間隔を指定する方法を学習します。
type: docs
weight: 510
url: /ja/net/programming-with-text/specify-line-spacing/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイル内の行間隔を指定する方法について説明します。提供されている C# ソース コードは、プロセスを段階的に示しています。

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
using System.IO;
```

## ステップ3: ドキュメントディレクトリへのパスを設定する

ドキュメントディレクトリへのパスを設定するには、`dataDir`変数：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。

## ステップ4: 入力PDFファイルを読み込む

入力PDFファイルを読み込みます。`Document`クラス：

```csharp
Document doc = new Document();
```

## ステップ5: TextFormattingOptionsを作成する

作成する`TextFormattingOptions`オブジェクトを選択し、行間隔モードを`FullSize`:

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

## ステップ6: TextFragmentを作成する

作成する`TextFragment`オブジェクトを作成し、テキスト コンテンツを指定します。

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

## ステップ7: フォントファイルを読み込む（オプション）

テキストに特定のフォントを使用する場合は、TrueTypeフォントファイルを`FileStream`物体：

```csharp
string fontFile = dataDir + "HPSimplified.TTF";
using (FileStream fontStream = File.OpenRead(fontFile))
{
    textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
}
```

交換する`"HPSimplified.TTF"`実際のフォントファイル名を使用します。

## ステップ8: テキストの位置と行間隔を指定する

テキストフラグメントの位置を設定し、`TextFormattingOptions`に`TextState.FormattingOptions`財産：

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

## ステップ9: 文書にテキストを追加する

テキストフラグメントをドキュメントに追加するには、`TextBuilder`または直接ページの`Paragraphs`コレクション：

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

## ステップ10: 結果のPDF文書を保存する

変更した PDF ドキュメントを保存します。

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

必ず交換してください`"SpecifyLineSpacing_out.pdf"`希望する出力ファイル名を指定します。

### Aspose.PDF for .NET を使用して行間隔を指定するためのサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
//入力PDFファイルを読み込む
Document doc = new Document();
//LineSpacingMode.FullSize で TextFormattingOptions を作成する
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
//ドキュメントの最初のページのテキスト ビルダー オブジェクトを作成します。
//テキストビルダー textBuilder = new TextBuilder(doc.Pages[1]);
//サンプル文字列でテキストフラグメントを作成する
TextFragment textFragment = new TextFragment("Hello world");
if (fontFile != "")
{
	//TrueTypeフォントをストリームオブジェクトにロードする
	using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
	{
		//テキスト文字列のフォント名を設定する
		textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
		//テキストフラグメントの位置を指定する
		textFragment.Position = new Position(100, 600);
		//現在のフラグメントの TextFormattingOptions を事前定義済み（LineSpacingMode.FullSize を指す）に設定します。
		textFragment.TextState.FormattingOptions = formattingOptions;
		// TextBuilderにテキストを追加して、PDFファイルの上に配置できるようにします。
		//textBuilder.AppendText(テキストフラグメント);
		var page = doc.Pages.Add();
		page.Paragraphs.Add(textFragment);
	}
	dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
	//結果のPDF文書を保存する
	doc.Save(dataDir);
}
```

## 結論

おめでとうございます! Aspose.PDF for .NET を使用して PDF ドキュメントの行間隔を指定する方法を学習しました。このチュートリアルでは、プロジェクトのセットアップから変更したドキュメントの保存まで、ステップ バイ ステップで説明しました。これで、このコードを独自の C# プロジェクトに組み込んで、PDF ファイル内のテキストの行間隔をカスタマイズできるようになりました。

### よくある質問

#### Q: 「PDF ファイルで行間隔を指定する」チュートリアルの目的は何ですか?

A: 「PDF ファイルで行間隔を指定する」チュートリアルは、Aspose.PDF ライブラリ for .NET を使用して PDF ドキュメント内のテキストの行間隔をカスタマイズする方法をユーザーに説明することを目的としています。このチュートリアルでは、プロセスを示す手順と C# コード サンプルが提供されます。

#### Q: このチュートリアルは、PDF ドキュメント内の行間隔を指定するのにどのように役立ちますか?

A: このチュートリアルは、Aspose.PDF for .NET の機能を利用して PDF ドキュメント内のテキストの行間隔を指定する方法をユーザーが理解するのに役立ちます。提供されている手順とコード例に従うことで、ユーザーは好みに応じて行間隔を調整できます。

#### Q: このチュートリアルを実行するために必要な前提条件は何ですか?

A: チュートリアルを始める前に、C# プログラミング言語の基礎を理解しておく必要があります。また、Aspose.PDF for .NET ライブラリがインストールされている必要があります。Aspose Web サイトから入手するか、NuGet を使用してプロジェクトにインストールできます。

#### Q: このチュートリアルに従うためにプロジェクトを設定するにはどうすればよいですか?

A: まず、お好みの統合開発環境 (IDE) で新しい C# プロジェクトを作成し、Aspose.PDF for .NET ライブラリへの参照を追加します。これにより、ライブラリの機能を活用して PDF ドキュメントを操作したり、行間隔をカスタマイズしたりできるようになります。

#### Q: このチュートリアルを使用して、任意のタイプのテキストの行間隔を指定できますか?

A: はい、このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内の任意のテキスト コンテンツの行間隔を指定する方法について説明します。提供されているコード サンプルを使用して、必要に応じてテキストの行間隔を調整できます。

#### Q: チュートリアルで行間隔モードを指定するにはどうすればよいですか?

 A: チュートリアルでは、`TextFormattingOptions`オブジェクトを設定し、`LineSpacing`財産に`TextFormattingOptions.LineSpacingMode.FullSize`このモードでは、テキスト コンテンツの行間隔が完全に指定されます。

#### Q: テキストに特定のフォントを読み込むにはどうすればいいですか?

 A: テキストコンテンツに特定のフォントを使用する場合は、チュートリアルでTrueTypeフォントファイルを読み込む方法を説明します。`FileStream`オブジェクトを選択し、それを`TextFragment`これにより、テキストのフォントと行間隔をカスタマイズできます。

#### Q: PDF ドキュメント内のテキストの位置をカスタマイズするにはどうすればよいですか?

 A: テキストの位置をカスタマイズするには、`TextFragment`オブジェクトを設定し、`Position`プロパティを目的の座標 (X と Y) に設定します。これにより、PDF ドキュメント内でテキストを配置する場所を制御できます。

#### Q: これらの行間隔の変更を既存の PDF ドキュメントに適用できますか?

 A: はい、既存のPDF文書内のテキストの行間を変更することができます。チュートリアルでは、`TextFragment`指定された行間と位置で配置し、ページの`Paragraphs`コレクション。