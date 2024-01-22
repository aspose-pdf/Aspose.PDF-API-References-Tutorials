---
title: テキストを検索してハイパーリンクを追加
linktitle: テキストを検索してハイパーリンクを追加
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、PDF 内のテキストを検索し、見つかったテキストにハイパーリンクを追加し、変更したドキュメントを保存する方法を学びます。
type: docs
weight: 450
url: /ja/net/programming-with-text/search-text-and-add-hyperlink/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内の特定のテキストを検索し、見つかったテキストにハイパーリンクを追加し、変更したドキュメントを保存する方法について説明します。提供されている C# ソース コードは、プロセスを段階的に示しています。

## 前提条件

チュートリアルを進める前に、次のものが揃っていることを確認してください。

- C# プログラミング言語の基本的な知識。
- Aspose.PDF for .NET ライブラリがインストールされています。 Aspose Web サイトから入手するか、NuGet を使用してプロジェクトにインストールできます。

## ステップ 1: プロジェクトをセットアップする

まず、好みの統合開発環境 (IDE) で新しい C# プロジェクトを作成し、Aspose.PDF for .NET ライブラリへの参照を追加します。

## ステップ 2: 必要な名前空間をインポートする

C# ファイルの先頭に次の using ディレクティブを追加して、必要な名前空間をインポートします。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## ステップ 3: ドキュメント ディレクトリへのパスを設定する

を使用してドキュメント ディレクトリへのパスを設定します。`dataDir`変数：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを置き換えます。

## ステップ 4: TextFragmentAbsorber を作成する

を作成します`TextFragmentAbsorber`オブジェクトを使用して、入力検索フレーズのすべてのインスタンスを検索します。

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

交換する`"\\d{4}-\\d{4}"`希望の正規表現パターンを使用します。

## ステップ 5: 正規表現検索を有効にする

を設定して正規表現検索を有効にします。`TextSearchOptions`吸収体の特性:

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## ステップ 6: PDF ドキュメントを開いてバインドします。

を作成します`PdfContentEditor`オブジェクトを取得し、ソース PDF ファイルにバインドします。

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

交換する`"SearchRegularExpressionPage.pdf"` PDF ファイルの実際の名前を付けます。

## ステップ 7: ページのアブソーバーを受け入れる

ドキュメントの目的のページの吸収体を受け入れます。

```csharp
editor.Document.Pages[1].Accept(absorber);
```

交換する`1`希望のページ番号を付けてください。

## ステップ 8: 見つかったテキストにハイパーリンクを追加する

取得したテキストの断片をループし、それらにハイパーリンクを追加します。

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    //テキストフラグメントの位置に基づいて長方形を作成します
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    //四角形に Web リンクを追加します
    editor.CreateWebLink(rect, "http://www.aspose.com"、1、System.Drawing.Color.Blue);
}
```

交換する`"http://www.aspose.com"`目的のハイパーリンク URL を使用します。

## ステップ 9: 変更したドキュメントを保存して閉じる

変更したドキュメントを保存し、エディタを閉じます。

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

必ず交換してください`"SearchTextAndAddHyperlink_out.pdf"`希望の出力ファイル名を付けます。

### Aspose.PDF for .NET を使用したテキストの検索とハイパーリンクの追加のサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//入力検索フレーズのすべてのインスタンスを検索するアブソーバー オブジェクトを作成します。
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
//正規表現検索を有効にする
absorber.TextSearchOptions = new TextSearchOptions(true);
//開いた文書
PdfContentEditor editor = new PdfContentEditor();
//ソース PDF ファイルをバインドする
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
//ページのアブソーバーを受け入れる
editor.Document.Pages[1].Accept(absorber);
int[] dashArray = { };
String[] LEArray = { };
System.Drawing.Color blue = System.Drawing.Color.Blue;
//フラグメントをループする
foreach (TextFragment textFragment in absorber.TextFragments)
{
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
		(int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
		(int)Math.Round(textFragment.Rectangle.Height + 1));
	Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
	editor.CreateWebLink(rect, "http://www.aspose.com"、1、青、アクション名);
	editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
		(float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

## 結論

おめでとう！ Aspose.PDF for .NET を使用して、PDF ドキュメント内の特定のテキストを検索し、見つかったテキストにハイパーリンクを追加し、変更されたドキュメントを保存する方法を学習しました。このチュートリアルでは、プロジェクトのセットアップから必要なアクションの実行までのステップバイステップのガイドを提供しました。このコードを独自の C# プロジェクトに組み込んで、テキストを操作したり、PDF ファイルにハイパーリンクを追加したりできるようになりました。

### よくある質問

#### Q: 「テキストの検索とハイパーリンクの追加」チュートリアルの目的は何ですか?

A: 「テキストの検索とハイパーリンクの追加」チュートリアルは、.NET 用の Aspose.PDF ライブラリを使用して PDF ドキュメント内の特定のテキストを検索し、見つかったテキストにハイパーリンクを追加して、変更したドキュメントを保存する方法を示すことを目的としています。このチュートリアルでは、段階的なプロセスを説明するための包括的なガイドと C# コード サンプルを提供します。

#### Q: このチュートリアルは、PDF ドキュメント内の特定のテキストにハイパーリンクを追加する際にどのように役立ちますか?

A: このチュートリアルでは、Aspose.PDF ライブラリを使用して PDF ドキュメント内の特定のテキストを検索し、特定されたテキストにハイパーリンクを適用し、変更された PDF を保存するプロセスを説明します。プロジェクトの設定、ドキュメントのロード、正規表現検索の有効化、見つかったテキストへのハイパーリンクの追加などの重要な手順について説明します。

#### Q: このチュートリアルを進めるにはどのような前提条件が必要ですか?

A: 始める前に、C# プログラミング言語の基本を理解しておく必要があります。さらに、Aspose.PDF for .NET ライブラリをインストールする必要があります。これは、Aspose Web サイトから入手するか、プロジェクトで NuGet を使用してインストールできます。

#### Q: このチュートリアルに従うようにプロジェクトを設定するにはどうすればよいですか?

A: まず、好みの統合開発環境 (IDE) で新しい C# プロジェクトを作成します。次に、Aspose.PDF for .NET ライブラリへの参照を追加します。これにより、プロジェクトでライブラリの機能を利用できるようになります。

#### Q: このチュートリアルを使用して特定のテキストにハイパーリンクを追加できますか?

A: はい、このチュートリアルでは、PDF ドキュメント内の特定のテキストにハイパーリンクを追加することに特に焦点を当てています。正規表現を使用して目的のテキストを検索して抽出し、テキストの断片に関連付けられたハイパーリンクを作成し、変更した PDF を保存する方法を示します。

#### Q: 検索してハイパーリンクを追加するテキストを定義するにはどうすればよいですか?

 A: 検索したいテキストを指定してハイパーリンクを追加するには、`TextFragmentAbsorber`オブジェクトを作成し、`Text`パラメータ。デフォルトのパターンを置き換える`"\\d{4}-\\d{4}"`チュートリアルのコード内で、必要な正規表現パターンを使用します。

#### Q: テキストの正規表現検索を有効にするにはどうすればよいですか?

 A: 正規表現検索は、`TextSearchOptions`オブジェクトを作成し、その値を`true`。このオブジェクトを`TextSearchOptions`の財産`TextFragmentAbsorber`実例。これにより、テキスト検索中に正規表現パターンが確実に適用されます。

#### Q: 見つかったテキストにハイパーリンクを追加するにはどうすればよいですか?

 A: を使用してテキストの断片を識別した後、`TextFragmentAbsorber` 、チュートリアルでは、これらのフラグメントを反復処理するループが提供されます。このチュートリアルでは、各テキスト フラグメントについて、テキストの色を青に設定し、`CreateWebLink`方法。

#### Q: 変更した PDF をハイパーリンク付きで保存するにはどうすればよいですか?

 A: 目的のテキスト部分にハイパーリンクを追加した後、`PdfContentEditor`変更されたドキュメントを保存するクラス。チュートリアルのサンプル コードでは、編集した PDF を保存し、エディタを閉じ、成功メッセージを表示する方法を示します。