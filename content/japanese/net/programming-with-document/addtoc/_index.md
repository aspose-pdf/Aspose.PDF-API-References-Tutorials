---
title: PDF ファイルに目次を追加
linktitle: PDF ファイルに目次を追加
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルに目次を追加する方法を学びます。ソースコードの例を含むステップバイステップのガイド。ドキュメントのナビゲーションを強化します。
type: docs
weight: 40
url: /ja/net/programming-with-document/addtoc/
---
このチュートリアルでは、Aspose.PDF for .NET の PDF ファイルへの TOC (目次) の追加機能を使用して、PDF ドキュメントに目次を追加する方法を説明します。ステップバイステップのガイドを提供し、これを実現するために必要な C# ソース コードについて説明します。このチュートリアルを完了すると、Aspose.PDF for .NET を使用して目次を含む PDF ドキュメントを生成できるようになります。


## ステップ 1: 既存の PDF ファイルをロードする

まず、既存の PDF ファイルをロードする必要があります。交換する`"YOUR DOCUMENT DIRECTORY"`次のコードでは、PDF ファイルへの実際のパスを指定します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

## ステップ 2: 目次用の新しいページを作成する

目次を保持する新しいページを作成します。次のコードは、インデックス 1 に新しいページを挿入します。

```csharp
Page tocPage = doc.Pages.Insert(1);
```

## ステップ 3: 目次情報を定義する

次に、目次情報を定義する必要があります。目次のタイトルやその他のプロパティを設定します。次のコードを追加します。

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

## ステップ 4: 目次要素を作成する

次に、目次の要素を作成します。このチュートリアルでは、異なるページに対応する 4 つの目次要素を作成します。要件に応じて次のコードを変更します。

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";

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

## ステップ 5: 更新されたドキュメントを保存する

最後に、変更したドキュメントを目次とともに保存する必要があります。交換する`"YOUR DOCUMENT DIRECTORY"`以下のコードで、目的の出力ファイルのパスを指定します。

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

### Aspose.PDF for .NET を使用して PDF ドキュメントに目次を追加するためのソース コードの例

```csharp

//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//既存の PDF ファイルをロードする
Document doc = new Document(dataDir + "AddTOC.pdf");

//PDF ファイルの最初のページにアクセスする
Page tocPage = doc.Pages.Insert(1);

//目次情報を表すオブジェクトを作成する
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

//目次のタイトルを設定します
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;

//TOC要素として使用される文字列オブジェクトを作成します。
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
for (int i = 0; i < 2; i++)
{
	//見出しオブジェクトの作成
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);

	//見出しオブジェクトの宛先ページを指定します
	heading2.DestinationPage = doc.Pages[i + 2];

	//宛先ページ
	heading2.Top = doc.Pages[i + 2].Rect.Height;

	//目的地座標
	segment2.Text = titles[i];

	//目次を含むページに見出しを追加する
	tocPage.Paragraphs.Add(heading2);
}
dataDir = dataDir + "TOC_out.pdf";
//更新されたドキュメントを保存する
doc.Save(dataDir);

Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントに目次 (TOC) を追加する方法を検討しました。ステップバイステップのガイドに従い、提供されている C# ソース コードを利用することで、目次を含む PDF ドキュメントを簡単に生成できます。目次によりドキュメントの使いやすさが向上し、ユーザーが特定のセクションやページに効率的に移動できるようになります。 Aspose.PDF for .NET は、.NET アプリケーションで PDF ファイルを操作するための堅牢で使いやすいソリューションを提供し、動的でインタラクティブな PDF ドキュメントを簡単に作成できるようにします。

### PDF ファイルへの目次の追加に関する FAQ

#### Q: Aspose.PDF for .NET とは何ですか?

A: Aspose.PDF for .NET は、開発者が .NET アプリケーションで PDF ファイルを効果的に操作できるようにする強力なライブラリです。 PDF ドキュメントをプログラムで作成、操作、管理するための幅広い機能を提供します。

#### Q: PDF ドキュメントに目次 (TOC) を追加する目的は何ですか?

A: 目次 (TOC) はユーザーにナビゲーション補助を提供し、PDF ドキュメント内の特定のセクションやページにすばやくジャンプできるようにします。ドキュメントの使いやすさとユーザー エクスペリエンスが向上します。

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメントに目次を追加するにはどうすればよいですか?

A: Aspose.PDF for .NET を使用して PDF ドキュメントに目次を追加するには、目次を保持する新しいページを作成し、目次情報を定義してから、特定のページに対応する目次要素を作成する必要があります。ドキュメント内のセクション。

#### Q: 目次の外観をカスタマイズできますか?

A: はい、フォント サイズ、フォント スタイル、配置などの目次要素のさまざまなプロパティを設定することで、目次の外観をカスタマイズできます。 Aspose.PDF for .NET は、目的のルック アンド フィールに合わせて目次を柔軟に設計できます。

#### Q: Aspose.PDF for .NET は、PDF ドキュメントに高度な機能を追加するのに適していますか?

A: もちろん、Aspose.PDF for .NET は、インタラクティブな要素、フォーム フィールド、デジタル署名などの高度な機能を PDF ドキュメントに追加できる機能豊富なライブラリです。