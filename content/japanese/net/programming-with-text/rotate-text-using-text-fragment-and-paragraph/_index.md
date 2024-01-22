---
title: テキストの断片と段落を使用してテキストを回転する
linktitle: テキストの断片と段落を使用してテキストを回転する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、PDF ドキュメント内のテキストのフラグメントと段落を使用してテキストを回転する方法を学びます。
type: docs
weight: 400
url: /ja/net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して、テキストのフラグメントと段落を使用してテキストを回転する方法について説明します。提供されている C# ソース コードは、プロセスを段階的に示しています。

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

複数作成する`TextFragment`オブジェクトを作成し、そのテキストとプロパティを設定し、回転角度を指定します。

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

## ステップ 6: テキストフラグメントをページに追加する

作成したテキスト フラグメントをページに追加するには、`Paragraphs`コレクション：

```csharp
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
```

## ステップ 7: PDF ドキュメントを保存する

変更した PDF ドキュメントをファイルに保存するには、`Save`方法：

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

必ず交換してください`"TextFragmentTests_Rotated3_out.pdf"`希望の出力ファイル名を付けます。

### Aspose.PDF for .NET を使用したテキストの断片と段落を使用したテキストの回転のサンプル ソース コード 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントオブジェクトの初期化
Document pdfDocument = new Document();
//特定のページを取得する
Page pdfPage = (Page)pdfDocument.Pages.Add();
//テキストフラグメントを作成する
TextFragment textFragment1 = new TextFragment("main text");
//テキストのプロパティを設定する
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
//テキストフラグメントを作成する
TextFragment textFragment2 = new TextFragment("rotated text");
//テキストのプロパティを設定する
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
//回転を設定する
textFragment2.TextState.Rotation = 315;
//テキストフラグメントを作成する
TextFragment textFragment3 = new TextFragment("rotated text");
//テキストのプロパティを設定する
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
//回転を設定する
textFragment3.TextState.Rotation = 270;
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
//文書の保存
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

## 結論

おめでとう！ Aspose.PDF for .NET を使用して、PDF ドキュメント内のテキストの断片と段落を使用してテキストを回転する方法を学習しました。このチュートリアルでは、ドキュメントの作成から変更されたバージョンの保存までのステップバイステップのガイドを提供しました。このコードを独自の C# プロジェクトに組み込んで、PDF ファイル内のテキストの回転を操作できるようになりました。

### よくある質問

#### Q: 「テキストの断片と段落を使用してテキストを回転する」チュートリアルの目的は何ですか?

A: 「テキストの断片と段落を使用してテキストを回転する」チュートリアルは、.NET 用の Aspose.PDF ライブラリを使用して、PDF ドキュメント内のテキストの断片と段落の両方を使用してテキストを回転するプロセスをガイドすることを目的としています。このチュートリアルでは、この機能を実現するための段階的な手順とサンプル コードを提供します。

#### Q: このチュートリアルは、以前のテキスト回転チュートリアルとどのように異なりますか?

A: このチュートリアルでは、テキストのフラグメントと段落を組み合わせて、PDF ドキュメント内でテキストの回転を実現します。テキストの断片を個別に回転してページに追加する方法を示します。`Paragraphs`コレクションを使用して、より包括的なテキスト回転効果を実現します。

#### Q: テキストの回転にテキストの断片と段落を使用する利点は何ですか?

A: テキストの断片と段落を一緒に使用すると、テキストの回転をより柔軟に行うことができます。テキスト フラグメントを使用すると、個別の回転と書式設定が可能になり、段落はページ内でテキスト フラグメントを配置および配置するための構造を提供します。

#### Q: 同じ段落内の異なるテキスト断片に異なる回転角度を適用できますか?

 A: はい、異なる回転角度を異なる角度に適用できます。`TextFragment`同じ段落内のオブジェクト。各テキスト フラグメントは、`TextState.Rotation`財産。

#### Q: この方法を使用して、複雑なテキスト回転効果を実現することはできますか?

A: はい、さまざまな回転角度のテキスト フラグメントを組み合わせて段落内に配置することで、複雑でカスタマイズされたテキストの回転効果を実現し、PDF ドキュメントの視覚的な魅力を高めることができます。

#### Q: テキストの断片や段落を使用してテキストを回転するには、どのような手順が必要ですか?

A: 手順には次のものが含まれます。

1. 新しい C# プロジェクトを作成し、Aspose.PDF for .NET ライブラリへの参照を追加することにより、プロジェクトをセットアップします。
2. PDF ドキュメントを作成し、ページを追加します。
3. テキストフラグメントの作成、そのプロパティの設定、および回転角度の指定。
4. を使用してページにテキスト フラグメントを追加する`Paragraphs`コレクション。
5. 変更した PDF ドキュメントを保存します。

#### Q: 段落全体に回転を適用できますか?

 A: はい、設定することで段落全体に回転を適用できます。`TextState.Rotation`段落自体のプロパティ。これにより、その段落内のすべてのテキスト断片が回転します。