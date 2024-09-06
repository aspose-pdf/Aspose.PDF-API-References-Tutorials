---
title: PDF ファイルに目次を追加する
linktitle: PDF ファイルに目次を追加する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF に目次を追加する方法を学びます。このステップ バイ ステップ ガイドはプロセスを簡素化し、ドキュメント内でのナビゲーションを容易にします。
type: docs
weight: 40
url: /ja/net/programming-with-document/addtoc/
---
## 導入

長い PDF を延々とスクロールしながら、きちんと整理された目次があればいいのにと思ったことはありませんか? 今日はラッキーな日です! このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルに目次を追加する方法を学びます。複雑なレポート、電子ブック、ビジネス提案書など、どのような文書でも、目次があれば、文書をプロフェッショナルで読みやすい傑作に変身させることができます。

## 前提条件

コードに進む前に、必要なものがすべて揃っていることを確認しましょう。

1. Aspose.PDF for .NET: Aspose.PDFライブラリをダウンロードしてインストールしたことを確認してください。ダウンロードはここから行えます。[ここ](https://releases.aspose.com/pdf/net/).
   
2. 開発環境: マシンに Visual Studio などの .NET 開発環境が設定されていることを確認します。

3. ライセンス: ライセンスをお持ちでない場合は、無料トライアルを取得するか、一時ライセンスをリクエストできます。[ここ](https://purchase.aspose.com/temporary-license/).

## パッケージのインポート

まず、コード ファイルの先頭に必要な名前空間をインポートしてください。方法は次のとおりです。

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

これらの名前空間を使用すると、PDF 固有の機能にアクセスし、ドキュメント内のテキスト要素を操作できます。

このタスクを小さなステップに分割してみましょう。各ステップでは、PDF ドキュメントに目次を作成して挿入するプロセスをガイドします。

## ステップ1: PDFドキュメントを読み込む

最初に行う必要があるのは、目次を追加する既存の PDF ファイルを読み込むことです。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

このステップでは、ドキュメントディレクトリへのパスを指定し、`Document`オブジェクト。必ず置き換えてください`"YOUR DOCUMENT DIRECTORY"`ファイルへの実際のパスを入力します。

## ステップ2: TOC用の新しいページを挿入する

次に、PDF ドキュメントの先頭に新しいページを挿入します。このページには目次が表示されます。

```csharp
Page tocPage = doc.Pages.Insert(1);
```

TOC ページを先頭に挿入することで、読者が PDF で最初に目にするページとして表示されるようになります。

## ステップ3: TOC情報オブジェクトを作成する

次に、目次情報を表すオブジェクトを作成しましょう。また、目次を目立たせるためにタイトルを追加します。

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

ここでは、TOC のタイトルを「Table Of Contents」に設定し、フォント サイズを大きくし、強調するために太字にしました。

## ステップ4: TOC要素を定義する

このステップでは、目次に表示される要素 (または見出し) を定義します。これらの要素は、読者がドキュメントの特定のセクションに移動するのに役立ちます。

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
```

PDF 内のさまざまなページに対応する TOC 項目として機能する文字列の配列を作成しました。

## ステップ5: 目次の見出しを作成する

ここで重要な部分、つまり目次に見出しを追加し、それぞれのページにリンクする作業が始まります。

```csharp
for (int i = 0; i < 2; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);

    heading2.DestinationPage = doc.Pages[i + 2];
    heading2.Top = doc.Pages[i + 2].Rect.Height;
    segment2.Text = titles[i];

    tocPage.Paragraphs.Add(heading2);
}
```

何が起こっているか見てみましょう:
- 見出し: 私たちは`Heading`オブジェクトを追加して`TextSegment`それに。
- リンク先ページ: 各見出しがリンクするページを設定します。
- 上部の位置: 見出しが指すページ上の位置を指定します。
- テキスト: 各見出しは、先ほど作成した配列からそれぞれのタイトルを取得します。

このループは、目次の最初の 2 つの要素の見出しを作成し、それらを対応するページにリンクします。

## ステップ6: TOC付きのPDFを保存する

最後に、すべての TOC 要素を追加したら、更新された PDF を保存します。

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
```

これで、PDF に目次が追加された状態でファイルが保存されました。おめでとうございます。目次が正常に追加されました。

## ステップ7: 確認メッセージ

プロセスが完了したことをユーザーに知らせるために、コンソールに簡単なメッセージを表示します。

```csharp
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

## 結論

これで完了です。Aspose.PDF for .NET を使用すると、PDF に目次を追加するのは簡単なだけでなく、カスタマイズも可能です。シンプルなナビゲーション リンクを作成する必要がある場合でも、複雑な構造を作成する必要がある場合でも、このツールが対応します。次に長い PDF を作成するときは、プロフェッショナルなタッチのために目次を追加することを忘れないでください。

## よくある質問

### Aspose.PDF で TOC の外観をカスタマイズできますか?  
はい、フォント スタイル、サイズ、配置など、目次の外観を完全にカスタマイズできます。

### 目次にサブ見出しを追加するにはどうすればよいですか?  
サブ見出しを追加するには、`Heading`レベル（例：`Heading(2)`) を使用して階層的な目次を作成します。

### ドキュメントが変更された場合に目次を自動的に更新することは可能ですか?  
いいえ、目次は自動的に更新されません。ドキュメント構造が変更された場合は、目次を再作成する必要があります。

### TOC エントリを外部ドキュメントにリンクできますか?  
はい、ハイパーリンクを使用して TOC エントリを外部の PDF または URL にリンクできます。

### Aspose.PDF は複数レベルの目次をサポートしていますか?  
はい、Aspose.PDF はサブセクションを含む複雑なドキュメントの複数レベルの目次をサポートしています。