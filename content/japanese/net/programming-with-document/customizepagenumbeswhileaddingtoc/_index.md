---
title: 目次を追加しながらページ番号をカスタマイズする
linktitle: 目次を追加しながらページ番号をカスタマイズする
second_title: Aspose.PDF for .NET API リファレンス
description: この包括的なチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントに目次を追加しながらページ番号をカスタマイズする方法を学習します。
type: docs
weight: 100
url: /ja/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---
## 導入

ドキュメント管理の世界では、PDF が最高です。さまざまなプラットフォーム間でドキュメントを共有および保存するための頼りになる形式です。しかし、目次 (TOC) などの機能を使用して PDF ドキュメントを強化したい場合はどうすればよいでしょうか。ここで Aspose.PDF for .NET が役立ちます。この強力なライブラリを使用すると、開発者は PDF ファイルを簡単に操作でき、コンテンツを簡単に追加、変更、カスタマイズできます。このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントに目次を追加しながらページ番号をカスタマイズする方法について詳しく説明します。では、コーディングの帽子をかぶって、始めましょう。

## 前提条件

コードに進む前に、準備しておくべきことがいくつかあります。

1. Visual Studio: マシンに Visual Studio がインストールされていることを確認します。これが開発環境になります。
2. Aspose.PDF for .NET: Aspose.PDFライブラリをダウンロードしてインストールする必要があります。[ここ](https://releases.aspose.com/pdf/net/).
3. C# の基礎知識: C# プログラミングに精通していると、コード スニペットをよりよく理解できるようになります。
4. サンプル PDF ファイル: 作業に使用できるサンプル PDF ファイルを用意してください。シンプルな PDF ファイルを作成することも、既存の PDF ファイルをダウンロードすることもできます。

## パッケージのインポート

まず、必要なパッケージをインポートする必要があります。Visual Studio プロジェクトを開き、Aspose.PDF ライブラリへの参照を追加します。これは NuGet パッケージ マネージャーを使用して実行できます。

1. ソリューション エクスプローラーでプロジェクトを右クリックします。
2. 「NuGet パッケージの管理」を選択します。
3. 「Aspose.PDF」を検索してインストールします。

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

ライブラリをインストールしたら、コーディングを開始できます。

## ステップ1: ドキュメントディレクトリを設定する

まず最初に、ドキュメント ディレクトリを設定する必要があります。ここに、入力および出力 PDF ファイルを保存します。 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
```

このスニペットでは、`YOUR DOCUMENT DIRECTORY` PDF ファイルが保存されている実際のパスを入力します。これにより、既存の PDF を読み込み、変更したバージョンを保存できるようになります。

## ステップ2: 既存のPDFファイルを読み込む

ドキュメント ディレクトリが設定されたので、既存の PDF ファイルを読み込みます。 

```csharp
Document doc = new Document(inFile);
```

ここで、新しい`Document`入力ファイル パスを渡すことでオブジェクトを作成します。これにより、プログラムで PDF コンテンツを操作できます。

## ステップ3: 目次用の新しいページを挿入する

次に、目次を配置する新しいページを PDF に作成する必要があります。

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

この行は、ドキュメントの先頭に新しいページを挿入します。このページに目次が表示されます。

## ステップ4: TOC情報を作成する

それでは、TOC 情報を表すオブジェクトを作成しましょう。

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

このステップでは、`TocInfo`オブジェクトを作成し、タイトルを「目次」に設定します。フォントサイズとスタイルもカスタマイズします。`PageNumbersPrefix` 「P」に設定され、目次のページ番号の前に付けられます。

## ステップ5: 目次に見出しを追加する

次は楽しい部分です。ドキュメントのページをループして、目次に見出しを追加します。

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    heading2.DestinationPage = doc.Pages[i + 1];
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    segment2.Text = "Page " + i.ToString();
    tocPage.Paragraphs.Add(heading2);
}
```

このループでは、新しい`Heading`各ページのオブジェクト。各見出しの宛先ページを設定し、表示するテキストを指定します。これは「ページ X」で、X はページ番号です。最後に、見出しを TOC ページに追加します。

## ステップ6: 更新されたドキュメントを保存する

必要な見出しをすべて追加したら、更新したドキュメントを保存します。

```csharp
doc.Save(outFile);
```

この行は、TOC が含まれた変更された PDF を保存します。これで、出力ファイルを開いて、カスタマイズされた目次を確認できます。

## 結論

これで完了です。Aspose.PDF for .NET を使用して PDF ドキュメントに目次を追加しながら、ページ番号をカスタマイズできました。この強力なライブラリを使用すると、PDF ファイルの操作が簡単になり、数行のコードでドキュメントを大幅に強化できます。レポート、電子ブック、またはその他の種類の PDF を作成する場合でも、目次があれば読者のナビゲーションが大幅に改善されます。では、何を待っているのですか? Aspose.PDF を使い始めて、今すぐ素晴らしい PDF の作成を始めましょう。

## よくある質問

### Aspose.PDF for .NET とは何ですか?
Aspose.PDF for .NET は、開発者がプログラムによって PDF ドキュメントを作成、操作、変換できるようにするライブラリです。

### Aspose.PDF を無料で使用できますか?
はい、Asposeはライブラリの機能を試すために使用できる無料試用版を提供しています。ダウンロードできます。[ここ](https://releases.aspose.com/).

### Aspose.PDF のサポートを受けるにはどうすればよいですか?
 Asposeフォーラムにアクセスしてサポートを受けることができます[ここ](https://forum.aspose.com/c/pdf/10).

### 一時ライセンスはありますか?
はい、Aspose.PDFの一時ライセンスをリクエストできます。[ここ](https://purchase.aspose.com/temporary-license/).

### Aspose.PDF for .NET はどこで購入できますか?
 Aspose.PDF for .NETを購入できます[ここ](https://purchase.aspose.com/buy).