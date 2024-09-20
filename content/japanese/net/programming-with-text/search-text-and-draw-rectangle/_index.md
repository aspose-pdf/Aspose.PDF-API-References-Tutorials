---
title: テキストを検索して四角形を描く
linktitle: テキストを検索して四角形を描く
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF 内のテキストを検索し、四角形で強調表示する方法を学びます。PDF 操作スキルを向上させるための簡単なステップバイステップのチュートリアルです。
type: docs
weight: 460
url: /ja/net/programming-with-text/search-text-and-draw-rectangle/
---
## 導入

PDF 操作スキルを向上させたいですか? PDF ファイル内の特定のテキストを検索し、それを四角形で強調表示する方法を学びたいですか? 完璧なガイドにたどり着きました! 今日は、Aspose.PDF for .NET を使用して PDF ドキュメント内のテキストを検索し、その周りに四角形を描く方法を説明します。この記事では、明快さと有用性を念頭に設計されたステップバイステップのチュートリアルを提供します。このチュートリアルに沿って、プロジェクトにこれらのテクニックを適用できます。 

## 前提条件

チュートリアルに進む前に、スムーズなワークフローを実現するために必要なものを準備しましょう。

1. .NET の基本的な理解: このチュートリアルを効果的に実行するには、C# プログラミングと .NET フレームワークに精通している必要があります。
   
2. Visual Studio がインストールされている: コードを記述してテストするには、統合開発環境 (IDE) が必要です。Visual Studio Community は優れたオプションであり、無料です。
   
3. Aspose.PDF for .NET: プロジェクトにAspose.PDFライブラリをインストールする必要があります。ダウンロードできます。[ここ](https://releases.aspose.com/pdf/net/)または、[一時ライセンス](https://purchase.aspose.com/temporary-license/)拡張機能用。
   
4. サンプルPDFドキュメント: このチュートリアルでは、次のサンプルPDFファイルが必要です。`SearchAndGetTextFromAll.pdf`プロジェクト ディレクトリに保存されます。 

## パッケージのインポート

まず、必要なパッケージを .NET プロジェクトにインポートする必要があります。次の手順に従います。

### Visual Studioを開く

Visual Studio を起動し、新しいコンソール アプリケーションを作成するか、PDF 機能を実装する既存のコンソール アプリケーションを使用します。

### Aspose.PDF をプロジェクトに追加する

1. ソリューション エクスプローラーでプロジェクトを右クリックします。
2. 「NuGet パッケージの管理」を選択します。
3. 検索する`Aspose.PDF`最新バージョンをインストールしてください。

これを行うことで、これから実行するすべての素晴らしい PDF 操作の基礎が整います。

## 名前空間のインポート

プログラム ファイルの先頭で、Aspose ライブラリから関連する名前空間をインポートする必要があります。

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
using Aspose.Pdf.Facades;
```

これにより、タスク用の Aspose.PDF ライブラリ内のクラスとメソッドに簡単にアクセスできるようになります。


これですべての設定が完了したので、PDF 内のテキストを検索し、その周囲に四角形を描画するプロセスを管理しやすい手順に分解してみましょう。

## ステップ1: ドキュメントのパスを設定する

まず、PDFファイルへのパスを設定します。`YOUR DOCUMENT DIRECTORY`実際の経路で`SearchAndGetTextFromAll.pdf`保存されます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ2: PDFドキュメントを開く

次に、`Document` PDF を読み込むクラス:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

このコード行は指定された PDF ファイルを開き、さらに操作できるようにします。

## ステップ3: テキストアブソーバーを作成する

さて、その文書内のテキストを検索する方法が必要です。そのためには、`TextFragmentAbsorber`:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

正規表現`@"[\S]+"` PDF 内の空白以外の文字列に一致するように設計されています。 

## ステップ4: テキスト検索オプションを構成する

次に、テキスト検索オプションを設定する必要があります。

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

ここでは、`true`パラメータは、検索時に大文字と小文字を区別することを意味します。`false`大文字と小文字を区別しない検索をしたい場合。

## ステップ5: 文書内のテキストアブソーバーを受け入れる

あなたの`TextFragmentAbsorber`検索オプションの準備ができたら、ドキュメントからテキストを吸収します。

```csharp
document.Pages.Accept(textAbsorber);
```

このメソッドは、PDF 内の各ページを調べて、指定されたパターンに一致するテキスト フラグメントを検索します。

## ステップ6: PdfContentEditorを作成する

文書に図形を描くには、`PdfContentEditor`:

```csharp
var editor = new PdfContentEditor(document);
```

このエディターを使用すると、PDF コンテンツを簡単に操作および編集できます。

## ステップ7: 見つかったテキストフラグメントをループする

ここで、見つかったテキスト フラグメントをループして、その周りに四角形を描画します。

```csharp
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

このループは各テキストフラグメントとそのセグメントを反復処理し、`DrawBox`長方形を描画する方法。

## ステップ8: DrawBoxメソッドを定義する

定義する必要があるのは`DrawBox`メソッドは、四角形の描画ロジックを処理します。簡単な実装は次のとおりです。

```csharp
private static void DrawBox(PdfContentEditor editor, int pageNumber, TextSegment textSegment, System.Drawing.Color color)
{
    //テキストセグメントに基づいて長方形の寸法を計算する
    float x = textSegment.Rectangle.LLX;
    float y = textSegment.Rectangle.LLY;
    float width = textSegment.Rectangle.Width;
    float height = textSegment.Rectangle.Height;

    //計算された値を使用して長方形を描く
    editor.DrawRectangle(pageNumber, x, y, width, height, color, 1);
}
```

このメソッドは、セグメントの境界四角形に基づいて四角形の位置とサイズを決定し、エディターを使用してそれを描画します。

## ステップ9: 変更したドキュメントを保存する

見つかったテキストの周囲に四角形を描画したら、変更したドキュメントを保存できます。

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

元のドキュメントが上書きされないように、新しいファイルが別の名前で保存されていることを確認してください。

## ステップ10: 確認メッセージ

最後に、操作が成功したことを知らせる確認メッセージをコンソールに出力します。

```csharp
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

これで完了です。PDF 内のテキストを検索し、四角形で強調表示するスクリプトが正常に作成されました。

## 結論

おめでとうございます! Aspose.PDF for .NET を使用して PDF 操作能力を大幅に強化できる強力なスキルを習得しました。簡単な手順をいくつか実行するだけで、ドキュメント内の任意のテキストを検索して視覚的に強調表示できるため、PDF ドキュメントをよりインタラクティブで管理しやすいものにできます。さまざまな正規表現パターンやカラー オプションを試して、このツールを自分だけのものにしてください。

## よくある質問

### Aspose.PDF for .NET とは何ですか?
Aspose.PDF for .NET は、PDF ドキュメントをプログラムで作成、操作、変換するための包括的な方法を提供するライブラリです。

### Aspose.PDF を無料で使用できますか?
はい、Aspose ではライブラリの機能をテストできる無料トライアルを提供しています。ぜひお試しください。[ここ](https://releases.aspose.com/).

### Aspose.PDF for .NET で使用するプログラミング言語は何ですか?
Aspose.PDF for .NET は、C# およびその他の .NET 言語で使用するように設計されています。

### Aspose.PDF に関するサポートを受けるにはどうすればよいですか?
問題や質問がある場合は、Aspose サポートフォーラムにアクセスしてサポートを受けることができます。サポートを探す[ここ](https://forum.aspose.com/c/pdf/10).

### Aspose.PDF for .NET はどこからダウンロードできますか?
ライブラリはAsposeのウェブサイトからダウンロードできます。[ここ](https://releases.aspose.com/pdf/net/).