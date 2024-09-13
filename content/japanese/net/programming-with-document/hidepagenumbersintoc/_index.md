---
title: 目次内のページ番号を非表示にする
linktitle: 目次内のページ番号を非表示にする
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して目次のページ番号を非表示にする方法を学びます。コード例を含むこの詳細なガイドに従って、プロフェッショナルな PDF を作成します。
type: docs
weight: 220
url: /ja/net/programming-with-document/hidepagenumbersintoc/
---
## 導入

PDF を操作しているとき、目次 (TOC) を生成しながらも、ページ番号を非表示にしてすっきりさせたい場合があります。ページ番号がない方がドキュメントの流れがスムーズになる場合もあれば、見た目を優先する場合もあります。理由が何であれ、Aspose.PDF for .NET を使用している場合、このチュートリアルでは TOC でページ番号を非表示にする方法を詳しく説明します。

## 前提条件

始める前に、いくつか準備しておく必要があります。簡単なチェックリストを以下に示します。

- Visual Studio がインストールされている: コーディングするには、動作するバージョンの Visual Studio が必要です。
- Aspose.PDF for .NET ライブラリ: Aspose.PDF for .NET ライブラリがインストールされていることを確認してください。
  - ダウンロードリンク:[Aspose.PDF の .NET 版](https://releases.aspose.com/pdf/net/)
- 一時ライセンス: 機能をテストする場合は、一時ライセンスがあると便利です。
  - 一時ライセンス:[ここから入手](https://purchase.aspose.com/temporary-license/)

## パッケージのインポート

コードに進む前に、C# プロジェクトに次の名前空間をインポートしてください。これらは、PDF ドキュメントの操作と目次 (TOC) の作成に必要なクラスとメソッドを提供します。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

環境の準備が整い、パッケージがインポートされたので、プロセスの各ステップを詳しく説明します。わかりやすくするためにコードのすべての部分をカバーしているので、簡単に理解できます。

## ステップ1: PDFドキュメントを初期化する

最初に行う必要があるのは、新しい PDF ドキュメントを作成し、目次 (TOC) のページを追加することです。


```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
```

- dataDir: 出力ファイルが保存されるディレクトリです。
- Document(): 新しい PDF ドキュメントを初期化します。
- Pages.Add(): ドキュメントに新しい空白ページを追加します。このページには後で目次が保持されます。

## ステップ2: TOC情報とタイトルを設定する

次に、目次の上部に表示されるタイトルの設定など、目次情報を定義します。

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

- TocInfo: このオブジェクトは TOC に関するすべての情報を保持します。
- TextFragment: TOC タイトルのテキストを表します。ここでは「Table Of Contents」として設定します。
- FontStyle: TOC タイトルのサイズを 20 に設定し、太字にしてスタイルを設定します。
- tocPage.TocInfo: TOC を表示するページに TOC 情報を割り当てます。

## ステップ3: 目次のページ番号を非表示にする

さて、ここからが楽しい部分です。ここでは、ページ番号を非表示にするように目次を構成します。

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
```

-  IsShowPageNumbers: これはページ番号を非表示にする魔法のスイッチです。`false`ページ番号は目次に表示されません。
- FormatArrayLength: これを 4 に設定し、4 つのレベルの TOC 見出しの書式設定を定義することを示します。

## ステップ4: TOCのフォーマットをカスタマイズする

TOC にさらにスタイルを追加するために、見出しのさまざまなレベルの書式を定義します。

```csharp
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
```

- FormatArray: この配列は TOC エントリの書式を制御します。各インデックスは異なる見出しレベルを表します。
- 余白とテキスト スタイル: 見出しレベルごとに余白を設定し、太字、斜体、下線などのフォント スタイルを適用します。

## ステップ5: 文書に見出しを追加する

最後に、目次の一部となる実際の見出しを追加しましょう。

```csharp
Page page = doc.Pages.Add();
for (int Level = 1; Level != 5; Level++)
{ 
    Heading heading2 = new Heading(Level); 
    TextSegment segment2 = new TextSegment(); 
    heading2.TocPage = tocPage; 
    heading2.Segments.Add(segment2); 
    heading2.IsAutoSequence = true; 
    segment2.Text = "this is heading of level " + Level; 
    heading2.IsInList = true; 
    page.Paragraphs.Add(heading2); 
}
```

- 見出しとテキスト セグメント: これらは TOC に表示される見出しを表します。各レベルには独自の見出しが割り当てられます。
- IsAutoSequence: 見出しに自動的に番号を付けます。
- IsInList: 各見出しが目次に表示されるようにします。

## ステップ6: ドキュメントを保存する

すべての設定が完了したら、PDF ドキュメントを指定した出力ファイルに保存します。

```csharp
doc.Save(outFile);
```

これで完了です。目次付きの PDF が正常に作成され、ページ番号が非表示になりました。

## 結論

PDF に目次を作成し、ページ番号を非表示にするのは難しそうに思えるかもしれませんが、Aspose.PDF for .NET を使えば簡単です。このステップ バイ ステップ ガイドに従うことで、目次形式をカスタマイズし、ページ番号を非表示にし、見出しにさまざまなスタイルを適用する方法を学習しました。これで、ニーズにぴったり合ったプロフェッショナルな PDF を作成できます。

## よくある質問

### 目次内の特定の見出しのページ番号を表示できますか?
いいえ、Aspose.PDF は目次全体のページ番号を非表示または表示します。特定のエントリに対して選択的にページ番号を非表示にすることはできません。

### TOC にさらにレベルを追加することは可能ですか?
はい、増やすことができます`FormatArrayLength`より多くのレベルの TOC 見出しを定義します。

### すべての TOC エントリのフォントを変更するにはどうすればよいですか?
フォントを変更するには、`TextState.Font`各レベルのプロパティ`FormatArray`.

### TOC にハイパーリンクを挿入できますか?
はい、各目次エントリを文書内の特定のセクションにリンクすることができます。`Heading.TocPage`財産。

### Aspose.PDF にはライセンスが必要ですか?
はい、本番環境での使用には有効なライセンスが必要です。一時ライセンスを取得できます。[ここ](https://purchase.aspose.com/temporary-license/)機能をテストします。