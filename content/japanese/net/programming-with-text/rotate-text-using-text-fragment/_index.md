---
title: PDF ファイル内のテキスト断片を使用してテキストを回転する
linktitle: PDF ファイル内のテキスト断片を使用してテキストを回転する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、PDF ファイル内のテキスト フラグメントを使用してテキストを回転する方法を学びます。
type: docs
weight: 390
url: /ja/net/programming-with-text/rotate-text-using-text-fragment/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して、PDF ファイル内のテキスト フラグメントを使用してテキストを回転する方法について説明します。提供されている C# ソース コードは、プロセスを段階的に示しています。

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

## ステップ 5: テキストフラグメントを作成する

複数作成する`TextFragment`オブジェクトを作成し、そのテキストとプロパティを設定し、ページ上の位置を指定します。

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

必要に応じて、テキスト、位置、その他のプロパティを調整します。

## ステップ 6: TextBuilder を作成し、テキスト フラグメントを追加する

を作成します`TextBuilder`を使用したオブジェクト`pdfPage`そしてテキストの断片を PDF ページに追加します。

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

## ステップ 7: PDF ドキュメントを保存する

変更した PDF ドキュメントをファイルに保存するには、`Save`方法：

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

必ず交換してください`"TextFragmentTests_Rotated1_out.pdf"`希望の出力ファイル名を付けます。

### Aspose.PDF for .NET を使用したテキスト フラグメントを使用したテキストの回転のサンプル ソース コード 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントオブジェクトの初期化
Document pdfDocument = new Document();
//特定のページを取得する
Page pdfPage = (Page)pdfDocument.Pages.Add();
//テキストフラグメントを作成する
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
//テキストのプロパティを設定する
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
//回転したテキストフラグメントを作成する
TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
//テキストのプロパティを設定する
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;
//回転したテキストフラグメントを作成する
TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
//テキストのプロパティを設定する
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
//TextBuilder オブジェクトを作成する
TextBuilder textBuilder = new TextBuilder(pdfPage);
//テキストフラグメントを PDF ページに追加します
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
//文書の保存
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

## 結論

おめでとう！ Aspose.PDF for .NET を使用して、PDF ドキュメント内のテキスト フラグメントを使用してテキストを回転する方法を学習しました。このチュートリアルでは、ドキュメントの作成から変更されたバージョンの保存までのステップバイステップのガイドを提供しました。このコードを独自の C# プロジェクトに組み込んで、PDF ファイル内のテキストの回転を操作できるようになりました。

### よくある質問

#### Q: 「テキストフラグメントを使用してテキストを回転」チュートリアルの目的は何ですか?

A: 「テキスト フラグメントを使用したテキストの回転」チュートリアルは、.NET 用の Aspose.PDF ライブラリを使用して、PDF ドキュメント内のテキスト フラグメントを使用してテキストを回転するプロセスをガイドすることを目的としています。このチュートリアルでは、この機能を実現するための段階的な手順とサンプル コードを提供します。

#### Q: 「テキストの断片を使用してテキストを回転する」とはどういう意味ですか?

A: テキスト フラグメントを使用したテキストの回転とは、Aspose.PDF ライブラリを使用して PDF ドキュメント内の個々のテキスト フラグメントに回転を適用する機能を指します。この手法を使用すると、PDF コンテンツ内のさまざまな角度または位置でテキストの方向を制御できます。

#### Q: PDF ドキュメント内のテキストの断片を回転したいのはなぜですか?

A: PDF ドキュメント内のテキストの断片を回転すると、特定のコンテンツを強調したり、芸術的なデザインを作成したり、レイアウトや読みやすさを改善したりするなど、さまざまな目的に役立ちます。

#### Q: チュートリアル用にプロジェクトを設定するにはどうすればよいですか?

A: プロジェクトをセットアップするには:

1. 好みの統合開発環境 (IDE) で新しい C# プロジェクトを作成します。
2. Aspose.PDF for .NET ライブラリへの参照を追加します。
3. 必要な using ディレクティブを C# ファイルに追加します。

#### Q: 新しい PDF ドキュメントを作成するにはどうすればよいですか?

 A: 新しい PDF ドキュメントを作成するには、`Document`Aspose.PDF ライブラリのオブジェクト。このオブジェクトを使用して、ページとコンテンツを PDF に追加できます。

#### Q: テキスト フラグメントを使用してテキスト フラグメントを回転するにはどうすればよいですか?

A: テキスト フラグメントを使用してテキスト フラグメントを回転するには:

1. 作成する`TextFragment`オブジェクト。
2. テキストとテキストフラグメントのプロパティを設定します。
3. ページ上のテキスト断片の位置を指定します。
4. を使用して回転角度を設定します。`TextState.Rotation`テキストフラグメントのプロパティ。
5. を作成します`TextBuilder`オブジェクトを作成し、テキストの断片を PDF ページに追加します。

#### Q: 異なるテキスト断片に異なる回転角度を適用できますか?

 A: はい、異なる回転角度を異なる角度に適用できます。`TextFragment`オブジェクト。各テキスト フラグメントは、`TextState.Rotation`財産。

#### Q: 回転したテキスト断片を含む PDF ドキュメントを保存するにはどうすればよいですか?

 A: 回転したテキスト断片を含む PDF ドキュメントを保存するには、`Save`の方法`Document`オブジェクトを指定し、必要な出力ファイルのパスと名前を指定します。