---
title: PDF ファイル内のテキスト段落とビルダーを使用してテキストを回転する
linktitle: PDF ファイル内のテキスト段落とビルダーを使用してテキストを回転する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内のテキスト段落とビルダーを使用してテキストを回転する方法を学びます。
type: docs
weight: 410
url: /ja/net/programming-with-text/rotate-text-using-text-paragraph-and-builder/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して、PDF ファイル内のテキスト段落とビルダーを使用してテキストを回転する方法について説明します。提供されている C# ソース コードは、プロセスを段階的に示しています。

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
using Aspose.Pdf.Text.TextBuilder;
```

## ステップ 3: PDF ドキュメントを作成する

を初期化します`Document`新しい PDF ドキュメントを作成するオブジェクト:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

必ず交換してください`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを置き換えます。

## ステップ 4: ページを追加する

を使用してドキュメントから特定のページを取得します。`Pages.Add()`方法：

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## ステップ 5: テキスト段落を作成して回転する

を作成します`for`ループを使用して、回転が異なる複数のテキスト段落を生成します。

```csharp
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	paragraph.Rotation = i * 90 + 45;
```

要件に応じて位置と回転の値を調整します。

## ステップ 6: テキストフラグメントの作成と構成

複数作成する`TextFragment`オブジェクトのテキストとプロパティを設定します。

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

## ステップ 7: テキストの断片を段落に追加する

作成したテキストの断片を段落に追加します。`AppendLine`方法：

```csharp
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
```

## ステップ 8: TextBuilder を作成し、段落を追加する

を作成します`TextBuilder`を使用したオブジェクト`pdfPage`そしてテキスト段落を PDF ページに追加します。

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendParagraph(paragraph);
}
```

## ステップ 9: PDF ドキュメントを保存する

変更した PDF ドキュメントをファイルに保存するには、`Save`方法：

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```

必ず交換してください`"TextFragmentTests_Rotated4_out.pdf"`希望の出力ファイル名を付けます。

### Aspose.PDF for .NET を使用したテキスト段落とビルダーを使用したテキストの回転のサンプル ソース コード 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントオブジェクトの初期化
Document pdfDocument = new Document();
//特定のページを取得する
Page pdfPage = (Page)pdfDocument.Pages.Add();
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	//回転を指定する
	paragraph.Rotation = i * 90 + 45;
	//テキストフラグメントを作成する
	TextFragment textFragment1 = new TextFragment("Paragraph Text");
	//テキストフラグメントを作成する
	textFragment1.TextState.FontSize = 12;
	textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment1.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment1.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	//テキストフラグメントを作成する
	TextFragment textFragment2 = new TextFragment("Second line of text");
	//テキストのプロパティを設定する
	textFragment2.TextState.FontSize = 12;
	textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment2.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment2.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	//テキストフラグメントを作成する
	TextFragment textFragment3 = new TextFragment("And some more text...");
	//テキストのプロパティを設定する
	textFragment3.TextState.FontSize = 12;
	textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment3.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment3.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	textFragment3.TextState.Underline = true;
	paragraph.AppendLine(textFragment1);
	paragraph.AppendLine(textFragment2);
	paragraph.AppendLine(textFragment3);
	//TextBuilder オブジェクトを作成する
	TextBuilder textBuilder = new TextBuilder(pdfPage);
	//テキストフラグメントを PDF ページに追加します
	textBuilder.AppendParagraph(paragraph);
}
//文書の保存
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```

## 結論

おめでとう！ Aspose.PDF for .NET を使用して、PDF ドキュメント内のテキスト段落とビルダーを使用してテキストを回転する方法を学習しました。このチュートリアルでは、ドキュメントの作成から変更されたバージョンの保存までのステップバイステップのガイドを提供しました。このコードを独自の C# プロジェクトに組み込んで、PDF ファイル内のテキストの回転を操作できるようになりました。

### よくある質問

#### Q: 「テキスト段落とビルダーを使用してテキストを回転する」チュートリアルの目的は何ですか?

A: 「テキスト段落とビルダーを使用してテキストを回転する」チュートリアルでは、.NET 用の Aspose.PDF ライブラリを使用して、PDF ドキュメント内のテキスト段落とビルダーを使用してテキストを回転する方法についての包括的なガイドを提供します。このチュートリアルでは、段階的な手順を示し、段落とカスタム書式設定を使用してテキストを回転させるためのサンプル C# コードが含まれています。

#### Q: このチュートリアルは、以前のテキスト回転チュートリアルとどう違うのですか?

A: 以前のチュートリアルとは異なり、このチュートリアルでは、テキスト段落、ビルダー、および回転角度の使用を組み合わせて、より高度なテキスト回転効果を実現します。さまざまな回転角度で複数のテキスト段落を生成し、個々のテキスト断片にカスタム書式設定を適用する方法を示します。

#### Q: テキストの回転にテキスト段落とビルダーを使用する意義は何ですか?

A: テキスト段落とビルダーを使用すると、テキストの回転と書式設定の制御を強化できます。テキスト段落はテキストの断片を整理するための構造化された方法を提供し、ビルダーは PDF ドキュメント内のテキスト コンテンツの作成と操作を容易にします。

#### Q: 各テキスト段落に異なる回転角度を適用できますか?

 A: はい、各テキスト段落に異なる回転角度を適用するには、`Rotation`の財産`TextParagraph`物体。これにより、PDF ドキュメント内で多様で動的なテキスト回転効果を作成できます。

#### Q: テキスト段落内のテキスト断片の書式設定をカスタマイズするにはどうすればよいですか?

 A: テキスト フラグメントのさまざまなプロパティを設定することで、テキスト フラグメントの書式設定をカスタマイズできます。`TextState`それぞれの中で`TextFragment`物体。フォント サイズ、フォント タイプ、前景色と背景色、下線などのプロパティを調整して、目的の視覚効果を実現できます。

#### Q: この方法を使用して、より複雑なテキスト回転効果を作成できますか?

A: もちろんです。異なる回転角度と書式設定オプションを使用して複数のテキスト段落を繰り返し作成することで、複雑で視覚的に魅力的なテキスト回転効果を実現し、PDF ドキュメントの読みやすさと美しさを向上させることができます。

#### Q: テキストの回転と他のテキスト操作テクニックを組み合わせることができますか?

A: はい、テキストの回転と、Aspose.PDF ライブラリが提供する他のテキスト操作テクニックを組み合わせることができます。これには、表、画像、ハイパーリンクなどを追加して、豊富で有益な PDF ドキュメントを作成することが含まれます。

#### Q: プロジェクトで Aspose.PDF ライブラリを使用するには、特別なライセンスが必要ですか?

A: はい、プロジェクトで Aspose.PDF ライブラリを使用するには、有効な Aspose ライセンスが必要です。 Aspose Web サイトからライセンスを取得できます。これにより、ライブラリを効果的に統合して使用するために必要な資格情報が提供されます。