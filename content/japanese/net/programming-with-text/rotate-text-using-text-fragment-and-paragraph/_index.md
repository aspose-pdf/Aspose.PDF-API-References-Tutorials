---
title: テキストフラグメントと段落を使用してテキストを回転する
linktitle: テキストフラグメントと段落を使用してテキストを回転する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、PDF ドキュメント内のテキスト フラグメントと段落を使用してテキストを回転する方法を学習します。
type: docs
weight: 400
url: /ja/net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して、テキスト フラグメントと段落を使用してテキストを回転させる方法について説明します。提供されている C# ソース コードは、プロセスを段階的に示しています。

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

複数作成`TextFragment`オブジェクトを作成し、テキストとプロパティを設定し、回転角度を指定します。

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 315;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 270;
```

必要に応じて、テキスト、回転角度、その他のプロパティを調整します。

## ステップ6: ページにテキストフラグメントを追加する

作成したテキストフラグメントをページに追加するには、`Paragraphs`コレクション：

```csharp
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
```

## ステップ7: PDF文書を保存する

変更したPDF文書をファイルに保存するには、`Save`方法：

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

必ず交換してください`"TextFragmentTests_Rotated3_out.pdf"`希望する出力ファイル名を指定します。

### Aspose.PDF for .NET を使用してテキスト フラグメントと段落を使用してテキストを回転するためのサンプル ソース コード 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントオブジェクトを初期化する
Document pdfDocument = new Document();
//特定のページを取得する
Page pdfPage = (Page)pdfDocument.Pages.Add();
//テキストフラグメントを作成
TextFragment textFragment1 = new TextFragment("main text");
//テキストプロパティを設定する
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
//テキストフラグメントを作成
TextFragment textFragment2 = new TextFragment("rotated text");
//テキストプロパティを設定する
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
//回転を設定する
textFragment2.TextState.Rotation = 315;
//テキストフラグメントを作成
TextFragment textFragment3 = new TextFragment("rotated text");
//テキストプロパティを設定する
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
//回転を設定する
textFragment3.TextState.Rotation = 270;
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
//ドキュメントを保存
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

## 結論

おめでとうございます! Aspose.PDF for .NET を使用して、PDF ドキュメント内のテキスト フラグメントと段落を使用してテキストを回転する方法を学習しました。このチュートリアルでは、ドキュメントの作成から変更後のバージョンの保存まで、ステップ バイ ステップで説明しました。これで、このコードを独自の C# プロジェクトに組み込んで、PDF ファイル内のテキストの回転を操作できるようになりました。

### よくある質問

#### Q: 「テキストフラグメントと段落を使用してテキストを回転する」チュートリアルの目的は何ですか?

A: 「テキスト フラグメントと段落を使用してテキストを回転する」チュートリアルは、Aspose.PDF ライブラリ for .NET を使用して PDF ドキュメント内のテキスト フラグメントと段落の両方を使用してテキストを回転するプロセスを説明することを目的としています。このチュートリアルでは、この機能を実現するための手順とサンプル コードが提供されます。

#### Q: このチュートリアルは、以前のテキスト回転チュートリアルとどう違うのですか?

A: このチュートリアルでは、テキストフラグメントと段落を組み合わせて、PDF文書内でテキストの回転を実現します。テキストフラグメントを個別に回転させてから、ページの`Paragraphs`より包括的なテキスト回転効果を実現するためのコレクション。

#### Q: テキストの回転にテキストフラグメントと段落を使用する利点は何ですか?

A: テキスト フラグメントと段落を併用すると、テキストの回転の柔軟性が向上します。テキスト フラグメントでは個別の回転と書式設定が可能になり、段落ではページ内でテキスト フラグメントを配置および配置するための構造が提供されます。

#### Q: 同じ段落内の異なるテキストフラグメントに異なる回転角度を適用できますか?

 A: はい、異なる回転角度を異なるオブジェクトに適用できます。`TextFragment`同じ段落内のオブジェクト。各テキストフラグメントには、`TextState.Rotation`財産。

#### Q: この方法を使用して複雑なテキスト回転効果を実現することは可能ですか?

A: はい、さまざまな回転角度のテキストフラグメントを組み合わせて段落内に配置することで、複雑でカスタマイズされたテキスト回転効果を実現し、PDF ドキュメントの視覚的な魅力を高めることができます。

#### Q: テキストフラグメントと段落を使用してテキストを回転するには、どのような手順が必要ですか?

A: 手順は次のとおりです。

1. 新しい C# プロジェクトを作成し、Aspose.PDF for .NET ライブラリへの参照を追加してプロジェクトを設定します。
2. PDF ドキュメントを作成し、ページを追加します。
3. テキストフラグメントを作成し、そのプロパティを設定し、回転角度を指定します。
4. ページにテキストフラグメントを追加するには、`Paragraphs`コレクション。
5. 変更された PDF ドキュメントを保存します。

#### Q: 段落全体に回転を適用できますか?

 A: はい、段落全体に回転を適用することができます。`TextState.Rotation`段落自体のプロパティ。これにより、その段落内のすべてのテキスト フラグメントが回転します。