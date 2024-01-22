---
title: PDF ファイルの段落を使用してテキストを回転する
linktitle: PDF ファイルの段落を使用してテキストを回転する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、PDF ファイル内の段落を使用してテキストを回転する方法を学びます。
type: docs
weight: 380
url: /ja/net/programming-with-text/rotate-text-using-paragraph/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して、段落を使用してテキストを回転する方法について説明します。提供されている C# ソース コードは、プロセスを段階的に示しています。

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

## ステップ 5: テキスト段落を作成する

を作成します`TextParagraph`オブジェクトを取得し、ページ上の位置を設定します。

```csharp
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
```

要件に応じて位置の値を調整します。

## ステップ 6: テキストフラグメントの作成と構成

複数作成する`TextFragment`オブジェクトを作成し、そのテキストとプロパティを設定します。

```csharp
TextFragment textFragment1 = new TextFragment("rotated text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment1.TextState.Rotation = 45;

TextFragment textFragment2 = new TextFragment("main text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment3 = new TextFragment("another rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = -45;
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
```

## ステップ 9: PDF ドキュメントを保存する

変更した PDF ドキュメントをファイルに保存するには、`Save`方法：

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```

必ず交換してください`"TextFragmentTests_Rotated2_out.pdf"`希望の出力ファイル名を付けます。

### Aspose.PDF for .NET を使用した段落を使用したテキストの回転のサンプル ソース コード 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントオブジェクトの初期化
Document pdfDocument = new Document();
//特定のページを取得する
Page pdfPage = (Page)pdfDocument.Pages.Add();
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
//テキストフラグメントを作成する
TextFragment textFragment1 = new TextFragment("rotated text");
//テキストのプロパティを設定する
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
//回転を設定する
textFragment1.TextState.Rotation = 45;
//テキストフラグメントを作成する
TextFragment textFragment2 = new TextFragment("main text");
//テキストのプロパティを設定する
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
//テキストフラグメントを作成する
TextFragment textFragment3 = new TextFragment("another rotated text");
//テキストのプロパティを設定する
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
//回転を設定する
textFragment3.TextState.Rotation = -45;
//テキストの断片を段落に追加する
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
//TextBuilder オブジェクトを作成する
TextBuilder textBuilder = new TextBuilder(pdfPage);
//PDF ページにテキスト段落を追加する
textBuilder.AppendParagraph(paragraph);
//文書の保存
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```


## 結論

おめでとう！ Aspose.PDF for .NET を使用して、PDF ドキュメント内の段落を使用してテキストを回転する方法を学習しました。このチュートリアルでは、ドキュメントの作成から変更されたバージョンの保存までのステップバイステップのガイドを提供しました。このコードを独自の C# プロジェクトに組み込んで、PDF ファイル内のテキストの回転を操作できるようになりました。

### よくある質問

#### Q: 「段落を使用してテキストを回転」チュートリアルの目的は何ですか?

A: 「段落を使用してテキストを回転」チュートリアルは、.NET 用の Aspose.PDF ライブラリを使用して、PDF ドキュメント内のテキスト段落を使用してテキストを回転するプロセスをガイドすることを目的としています。このチュートリアルでは、この機能を実現するための段階的な手順とサンプル コードを提供します。

#### Q: 「段落を使用してテキストを回転する」とはどういう意味ですか?

A: 段落を使用したテキストの回転とは、テキスト段落を使用して PDF ドキュメント内のテキストに回転を適用する機能を指します。この手法を使用すると、PDF コンテンツ内でテキストをさまざまな角度や位置に配置することができます。

#### Q: PDF ドキュメント内のテキストを回転したいのはなぜですか?

A: PDF ドキュメント内のテキストを回転すると、特定のコンテンツを強調したり、芸術的なデザインを作成したり、レイアウトや読みやすさを改善したりするなど、さまざまな目的に役立ちます。

#### Q: 新しい PDF ドキュメントを作成するにはどうすればよいですか?

 A: 新しい PDF ドキュメントを作成するには、`Document`Aspose.PDF ライブラリのオブジェクト。このオブジェクトを使用して、ページとコンテンツを PDF に追加できます。

#### Q: 段落を使用してテキストを回転するにはどうすればよいですか?

A: 段落を使用してテキストを回転するには:

1. を作成します`TextParagraph`物体。
2. 作成する`TextFragment`目的のテキストと回転角度を持つオブジェクト。
3. テキストの断片をテキスト段落に追加します。
4. を作成します`TextBuilder`オブジェクトを作成し、テキスト段落を特定の PDF ページに追加します。

#### Q: 個々のテキスト断片の回転角度を制御できますか?

 A: はい、個々の回転角度を制御できます。`TextFragment`を設定してオブジェクトを`TextState.Rotation`財産。正の値は時計回りの回転を示し、負の値は反時計回りの回転を示します。

#### Q: 同じ段落内の異なるテキスト断片に異なる回転角度を適用できますか?

 A: はい、異なる回転角度を異なる角度に適用できます。`TextFragment`同じ段落内のオブジェクトを設定するには、`TextState.Rotation`それに応じて各フラグメントのプロパティが決定されます。

#### Q: 回転した PDF ドキュメントを保存するにはどうすればよいですか?

A: 回転した PDF ドキュメントを保存するには、`Save`の方法`Document`オブジェクトを指定し、必要な出力ファイルのパスと名前を指定します。