---
title: テキストを検索して四角形を描画する
linktitle: テキストを検索して四角形を描画する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、PDF 内のテキストを検索し、見つかったテキストの周囲に四角形を描画し、変更したドキュメントを保存する方法を学びます。
type: docs
weight: 460
url: /ja/net/programming-with-text/search-text-and-draw-rectangle/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内の特定のテキストを検索し、見つかったテキストの周囲に四角形を描画し、変更したドキュメントを保存する方法について説明します。提供されている C# ソース コードは、プロセスを段階的に示しています。

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
```

## ステップ 3: ドキュメント ディレクトリへのパスを設定する

を使用してドキュメント ディレクトリへのパスを設定します。`dataDir`変数：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを置き換えます。

## ステップ 4: PDF ドキュメントをロードする

次のコマンドを使用して PDF ドキュメントをロードします。`Document`クラス：

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

交換する`"SearchAndGetTextFromAll.pdf"` PDF ファイルの実際の名前を付けます。

## ステップ 5: TextFragmentAbsorber を作成する

を作成します`TextFragmentAbsorber`オブジェクトを使用して、入力検索フレーズのすべてのインスタンスを検索します。

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

交換する`@"[\S]+"`希望の正規表現パターンを使用します。

## ステップ 6: 正規表現検索を有効にする

を設定して正規表現検索を有効にします。`TextSearchOptions`吸収体の特性:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## ステップ 7: すべてのページで検索する

ドキュメントのすべてのページに対して吸収体を受け入れます。

```csharp
document.Pages.Accept(textAbsorber);
```

## ステップ 8: 見つかったテキストの周囲に四角形を描画します。

を作成します`PdfContentEditor`オブジェクトを作成し、取得したテキスト フラグメントをループして、各テキスト セグメントの周囲に四角形を描画します。

```csharp
var editor = new PdfContentEditor(document);
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

## ステップ 9: 変更したドキュメントを保存する

変更したドキュメントを保存します。

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

必ず交換してください`"SearchTextAndDrawRectangle_out.pdf"`希望の出力ファイル名を付けます。

### Aspose.PDF for .NET を使用したテキストの検索と四角形の描画のサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開いた文書
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
//TextAbsorber オブジェクトを作成して、正規表現に一致するすべてのフレーズを検索します
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
document.Pages.Accept(textAbsorber); 
var editor = new PdfContentEditor(document); 
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
			DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
	}
}
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

## 結論

おめでとう！ Aspose.PDF for .NET を使用して、PDF ドキュメント内の特定のテキストを検索し、見つかったテキストの周囲に四角形を描画し、変更したドキュメントを保存する方法を学習しました。このチュートリアルでは、プロジェクトのセットアップから必要なアクションの実行までのステップバイステップのガイドを提供しました。このコードを独自の C# プロジェクトに組み込んで、PDF ファイル内のテキストを操作したり四角形を描画したりできるようになりました。

### よくある質問

#### Q: 「テキストを検索して四角形を描画する」チュートリアルの目的は何ですか?

A: 「テキストの検索と四角形の描画」チュートリアルは、.NET 用の Aspose.PDF ライブラリを使用して、PDF ドキュメント内の特定のテキストを検索し、見つかったテキスト セグメントの周囲に四角形を描画し、変更したテキストを保存するプロセスをユーザーにガイドすることを目的としています。書類。このチュートリアルでは、プロセスの各ステップを説明するための詳細な手順と C# コード サンプルが提供されます。

#### Q: このチュートリアルは、PDF ドキュメント内の特定のテキストの周囲に四角形を描画するのにどのように役立ちますか?

A: このチュートリアルでは、PDF ドキュメント内の特定のテキスト セグメントを見つけて周囲に四角形を描画する方法についての包括的なガイドを提供します。ここでは、プロジェクトのセットアップ、PDF ドキュメントのロード、正規表現検索の有効化、見つかったテキスト セグメントの周囲に四角形の描画、変更された PDF の保存のプロセスを示します。

#### Q: このチュートリアルに従うにはどのような前提条件が必要ですか?

A: チュートリアルを開始する前に、C# プログラミング言語の基本を理解しておく必要があります。さらに、Aspose.PDF for .NET ライブラリをインストールする必要があります。 Aspose Web サイトから入手するか、NuGet を使用してプロジェクトにインストールできます。

#### Q: このチュートリアルに従うようにプロジェクトを設定するにはどうすればよいですか?

A: まず、好みの統合開発環境 (IDE) で新しい C# プロジェクトを作成します。次に、Aspose.PDF for .NET ライブラリへの参照をプロジェクトに追加します。これにより、ライブラリの機能を使用して PDF ドキュメントを操作できるようになります。

#### Q: このチュートリアルを使用して、特定のテキストの周囲に四角形を描画できますか?

A: はい、このチュートリアルでは、PDF ドキュメント内の特定のテキスト セグメントの周囲に四角形を描画することに重点を置いています。正規表現を使用して目的のテキストを検索し、特定されたテキスト セグメントの周囲に四角形を作成し、変更した PDF を保存する方法を示します。

#### Q: 検索したいテキストを指定して周囲に四角形を描くにはどうすればよいですか?

 A: 検索するテキストを指定して周囲に四角形を描画するには、`TextFragmentAbsorber`オブジェクトを作成し、`Text`パラメータ。デフォルトのパターンを置き換える`@"[\S]+"`チュートリアルのコード内で、必要な正規表現パターンを使用します。

#### Q: テキストの正規表現検索を有効にするにはどうすればよいですか?

 A: 正規表現検索は、`TextSearchOptions`オブジェクトを作成し、その値を`true`。このオブジェクトを`TextSearchOptions`の財産`TextFragmentAbsorber`実例。これにより、テキスト検索中に正規表現パターンが確実に使用されます。

#### Q: 見つかったテキストの周囲に四角形を描画するにはどうすればよいですか?

 A: を使用してテキストセグメントを識別した後、`TextFragmentAbsorber` 、チュートリアルでは、これらのセグメントを反復処理するループが提供されます。このチュートリアルでは、テキスト セグメントごとに、`DrawBox`メソッドを使用して、四角形の外観を指定します。

#### Q: 長方形が描かれた変更された PDF を保存するには、どのような手順を実行しますか?

A: 目的のテキスト セグメントの周囲に四角形を描画した後、`Document`クラスの`Save`変更されたドキュメントを保存するメソッド。チュートリアルのサンプル コードでは、編集した PDF を保存し、成功メッセージを表示する方法を示します。

#### Q: 描画された長方形の外観をカスタマイズできますか?

 A: はい、描画された長方形の外観をカスタマイズできます。チュートリアルのサンプル コードでは、`DrawBox`メソッドを使用して長方形を作成します。色、スタイル、太さなどのプロパティを変更して、描画された四角形の外観をカスタマイズできます。