---
title: PDF ファイル内のテキスト セグメント ページを検索
linktitle: PDF ファイル内のテキスト セグメント ページを検索
second_title: Aspose.PDF for .NET API リファレンス
description: この詳細なステップバイステップ ガイドでは、Aspose.PDF for .NET を使用して PDF ファイル内のテキスト セグメントを検索する方法を学習します。テキストの抽出、セグメントの分析などを行います。
type: docs
weight: 470
url: /ja/net/programming-with-text/search-text-segments-page/
---
## 導入

Aspose.PDF for .NET を使用して PDF ドキュメント内の特定のテキスト セグメントを検索する方法を考えたことはありませんか? いいえ、大丈夫です! このガイドでは、プロセスを簡単なステップ バイ ステップ形式で説明します。情報の抽出、テキストの分析、または PDF 操作の複雑さの把握など、Aspose.PDF for .NET がお手伝いします。さあ、始めましょう!

## 前提条件

始める前に、必要なものがすべて揃っていることを確認しましょう。

-  Aspose.PDF for .NET: ライブラリがインストールされていることを確認してください。[ここ](https://releases.aspose.com/pdf/net/).
- .NET Framework: マシンに .NET がインストールされていることを確認します。
- 開発環境: Visual Studio または .NET をサポートする任意の IDE が推奨されます。
- PDF ドキュメント: テキスト セグメントを検索する PDF ファイル。

 Aspose.PDF for .NETをまだお持ちでない場合は、ご心配なく。こちらから無料トライアルを入手できます。[ここ](https://releases.aspose.com/)または購入する[ここ](https://purchase.aspose.com/buy).

## パッケージのインポート

コーディングを始める前に、プロジェクトに必要なパッケージをインポートすることが重要です。これにより、PDF 操作タスクに必要なすべてのクラスとメソッドが使用できるようになります。

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

基本的な準備が整ったので、ステップバイステップのガイドに進みましょう。


## ステップ1: PDFドキュメントを読み込む

プロセスの最初のステップは、PDF ファイルをプログラムに読み込むことです。読み込まれたドキュメントがなければ、検索するものがありませんよね? やり方は次のとおりです。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントを開く
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

- `dataDir` : この変数はPDFファイルへのパスを保持します。`"YOUR DOCUMENT DIRECTORY"`ファイルが保存されている実際のディレクトリに置き換えます。
- `pdfDocument` : 使用して`Document`クラスでは、PDF をメモリに読み込みます。

## ステップ2: テキスト検索を設定する

ドキュメントが読み込まれたら、次のステップは`TextFragmentAbsorber`オブジェクトを使用すると、ドキュメント内の特定のテキストを検索できます。

```csharp
//入力された検索フレーズのすべてのインスタンスを検索する TextAbsorber オブジェクトを作成します。
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

- `TextFragmentAbsorber` : このオブジェクトは、検索するテキストのすべての出現箇所を取得するために使用されます。置換`"text"`検索したい実際のテキストを入力します。

## ステップ3: 特定のページのアブソーバーを受け入れる

必ずしも PDF ドキュメント全体を検索したいとは限りません。この例では、特定のページに絞り込んでいます。

```csharp
//すべてのページの吸収剤を受け入れる
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

- `pdfDocument.Pages[2]`: これは、ドキュメントの 2 ページ目のみを検索することを示します。インデックスを変更して、他のページを対象にすることもできます。
- `Accept()` : この方法では、`TextFragmentAbsorber`指定されたページ内のテキストを処理します。

## ステップ4: テキストフラグメントを抽出する

ページを検索した後、見つかったテキストの断片をコレクションに抽出します。

```csharp
//抽出されたテキストフラグメントを取得する
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- `TextFragmentCollection`: このコレクションには、検索プロセス中に見つかったテキスト フラグメントのすべてのインスタンスが保持されます。

## ステップ5: テキストフラグメントをループしてデータを抽出する

ここで、各テキスト フラグメントをループして、位置、フォント、色などの詳細を抽出します。

```csharp
//フラグメントをループする
foreach (TextFragment textFragment in textFragmentCollection)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        Console.WriteLine("Text : {0} ", textSegment.Text);
        Console.WriteLine("Position : {0} ", textSegment.Position);
        Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
        Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
        Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
        Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
        Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
        Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
        Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
        Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
    }
}
```

- `foreach (TextFragment textFragment in textFragmentCollection)` : それぞれをループします`TextFragment`コレクション内。
- `foreach (TextSegment textSegment in textFragment.Segments)`各フラグメント内には複数のセグメントがあります。それらをループして、関連するすべての情報を収集します。
- さまざまな特性`textSegment`これらは、テキストの位置 (X と Y)、フォントの詳細、サイズ、色など、テキストに関する詳細な情報を提供します。

## ステップ6: 結果を出力する

最後に、すべての情報を抽出した後、結果がコンソールに出力されます。これにより、テキストがどこにあるか、およびその書式設定の詳細を正確に確認できます。

わかりやすくするために、サンプル出力を以下に示します。

```
Text : text
Position : X: 45.0, Y: 75.0
XIndent : 45.0
YIndent : 75.0
Font - Name : Arial
Font - IsAccessible : True
Font - IsEmbedded : False
Font - IsSubset : False
Font Size : 12.0
Foreground Color : System.Drawing.Color [Black]
```

- この出力では、指定されたページ上のテキスト「text」の正確な位置と書式情報が提供されます。

## 結論

これで完了です。Aspose.PDF for .NET を使用して PDF ドキュメント内の特定のテキスト セグメントを検索する方法を学習しました。このプロセスは、大きな PDF を扱うときに非常に便利で、重要なテキストを効率的に特定して抽出できます。データの分析、情報の抽出、または単にドキュメント内を移動する場合でも、Aspose.PDF は作業を完了するための強力なツールを提供します。

## よくある質問

### 複数の単語やフレーズを検索できますか?
はい、変更できます`TextFragmentAbsorber`入力文字列を変更して異なるテキストを検索します。

### 複数のページにわたって検索することは可能ですか?
もちろんです！PDF内のすべてのページをループ処理して、`pdfDocument.Pages`.

### 大文字と小文字を区別しないテキストを検索するにはどうすればよいですか?
使用できます`TextSearchOptions`大文字と小文字を区別しない検索を有効にします。

### 見つけたテキストを後で変更することはできますか?
はい、`TextFragment`テキストのプロパティを変更できます。

### この方法は暗号化された PDF に適用できますか?
はい、正しいパスワードを使用して PDF のロックを解除すれば可能です。