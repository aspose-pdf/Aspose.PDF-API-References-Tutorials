---
title: テキストを検索してハイパーリンクを追加する
linktitle: テキストを検索してハイパーリンクを追加する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、PDF 内のテキストを検索し、見つかったテキストにハイパーリンクを追加し、変更されたドキュメントを保存する方法を学習します。
type: docs
weight: 450
url: /ja/net/programming-with-text/search-text-and-add-hyperlink/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内の特定のテキストを検索し、見つかったテキストにハイパーリンクを追加し、変更されたドキュメントを保存する方法について説明します。提供されている C# ソース コードでは、プロセスを段階的に示しています。

## 前提条件

チュートリアルを進める前に、次のものを用意してください。

- C# プログラミング言語に関する基本的な知識。
- Aspose.PDF for .NET ライブラリがインストールされています。Aspose Web サイトから入手するか、NuGet を使用してプロジェクトにインストールできます。

## ステップ1: プロジェクトを設定する

まず、好みの統合開発環境 (IDE) で新しい C# プロジェクトを作成し、Aspose.PDF for .NET ライブラリへの参照を追加します。

## ステップ2: 必要な名前空間をインポートする

必要な名前空間をインポートするには、C# ファイルの先頭に次の using ディレクティブを追加します。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## ステップ3: ドキュメントディレクトリへのパスを設定する

ドキュメントディレクトリへのパスを設定するには、`dataDir`変数：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。

## ステップ4: TextFragmentAbsorberを作成する

作成する`TextFragmentAbsorber`入力された検索フレーズのすべてのインスタンスを検索するオブジェクト:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

交換する`"\\d{4}-\\d{4}"`希望する正規表現パターンを使用します。

## ステップ5: 正規表現検索を有効にする

正規表現検索を有効にするには、`TextSearchOptions`吸収体の特性:

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## ステップ6: PDF文書を開いてバインドする

作成する`PdfContentEditor`オブジェクトを作成し、それをソース PDF ファイルにバインドします。

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

交換する`"SearchRegularExpressionPage.pdf"` PDF ファイルの実際の名前を入力します。

## ステップ7: ページの吸収剤を受け入れる

ドキュメントの目的のページの吸収剤を受け入れます。

```csharp
editor.Document.Pages[1].Accept(absorber);
```

交換する`1`希望するページ番号を入力します。

## ステップ8: 見つかったテキストにハイパーリンクを追加する

取得したテキスト フラグメントをループし、それらにハイパーリンクを追加します。

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    //テキストフラグメントの位置に基づいて四角形を作成する
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    //四角形にウェブリンクを追加する
    editor.CreateWebLink(rect, "http://www.aspose.com"、1、System.Drawing.Color.Blue);
}
```

交換する`"http://www.aspose.com"`目的のハイパーリンク URL を入力します。

## ステップ9: 変更したドキュメントを保存して閉じる

変更したドキュメントを保存し、エディターを閉じます。

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

必ず交換してください`"SearchTextAndAddHyperlink_out.pdf"`希望する出力ファイル名を指定します。

### Aspose.PDF for .NET を使用してテキストを検索し、ハイパーリンクを追加するためのサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//入力された検索フレーズのすべてのインスタンスを検索するためのアブソーバーオブジェクトを作成します
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
//正規表現検索を有効にする
absorber.TextSearchOptions = new TextSearchOptions(true);
//ドキュメントを開く
PdfContentEditor editor = new PdfContentEditor();
//ソースPDFファイルをバインドする
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
//ページの吸収剤を受け入れる
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
	editor.CreateWebLink(rect, "http://Www.aspose.com", 1, blue, actionName);
	editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
		(float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

## 結論

おめでとうございます! Aspose.PDF for .NET を使用して、PDF ドキュメント内の特定のテキストを検索し、見つかったテキストにハイパーリンクを追加し、変更したドキュメントを保存する方法を学習しました。このチュートリアルでは、プロジェクトのセットアップから必要なアクションの実行まで、ステップ バイ ステップのガイドを提供しました。これで、このコードを独自の C# プロジェクトに組み込んで、PDF ファイル内のテキストを操作し、ハイパーリンクを追加できるようになりました。

### よくある質問

#### Q: 「テキストの検索とハイパーリンクの追加」チュートリアルの目的は何ですか?

A: 「テキストの検索とハイパーリンクの追加」チュートリアルは、.NET 用の Aspose.PDF ライブラリを使用して PDF ドキュメント内の特定のテキストを検索し、見つかったテキストにハイパーリンクを追加して、変更したドキュメントを保存する方法を示すことを目的としています。このチュートリアルでは、包括的なガイドと C# コード サンプルが提供され、手順を追ってプロセスを説明します。

#### Q: このチュートリアルは、PDF ドキュメント内の特定のテキストにハイパーリンクを追加するのにどのように役立ちますか?

A: このチュートリアルでは、Aspose.PDF ライブラリを使用して PDF ドキュメント内の特定のテキストを検索し、特定したテキストにハイパーリンクを適用し、変更した PDF を保存するプロセスについて説明します。プロジェクトの設定、ドキュメントの読み込み、正規表現検索の有効化、見つかったテキストへのハイパーリンクの追加などの重要な手順について説明します。

#### Q: このチュートリアルを実行するために必要な前提条件は何ですか?

A: 始める前に、C# プログラミング言語の基礎を理解しておく必要があります。また、Aspose.PDF for .NET ライブラリがインストールされている必要があります。このライブラリは、Aspose Web サイトから取得するか、プロジェクトで NuGet を使用してインストールできます。

#### Q: このチュートリアルに従うためにプロジェクトを設定するにはどうすればよいですか?

A: まず、お好みの統合開発環境 (IDE) で新しい C# プロジェクトを作成します。次に、Aspose.PDF for .NET ライブラリへの参照を追加します。これにより、プロジェクトでライブラリの機能を利用できるようになります。

#### Q: このチュートリアルを使用して特定のテキストにハイパーリンクを追加できますか?

A: はい、このチュートリアルでは、PDF ドキュメント内の特定のテキストにハイパーリンクを追加することに特に焦点を当てています。正規表現を使用して目的のテキストを検索して抽出し、テキスト フラグメントに関連付けられたハイパーリンクを作成し、変更した PDF を保存する方法を説明します。

#### Q: 検索するテキストを定義してハイパーリンクを追加するにはどうすればよいですか?

 A: 検索したいテキストを指定してハイパーリンクを追加するには、`TextFragmentAbsorber`オブジェクトを作成し、そのパターンを`Text`パラメータ。デフォルトのパターンを置き換えます`"\\d{4}-\\d{4}"`チュートリアルのコードに、希望する正規表現パターンを入力します。

#### Q: テキストの正規表現検索を有効にするにはどうすればいいですか?

 A: 正規表現検索は、`TextSearchOptions`オブジェクトとその値を設定する`true`このオブジェクトを`TextSearchOptions`の財産`TextFragmentAbsorber`インスタンス。これにより、テキスト検索中に正規表現パターンが適用されるようになります。

#### Q: 見つかったテキストにハイパーリンクを追加するにはどうすればよいですか?

 A: テキストの断片を`TextFragmentAbsorber`チュートリアルでは、これらのフラグメントを反復処理するループを提供します。各テキストフラグメントについて、チュートリアルではテキストの色を青に設定し、`CreateWebLink`方法。

#### Q: ハイパーリンクを含む変更された PDF を保存する手順は何ですか?

 A: 目的のテキストフラグメントにハイパーリンクを追加した後、`PdfContentEditor`クラスを使用して、変更したドキュメントを保存します。チュートリアルのサンプル コードでは、編集した PDF を保存し、エディターを閉じて、成功メッセージを表示する方法を示します。