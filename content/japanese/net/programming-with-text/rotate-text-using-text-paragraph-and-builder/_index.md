---
title: PDF ファイルでテキスト段落とビルダーを使用してテキストを回転する
linktitle: PDF ファイルでテキスト段落とビルダーを使用してテキストを回転する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、PDF ファイル内のテキスト段落とビルダーを使用してテキストを回転する方法を学習します。
type: docs
weight: 410
url: /ja/net/programming-with-text/rotate-text-using-text-paragraph-and-builder/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して、PDF ファイル内のテキスト段落とビルダーを使用してテキストを回転する方法を説明します。提供されている C# ソース コードでは、プロセスを段階的に示しています。

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
using Aspose.Pdf.Text.TextBuilder;
```

## ステップ3: PDFドキュメントを作成する

初期化する`Document`新しい PDF ドキュメントを作成するオブジェクト:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

必ず交換してください`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。

## ステップ4: ページを追加する

ドキュメントから特定のページを取得するには、`Pages.Add()`方法：

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## ステップ5: テキスト段落を作成して回転する

作成する`for`異なる回転を持つ複数のテキスト段落を生成するループ:

```csharp
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	paragraph.Rotation = i * 90 + 45;
```

必要に応じて位置と回転の値を調整します。

## ステップ6: テキストフラグメントを作成して構成する

複数作成`TextFragment`オブジェクトにテキストとプロパティを設定します。

```csharp
TextFragment textFragment1 = new TextFragment("Paragraph Text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment1.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment1.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;

TextFragment textFragment2 = new TextFragment("Second line of text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment2.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;

TextFragment textFragment3 = new TextFragment("And some more text...");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment3.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
textFragment3.TextState.Underline = true;
```

必要に応じてテキストやその他のプロパティを調整します。

## ステップ7: 段落にテキストフラグメントを追加する

作成したテキストフラグメントを段落に追加するには、`AppendLine`方法：

```csharp
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
```

## ステップ8: TextBuilderを作成し、段落を追加する

作成する`TextBuilder`オブジェクトを使用して`pdfPage`テキスト段落を PDF ページに追加します。

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendParagraph(paragraph);
}
```

## ステップ9: PDF文書を保存する

変更したPDF文書をファイルに保存するには、`Save`方法：

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```

必ず交換してください`"TextFragmentTests_Rotated4_out.pdf"`希望する出力ファイル名を指定します。

### Aspose.PDF for .NET を使用したテキスト段落とビルダーを使用したテキストの回転のサンプル ソース コード 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントオブジェクトを初期化する
Document pdfDocument = new Document();
//特定のページを取得する
Page pdfPage = (Page)pdfDocument.Pages.Add();
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	//回転を指定
	paragraph.Rotation = i * 90 + 45;
	//テキストフラグメントを作成
	TextFragment textFragment1 = new TextFragment("Paragraph Text");
	//テキストフラグメントを作成
	textFragment1.TextState.FontSize = 12;
	textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment1.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment1.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	//テキストフラグメントを作成
	TextFragment textFragment2 = new TextFragment("Second line of text");
	//テキストプロパティを設定する
	textFragment2.TextState.FontSize = 12;
	textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment2.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment2.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	//テキストフラグメントを作成
	TextFragment textFragment3 = new TextFragment("And some more text...");
	//テキストプロパティを設定する
	textFragment3.TextState.FontSize = 12;
	textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment3.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment3.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	textFragment3.TextState.Underline = true;
	paragraph.AppendLine(textFragment1);
	paragraph.AppendLine(textFragment2);
	paragraph.AppendLine(textFragment3);
	//TextBuilderオブジェクトを作成する
	TextBuilder textBuilder = new TextBuilder(pdfPage);
	//テキストフラグメントをPDFページに追加します
	textBuilder.AppendParagraph(paragraph);
}
//ドキュメントを保存
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```

## 結論

おめでとうございます! Aspose.PDF for .NET を使用して、PDF ドキュメント内のテキスト パラグラフとビルダーを使用してテキストを回転する方法を学習しました。このチュートリアルでは、ドキュメントの作成から変更後のバージョンの保存まで、ステップ バイ ステップで説明しました。これで、このコードを独自の C# プロジェクトに組み込んで、PDF ファイル内のテキストの回転を操作できるようになりました。

### よくある質問

#### Q: 「テキスト段落とビルダーを使用してテキストを回転する」チュートリアルの目的は何ですか?

A: 「テキスト段落とビルダーを使用してテキストを回転する」チュートリアルでは、Aspose.PDF ライブラリ for .NET を使用して PDF ドキュメント内のテキスト段落とビルダーを使用してテキストを回転する方法について包括的なガイドを提供します。このチュートリアルでは、手順を段階的に説明し、段落とカスタム書式を使用してテキストを回転するためのサンプル C# コードが含まれています。

#### Q: このチュートリアルは、以前のテキスト回転チュートリアルとどう違うのですか?

A: これまでのチュートリアルとは異なり、このチュートリアルでは、テキスト段落、ビルダー、回転角度を組み合わせて、より高度なテキスト回転効果を実現します。さまざまな回転角度で複数のテキスト段落を生成し、個々のテキスト フラグメントにカスタム書式を適用する方法を説明します。

#### Q: テキストの回転にテキスト段落とビルダーを使用することの重要性は何ですか?

A: テキスト段落とビルダーを使用すると、テキストの回転と書式設定をより細かく制御できます。テキスト段落はテキストの断片を構造的に整理する方法を提供し、ビルダーは PDF ドキュメント内のテキスト コンテンツの作成と操作を容易にします。

#### Q: テキスト段落ごとに異なる回転角度を適用できますか?

 A: はい、テキスト段落ごとに異なる回転角度を適用できます。`Rotation`の財産`TextParagraph`オブジェクト。これにより、PDF ドキュメント内で多様で動的なテキスト回転効果を作成できます。

#### Q: テキスト段落内のテキストフラグメントの書式設定をカスタマイズするにはどうすればよいですか?

 A: テキストフラグメントの書式設定は、さまざまなプロパティを設定することでカスタマイズできます。`TextState`それぞれの中で`TextFragment`オブジェクト。フォント サイズ、フォント タイプ、前景色と背景色、下線などのプロパティを調整して、目的の視覚効果を実現できます。

#### Q: この方法を使用して、より複雑なテキスト回転効果を作成できますか?

A: もちろんです。回転角度や書式設定オプションを変えて複数のテキスト段落を繰り返し作成することで、複雑で視覚的に魅力的なテキスト回転効果を実現し、PDF ドキュメントの読みやすさと美しさを向上させることができます。

#### Q: テキストの回転を他のテキスト操作技術と組み合わせることは可能ですか?

A: はい、テキストの回転を Aspose.PDF ライブラリが提供する他のテキスト操作テクニックと組み合わせることができます。これには、表、画像、ハイパーリンクなどを追加して、情報量の多い PDF ドキュメントを作成することが含まれます。

#### Q: プロジェクトで Aspose.PDF ライブラリを使用するには特別なライセンスが必要ですか?

A: はい、プロジェクトで Aspose.PDF ライブラリを使用するには、有効な Aspose ライセンスが必要です。Aspose Web サイトからライセンスを取得すると、ライブラリを効果的に統合して使用するために必要な資格情報が提供されます。