---
title: 目次を追加するときにページ番号をカスタマイズする
linktitle: 目次を追加するときにページ番号をカスタマイズする
second_title: Aspose.PDF for .NET API リファレンス
description: このステップバイステップのガイドとコード例で、Aspose.PDF for .NET を使用して目次 (TOC) を追加しながらページ番号をカスタマイズする方法を学びます。
type: docs
weight: 100
url: /ja/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して目次 (TOC) を追加しながらページ番号をカスタマイズする方法を説明します。これを達成するために、コード例とともに段階的なガイダンスを提供します。

## ステップ 1: 既存の PDF ファイルをロードする

まず、既存の PDF ファイルをロードする必要があります。このチュートリアルでは、「YOUR DOCUMENT DIRECTORY」ディレクトリにあるファイル「42824.pdf」を使用します。このディレクトリ パスをドキュメント ディレクトリへの実際のパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
Document doc = new Document(inFile);
```

## ステップ 2: 目次ページを追加する

次に、目次ページとして機能する新しいページをドキュメントの先頭に追加する必要があります。これを実現するには、`Insert()`の方法`Pages`のコレクション`Document`物体。

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

## ステップ 3: TOC オブジェクトの作成

TOC オブジェクトを作成するには、まず、`TocInfo`オブジェクトを作成し、そのプロパティを設定します。このチュートリアルでは、目次のタイトルを「目次」に、ページ番号の接頭辞を「P」に設定します。

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

## ステップ 4: 目次エントリーの作成

目次エントリを作成するには、目次ページを除くドキュメントのすべてのページをループし、各ページの見出しオブジェクトを作成する必要があります。次に、見出しオブジェクトを目次ページに追加し、その宛先ページを指定します。

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    //見出しオブジェクトの作成
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    //見出しオブジェクトの宛先ページを指定します
    heading2.DestinationPage = doc.Pages[i + 1];
    //宛先ページ
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    //目的地座標
    segment2.Text = "Page " + i.ToString();
    //目次を含むページに見出しを追加する
    tocPage.Paragraphs.Add(heading2);
}
```

## ステップ 5: 更新されたドキュメントを保存する

最後に、更新されたドキュメントを新しいファイルに保存する必要があります。これを実現するには、`Save()`の方法`Document`物体。

```csharp
doc.Save(outFile);
```

### Aspose.PDF for .NET を使用して目次を追加する際にページ番号をカスタマイズするためのソース コードの例

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
//既存の PDF ファイルをロードする
Document doc = new Document(inFile);
//PDF ファイルの最初のページにアクセスする
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
//目次情報を表すオブジェクトを作成する
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
//目次のタイトルを設定します
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
for (int i = 1; i<doc.Pages.Count; i++)
{
	//見出しオブジェクトの作成
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);
	//見出しオブジェクトの宛先ページを指定します
	heading2.DestinationPage = doc.Pages[i + 1];
	//宛先ページ
	heading2.Top = doc.Pages[i + 1].Rect.Height;
	//目的地座標
	segment2.Text = "Page " + i.ToString();
	//目次を含むページに見出しを追加する
	tocPage.Paragraphs.Add(heading2);
}

//更新されたドキュメントを保存する
doc.Save(outFile);
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して目次を追加する際にページ番号をカスタマイズする方法について段階的なガイダンスを提供しました。この機能を実装する際の参考として使用できるコード例も提供しています。

### よくある質問

#### Q: PDF ドキュメントの目次 (TOC) とは何ですか?

A: PDF ドキュメントの目次 (TOC) は、ドキュメントのセクションまたは章の整理されたリストと、対応するページ番号を提供するナビゲーション補助です。これにより、読者はドキュメント内の特定のセクションにすばやく移動できます。

#### Q:目次のページ番号をカスタマイズしたいのはなぜですか?

A: 目次のページ番号をカスタマイズすると、特定のページ番号形式を使用する場合、またはページ番号とともに追加情報を含める場合に便利です。よりパーソナライズされた有益な目次を作成できます。

#### Q: PDF ドキュメント内の特定のセクションまたはページにリンクするハイパーリンクを目次に含めることはできますか?

A: はい、Aspose.PDF for .NET を使用すると、PDF ドキュメント内の特定のセクションまたはページにリンクするハイパーリンクを目次に作成できます。これにより、PDF ドキュメントの対話性とナビゲーションが強化されます。

#### Q: Aspose.PDF for .NET は PDF/A 標準と互換性がありますか?

A: はい、Aspose.PDF for .NET は、PDF/A-1、PDF/A-2、PDF/A-3 などの PDF/A 標準をサポートしています。これにより、アーカイブおよび長期保存の要件に準拠した PDF ドキュメントを作成できます。

#### Q: フォント スタイルや色など、目次エントリにさらに書式設定を追加できますか?

A: はい、Aspose.PDF for .NET を使用して、フォント スタイル、色、フォント サイズなどの追加の書式設定を目次エントリに追加できます。これにより、要件に応じて目次の外観をカスタマイズできます。
