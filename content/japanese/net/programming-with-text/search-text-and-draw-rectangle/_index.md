---
title: テキストを検索して四角形を描く
linktitle: テキストを検索して四角形を描く
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、PDF 内のテキストを検索し、見つかったテキストの周囲に四角形を描画し、変更されたドキュメントを保存する方法を学習します。
type: docs
weight: 460
url: /ja/net/programming-with-text/search-text-and-draw-rectangle/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内の特定のテキストを検索し、見つかったテキストの周囲に四角形を描画し、変更されたドキュメントを保存する方法について説明します。提供されている C# ソース コードでは、このプロセスを段階的に示しています。

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
```

## ステップ3: ドキュメントディレクトリへのパスを設定する

ドキュメントディレクトリへのパスを設定するには、`dataDir`変数：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。

## ステップ4: PDF文書を読み込む

 PDF文書を読み込むには、`Document`クラス：

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

交換する`"SearchAndGetTextFromAll.pdf"` PDF ファイルの実際の名前を入力します。

## ステップ5: TextFragmentAbsorberを作成する

作成する`TextFragmentAbsorber`入力された検索フレーズのすべてのインスタンスを検索するオブジェクト:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

交換する`@"[\S]+"`希望する正規表現パターンを使用します。

## ステップ6: 正規表現検索を有効にする

正規表現検索を有効にするには、`TextSearchOptions`吸収体の特性:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## ステップ7: すべてのページを検索する

ドキュメントのすべてのページの吸収剤を受け入れます。

```csharp
document.Pages.Accept(textAbsorber);
```

## ステップ8: 見つかったテキストの周囲に四角形を描く

作成する`PdfContentEditor`オブジェクトを取得し、取得したテキスト フラグメントをループして、各テキスト セグメントの周囲に四角形を描画します。

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

## ステップ9: 変更したドキュメントを保存する

変更したドキュメントを保存します。

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

必ず交換してください`"SearchTextAndDrawRectangle_out.pdf"`希望する出力ファイル名を指定します。

### Aspose.PDF for .NET を使用してテキストを検索し、四角形を描画するためのサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントを開く
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
//正規表現に一致するすべてのフレーズを見つけるためにTextAbsorberオブジェクトを作成します。
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

おめでとうございます! Aspose.PDF for .NET を使用して、PDF ドキュメント内の特定のテキストを検索し、見つかったテキストの周囲に四角形を描画し、変更したドキュメントを保存する方法を学習しました。このチュートリアルでは、プロジェクトのセットアップから必要なアクションの実行まで、ステップ バイ ステップのガイドを提供しました。これで、このコードを独自の C# プロジェクトに組み込んで、PDF ファイル内のテキストを操作し、四角形を描画できるようになりました。

### よくある質問

#### Q: 「テキストを検索して四角形を描画する」チュートリアルの目的は何ですか?

A: 「テキストの検索と四角形の描画」チュートリアルは、Aspose.PDF ライブラリ for .NET を使用して PDF ドキュメント内の特定のテキストを検索し、見つかったテキスト セグメントの周囲に四角形を描画し、変更されたドキュメントを保存するプロセスをユーザーに案内することを目的としています。このチュートリアルでは、プロセスの各ステップを説明する詳細な手順と C# コード サンプルが提供されます。

#### Q: このチュートリアルは、PDF ドキュメント内の特定のテキストの周囲に四角形を描画するのにどのように役立ちますか?

A: このチュートリアルでは、PDF ドキュメント内の特定のテキスト セグメントを見つけてその周囲に四角形を描画する方法について包括的なガイドを提供します。プロジェクトの設定、PDF ドキュメントの読み込み、正規表現検索の有効化、見つかったテキスト セグメントの周囲に四角形を描画、変更した PDF を保存するプロセスを示します。

#### Q: このチュートリアルを実行するために必要な前提条件は何ですか?

A: チュートリアルを始める前に、C# プログラミング言語の基礎を理解しておく必要があります。また、Aspose.PDF for .NET ライブラリがインストールされている必要があります。Aspose Web サイトから入手するか、NuGet を使用してプロジェクトにインストールできます。

#### Q: このチュートリアルに従うためにプロジェクトを設定するにはどうすればよいですか?

A: まず、お好みの統合開発環境 (IDE) で新しい C# プロジェクトを作成します。次に、Aspose.PDF for .NET ライブラリへの参照をプロジェクトに追加します。これにより、ライブラリの機能を使用して PDF ドキュメントを操作できるようになります。

#### Q: このチュートリアルを使用して、特定のテキストの周囲に四角形を描くことはできますか?

A: はい、このチュートリアルでは、PDF ドキュメント内の特定のテキスト セグメントの周囲に四角形を描画することに焦点を当てています。正規表現を使用して目的のテキストを見つけ、識別されたテキスト セグメントの周囲に四角形を作成し、変更した PDF を保存する方法を説明します。

#### Q: 検索したいテキストを指定して、その周囲に四角形を描くにはどうすればいいですか?

 A: 検索したいテキストを指定して四角形を描くには、`TextFragmentAbsorber`オブジェクトを作成し、そのパターンを`Text`パラメータ。デフォルトのパターンを置き換える`@"[\S]+"`チュートリアルのコードに、希望する正規表現パターンを入力します。

#### Q: テキストの正規表現検索を有効にするにはどうすればいいですか?

 A: 正規表現検索は、`TextSearchOptions`オブジェクトとその値を設定する`true`このオブジェクトを`TextSearchOptions`の財産`TextFragmentAbsorber`インスタンス。これにより、テキスト検索中に正規表現パターンが使用されるようになります。

#### Q: 見つかったテキストの周囲に四角形を描くにはどうすればいいですか?

 A: テキストセグメントを識別した後、`TextFragmentAbsorber`チュートリアルでは、これらのセグメントを反復処理するループが用意されています。各テキストセグメントについて、チュートリアルでは、`DrawBox`メソッドを使用して、四角形の外観を指定します。

#### Q: 四角形を描画した変更済みの PDF を保存する手順は何ですか?

A: 希望するテキストセグメントの周囲に四角形を描いた後、`Document`クラスの`Save`メソッドを使用して、変更したドキュメントを保存します。チュートリアルのサンプル コードでは、編集した PDF を保存し、成功メッセージを表示する方法を示します。

#### Q: 描画した長方形の外観をカスタマイズできますか?

 A: はい、描画した四角形の外観をカスタマイズできます。チュートリアルのサンプルコードでは、`DrawBox`メソッドは長方形を作成するために使用されます。色、スタイル、太さなどのプロパティを変更して、描画された長方形の外観をカスタマイズできます。