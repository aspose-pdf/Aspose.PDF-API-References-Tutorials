---
title: PDF ファイル内の隠しテキストの追加と検索
linktitle: PDF ファイル内の隠しテキストの追加と検索
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルに隠しテキストを追加および検索するためのステップバイステップ ガイド。
type: docs
weight: 20
url: /ja/net/programming-with-text/add-and-search-hidden-text/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルに隠しテキストを追加および検索する方法を説明します。この操作を簡単に実行するには、次の手順に従ってください。

## 1. 前提条件

始める前に、以下のものがあることを確認してください。

- Visual Studio またはその他の開発環境がインストールされ、構成されている。
- C# プログラミング言語の基本的な知識。
- .NET 用の Aspose.PDF ライブラリがインストールされています。 Aspose公式Webサイトからダウンロードできます。

## 2. 隠し文字を含む PDF ドキュメントの作成

まず、次のコードを使用して、隠しテキストを含む新しい PDF ドキュメントを作成します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//文書を作成する
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
//テキストプロパティを設定 - 非表示
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

PDF ドキュメントの目的のパスとファイル名を必ず指定してください。

## 3. 文書内のテキストを検索する

次に、PDF ドキュメント内の隠しテキストを検索します。次のコードを使用します。

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb.Visit(doc.Pages[1]);
foreach(TextFragment fragment in absorber.TextFragments)
{
//フラグメントを使って何かをする
Console.WriteLine("Text '{0}' at position {1}, invisibility: {2} ",
fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

これにより、PDF ドキュメントの 2 ページ目の隠しテキストが検索され、関連情報が表示されます。

### Aspose.PDF for .NET を使用した隠しテキストの追加と検索のサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//隠しテキストを含む文書を作成する
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
//テキストプロパティを設定 - 非表示
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
//文書内のテキストを検索する
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
foreach (TextFragment fragment in absorber.TextFragments)
{
	//フラグメントを使って何かをする
	Console.WriteLine("Text '{0}' on pos {1} invisibility: {2} ",
	fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

## 結論

おめでとうございます！ Aspose.PDF for .NET を使用して PDF ドキュメントに隠しテキストを追加し、見つけることができました。この方法を独自のプロジェクトに適用して、PDF ファイル内の隠しテキストを操作および検索できるようになりました。

### よくある質問

#### Q: Aspose.PDF for .NET とは何ですか?

A: Aspose.PDF for .NET は、開発者が .NET アプリケーション内で PDF ドキュメントを作成、操作、変換できるようにする堅牢なライブラリです。

#### Q: 隠しテキストを透かしの目的で使用できますか?

A: もちろんです！隠しテキストは、PDF 文書に透かしを入れる効果的な手段として機能し、セキュリティをさらに強化します。

#### Q: PDF ドキュメント内の隠しテキストを表示することはできますか?

A: はい、PDF ドキュメント内の隠しテキストを検索して表示するプロセスは、このチュートリアルで概説した手法を使用して実行できます。

#### Q: Aspose.PDF for .NET は他にどのような機能を提供しますか?

A: Aspose.PDF for .NET は、隠しテキストの操作以外にも、PDF の生成、変換、暗号化などの幅広い機能を提供します。