---
title: PDF ファイル内のテキストフラグメントを使用してテキストを回転する
linktitle: PDF ファイル内のテキストフラグメントを使用してテキストを回転する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、PDF ファイル内のテキスト フラグメントを使用してテキストを回転する方法を学習します。
type: docs
weight: 390
url: /ja/net/programming-with-text/rotate-text-using-text-fragment/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイル内のテキスト フラグメントを使用してテキストを回転する方法を説明します。提供されている C# ソース コードでは、プロセスを段階的に示しています。

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

## ステップ5: テキストフラグメントを作成する

複数作成`TextFragment`オブジェクトを作成し、テキストとプロパティを設定し、ページ上の位置を指定します。

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
```

必要に応じてテキスト、位置、その他のプロパティを調整します。

## ステップ6: TextBuilderを作成し、テキストフラグメントを追加する

作成する`TextBuilder`オブジェクトを使用して`pdfPage`テキストフラグメントを PDF ページに追加します。

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

## ステップ7: PDF文書を保存する

変更したPDF文書をファイルに保存するには、`Save`方法：

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

必ず交換してください`"TextFragmentTests_Rotated1_out.pdf"`希望する出力ファイル名を指定します。

### Aspose.PDF for .NET を使用したテキスト フラグメントによるテキストの回転のサンプル ソース コード 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントオブジェクトを初期化する
Document pdfDocument = new Document();
//特定のページを取得する
Page pdfPage = (Page)pdfDocument.Pages.Add();
//テキストフラグメントを作成
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
//テキストプロパティを設定する
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
//回転したテキストフラグメントを作成する
TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
//テキストプロパティを設定する
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;
//回転したテキストフラグメントを作成する
TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
//テキストプロパティを設定する
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
//TextBuilder オブジェクトを作成する
TextBuilder textBuilder = new TextBuilder(pdfPage);
//テキストフラグメントをPDFページに追加します
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
//ドキュメントを保存
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

## 結論

おめでとうございます! Aspose.PDF for .NET を使用して PDF ドキュメント内のテキスト フラグメントを使用してテキストを回転する方法を学習しました。このチュートリアルでは、ドキュメントの作成から変更後のバージョンの保存まで、ステップ バイ ステップでガイドしました。これで、このコードを独自の C# プロジェクトに組み込んで、PDF ファイル内のテキストの回転を操作できるようになりました。

### よくある質問

#### Q: 「テキストフラグメントを使用してテキストを回転する」チュートリアルの目的は何ですか?

A: 「テキスト フラグメントを使用してテキストを回転する」チュートリアルは、Aspose.PDF ライブラリ for .NET を使用して PDF ドキュメント内のテキスト フラグメントを使用してテキストを回転するプロセスを説明することを目的としています。このチュートリアルでは、この機能を実現するための手順とサンプル コードが提供されます。

#### Q: 「テキストフラグメントを使用してテキストを回転する」とはどういう意味ですか?

A: テキスト フラグメントを使用したテキストの回転とは、Aspose.PDF ライブラリを使用して PDF ドキュメント内の個々のテキスト フラグメントに回転を適用する機能を指します。この手法を使用すると、PDF コンテンツ内のさまざまな角度や位置でテキストの方向を制御できます。

#### Q: PDF ドキュメント内のテキスト フラグメントを回転する必要があるのはなぜですか?

A: PDF ドキュメント内のテキスト フラグメントを回転すると、特定のコンテンツを強調したり、芸術的なデザインを作成したり、レイアウトや読みやすさを改善したりするなど、さまざまな目的に役立ちます。

#### Q: チュートリアル用のプロジェクトを設定するにはどうすればよいですか?

A: プロジェクトを設定するには:

1. 好みの統合開発環境 (IDE) で新しい C# プロジェクトを作成します。
2. Aspose.PDF for .NET ライブラリへの参照を追加します。
3. 必要な using ディレクティブを C# ファイルに追加します。

#### Q: 新しい PDF ドキュメントを作成するにはどうすればよいですか?

 A: 新しいPDF文書を作成するには、`Document`Aspose.PDF ライブラリのオブジェクト。このオブジェクトを使用して、PDF にページとコンテンツを追加できます。

#### Q: テキスト フラグメントを使用してテキスト フラグメントを回転するにはどうすればよいですか?

A: テキストフラグメントを使用してテキストフラグメントを回転するには:

1. 作成する`TextFragment`オブジェクト。
2. テキスト フラグメントのテキストとプロパティを設定します。
3. ページ上のテキストフラグメントの位置を指定します。
4. 回転角度を設定するには、`TextState.Rotation`テキストフラグメントのプロパティ。
5. 作成する`TextBuilder`オブジェクトを作成し、テキスト フラグメントを PDF ページに追加します。

#### Q: 異なるテキストフラグメントに異なる回転角度を適用できますか?

 A: はい、異なる回転角度を異なるオブジェクトに適用できます。`TextFragment`オブジェクト。各テキストフラグメントには、`TextState.Rotation`財産。

#### Q: 回転したテキストフラグメントを含む PDF ドキュメントを保存するにはどうすればよいですか?

 A: 回転したテキストフラグメントを含むPDF文書を保存するには、`Save`方法の`Document`オブジェクトを選択し、必要な出力ファイルのパスと名前を指定します。