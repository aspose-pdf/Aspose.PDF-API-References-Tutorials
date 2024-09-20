---
title: PDF ファイルに隠しテキストを追加して検索する
linktitle: PDF ファイルに隠しテキストを追加して検索する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ドキュメントに隠しテキストを追加および検索する方法を学びます。コード例を含むステップバイステップ ガイドです。
type: docs
weight: 20
url: /ja/net/programming-with-text/add-and-search-hidden-text/
---
## 導入

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルに隠しテキストを追加および検索する方法について、ステップ バイ ステップで説明します。熟練した開発者でも、プログラミング スキルの向上を目指す初心者でも、この記事は、隠しテキスト機能をアプリケーションに組み込むために必要な情報を提供します。

## 前提条件

コーディング部分に進む前に、いくつかの前提条件を満たす必要があります。

### 要件チェックリスト
- Visual Studio: Visual Studio がインストールされていることを確認してください。このチュートリアルでは、.NET Framework を使用していることを前提としています。
-  Aspose.PDF for .NET: Aspose.PDF for .NETライブラリが必要です。ダウンロードできます。[ここ](https://releases.aspose.com/pdf/net/).
- C# の基礎知識: C# プログラミングに精通していると、コード スニペットをよりよく理解できるようになります。

## パッケージのインポート

コードを開始する前に、必要な Aspose.PDF 名前空間をインポートする必要があります。手順は次のとおりです。

### プロジェクトを設定する
1. Visual Studio を開き、新しい C# プロジェクトを作成するか、既存のプロジェクトを使用します。
2.  Aspose.PDFをNuGetパッケージを追加してインストールします。NuGetパッケージマネージャーに移動して、以下を検索することで実行できます。`Aspose.PDF`. 
3. または、ライブラリを直接ダウンロードすることもできます。[ここ](https://releases.aspose.com/pdf/net/)それをプロジェクト内の参照として追加します。

### 必要な名前空間をインポートする
C# ファイルの先頭で、次の名前空間をインポートします。

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

これらの名前空間には PDF ドキュメントを操作するために必要なクラスとメソッドが含まれているため、この手順は非常に重要です。

## 隠しテキストを含む PDF ドキュメントの作成

設定が完了したら、可視テキストと不可視テキストの両方を含む PDF ドキュメントを作成する手順を実行してみましょう。

### ステップ1: ドキュメントディレクトリを定義する
まず、PDF を保存するパスを設定します。ここから魔法が始まります。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; //これをあなたのディレクトリに変更してください
```

この行は、生成されたPDFが保存される場所を定義します。`YOUR DOCUMENT DIRECTORY`実際のパスを使用します。

### ステップ2: PDFドキュメントを作成する
次に、新しい PDF ドキュメントを作成し、それにページを追加してみましょう。

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
```

ここでは、新しいドキュメントを初期化し、テキストフラグメントを配置するページを追加します。

### ステップ3: 表示テキストと非表示テキストを追加する
ここで、表示可能なテキストと非表示のテキストの両方を PDF に追加します。

```csharp
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
```

このスニペットでは、`frag1`表示されますが、`frag2`次は非表示に設定されます。

### ステップ4: テキストを非表示にする
テキストを作成するには`frag2`目に見えない場合は、単に`TextState`.

```csharp
frag2.TextState.Invisible = true;
```

このプロパティを設定すると、`frag2` PDF を表示するときにはレンダリングされません。

### ステップ5: ページにテキストフラグメントを追加する
最後に、これらのテキストフラグメントをページに追加し、PDF を保存します。

```csharp
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

このコード部分は、テキストフラグメントをページに追加します。その後、ドキュメントを適切に保存して破棄します。

## PDF内の隠しテキストの検索

表示テキストと非表示テキストの両方を含む PDF を作成したので、非表示テキストを検索するにはどうすればよいでしょうか。詳しく見ていきましょう。

### ステップ1: PDFドキュメントを読み込む
PDF 内のテキストを検索するには、まず、作成したドキュメントを読み込む必要があります。

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
```

### ステップ2: テキストフラグメント吸収体を作成する
私たちは`TextFragmentAbsorber`PDF 内のすべてのテキスト フラグメントをキャプチャします。

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
```

ここでは、最初のページからすべてのテキストフラグメントを吸収することを指定します。

### ステップ3: フラグメントを反復処理する
これで、収集されたテキスト フラグメントを反復処理して、どのテキスト フラグメントが表示され、どのテキスト フラグメントが非表示になっているかを確認できます。

```csharp
foreach (TextFragment fragment in absorber.TextFragments)
{
    Console.WriteLine("Text '{0}' on pos {1} invisibility: {2}",
        fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
```

このループは各テキストフラグメントをチェックし、その内容と位置および可視性ステータスを出力します。`fragment.TextState.Invisible` true に設定すると、テキストが非表示になります。

### ステップ4: 文書を処分する
最後に、作業が終わったら必ず文書を廃棄してください。

```csharp
doc.Dispose();
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルに隠しテキストを追加および検索する興味深いプロセスを説明しました。表示テキストと隠しテキストの両方を含む PDF ドキュメントを作成する方法と、隠しテキストをプログラムで検索する方法を学びました。この機能は、機密情報を保存する必要がある場合や、ドキュメント内で独自のユーザー エクスペリエンスを提供する必要があるなど、さまざまなアプリケーションで非常に役立ちます。

ASPose.PDF に慣れるにつれて、可能性は無限に広がります。実験を続け、PDF ドキュメントで実現できることの限界を押し広げてください。

## よくある質問

### Aspose.PDF は暗号化された PDF ファイルを処理できますか?  
はい、Aspose.PDF は PDF ドキュメントの暗号化と復号化をサポートしています。パスワードを使用して PDF を簡単に保護できます。

### Aspose.PDF の試用版はありますか?  
もちろんです！無料トライアルはこちらからダウンロードできます[ここ](https://releases.aspose.com/).

### Aspose.PDF はどのようなプログラミング言語をサポートしていますか?  
Aspose.PDF は、C#、Java、Python を含む複数の言語をサポートしています。

### Aspose.PDF のドキュメントはどこにありますか?  
ドキュメントにアクセスできます[ここ](https://reference.aspose.com/pdf/net/).

### 問題が発生した場合、どうすればサポートを受けることができますか?  
サポートについては、Asposeフォーラムをご覧ください。[ここ](https://forum.aspose.com/c/pdf/10).