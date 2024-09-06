---
title: 目次内のページ番号を非表示にする
linktitle: 目次内のページ番号を非表示にする
second_title: Aspose.PDF for .NET API リファレンス
description: このステップバイステップ ガイドでは、Aspose.PDF for .NET を使用して目次のページ番号を非表示にする方法を説明します。
type: docs
weight: 220
url: /ja/net/programming-with-document/hidepagenumbersintoc/
---
この記事では、C# を使用して Aspose.PDF for .NET の目次でページ番号を非表示にする機能を実装する方法について説明します。まず Aspose.PDF for .NET について簡単に紹介し、次にこの機能を実装するためのステップ バイ ステップ ガイドに進みます。 

## Aspose.PDF for .NET の紹介

Aspose.PDF for .NET は、開発者がプログラムで PDF ファイルを作成、編集、操作できるようにする強力な PDF 操作コンポーネントです。PDF ドキュメントの操作を容易にする幅広い機能を提供します。Aspose.PDF for .NET は、32 ビットと 64 ビットの両方のオペレーティング システムをサポートし、.NET Framework、.NET Core、および Xamarin プラットフォームで使用できます。 

## TOC 内のページ番号を非表示にする機能とは何ですか?

目次 (TOC) は、ユーザーにコンテンツの概要を素早く提供する PDF ドキュメントの重要な部分です。場合によっては、TOC のページ番号を非表示にして、ユーザー フレンドリにしたい場合があります。Aspose.PDF for .NET には、TOC のページ番号を非表示にする組み込み機能が用意されています。この機能を使用すると、よりユーザー フレンドリな PDF ドキュメントを作成できます。 

## 前提条件

このチュートリアルを実行するには、次のものが必要です。

- Visual Studio 2010 以降
- システムに Aspose.PDF for .NET がインストールされている
- C#プログラミング言語の基礎知識

## 目次でページ番号を非表示にする機能を実装するためのステップバイステップガイド

Aspose.PDF for .NET を使用して TOC でページ番号を非表示にする機能を実装するには、以下の手順に従います。

## ステップ 1: Visual Studio で新しい C# コンソール アプリケーションを作成する

Visual Studio を開き、新しい C# コンソール アプリケーションを作成します。

## ステップ 2: Aspose.PDF for .NET への参照を追加する

プロジェクトの [参照] フォルダーを右クリックし、[参照の追加] を選択します。システム上で Aspose.PDF for .NET がインストールされている場所を参照して、参照を追加します。

## ステップ1: 新しいPDFドキュメントを作成する

次のコードを使用して新しい PDF ドキュメントを作成します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
```

## ステップ2: TOCページを作成する

次のコードを使用して、目次用の新しいページを作成し、それを PDF ドキュメントに追加します。

```csharp
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
```

## ステップ3: PDFドキュメントのセクションコレクションにリストセクションを追加する

次のコードを使用して、PDF ドキュメントのセクション コレクションにリスト セクションを追加します。

```csharp
tocPage.TocInfo = tocInfo;
```

## ステップ4: 4つのレベルリストの形式を定義する

次のコードを使用して、各レベルの左余白とテキスト形式の設定を指定して、4 つのレベルのリストの形式を定義します。

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
```

## ステップ5: セクションに4つの見出しを追加する

```csharp

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
doc.Save(outFile);

```

### Aspose.PDF for .NET を使用して目次でページ番号を非表示にするサンプル ソース コード

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
//PDFドキュメントのセクションコレクションにリストセクションを追加します
tocPage.TocInfo = tocInfo;
//左余白と
//各レベルのテキストフォーマット設定

tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
//セクションに4つの見出しを追加する
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
doc.Save(outFile);
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内の XMP メタデータを操作する方法について説明しました。XMP メタデータは、タイトル、作成者、作成日など、PDF ドキュメントに関する貴重な情報を提供します。Aspose.PDF for .NET を使用すると、開発者はこのメタデータにアクセスして操作することができ、PDF ドキュメントを操作するための柔軟で強力な API が提供されます。

### よくある質問

#### Q: PDF ドキュメント内の XMP メタデータとは何ですか?

A: PDF ドキュメント内の XMP (Extensible Metadata Platform) メタデータは、ドキュメントに関するメタデータ情報を格納するための標準形式です。これには、ドキュメントのタイトル、作成者、作成日、キーワードなどの詳細が含まれます。XMP メタデータは、PDF ドキュメントに関する情報を格納および共有するための構造化された標準化された方法を提供します。

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメントの XMP メタデータを変更できますか?

 A: はい、Aspose.PDF for .NETを使用してPDFドキュメントのXMPメタデータをプログラム的に変更できます。`Info`の財産`Document`オブジェクトを使用すると、XMP メタデータ プロパティにアクセスできます。その後、これらのプロパティの値を更新して、PDF ドキュメントの XMP メタデータを変更できます。

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメントからカスタム XMP メタデータ プロパティを抽出できますか?

 A: はい、Aspose.PDF for .NETを使用してPDFドキュメントからカスタムXMPメタデータプロパティを抽出できます。`Metadata`の財産`Document`オブジェクトは、PDF ドキュメントのすべての XMP メタデータ プロパティへのアクセスを提供します。その後、カスタム プロパティを抽出し、必要に応じてその値を使用できます。