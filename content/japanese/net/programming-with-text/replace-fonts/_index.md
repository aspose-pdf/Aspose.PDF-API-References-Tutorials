---
title: PDF ファイル内のフォントを置き換える
linktitle: PDF ファイル内のフォントを置き換える
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内のフォントを置き換える方法を学習します。
type: docs
weight: 340
url: /ja/net/programming-with-text/replace-fonts/
---
このチュートリアルでは、.NET 用の Aspose.PDF ライブラリを使用して PDF ファイル内の特定のフォントを置き換える方法について説明します。提供されている C# ソース コードを使用して、PDF ドキュメントの読み込み、テキスト フラグメントの検索、置き換えるフォントの識別、フォントの置き換え、変更された PDF の保存というプロセスを段階的に実行します。

## 前提条件

始める前に、次のものがあることを確認してください。

- Aspose.PDF for .NET ライブラリがインストールされました。
- C# プログラミングの基本的な理解。

## ステップ1: ドキュメントディレクトリを設定する

まず、入力PDFファイルがあるディレクトリへのパスを設定する必要があります。`"YOUR DOCUMENT DIRECTORY"`の`dataDir` PDF ファイルへのパスを含む変数。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ2: PDFドキュメントを読み込む

次に、PDF文書を読み込み、`Document` Aspose.PDF ライブラリのクラス。

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## ステップ3: フォントの検索と置換

私たちは`TextFragmentAbsorber`オブジェクトを選択し、未使用のフォントを削除する編集オプションを設定します。次に、PDF ドキュメントのすべてのページのアブソーバーを受け入れて、テキストの断片を検索します。

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
pdfDocument.Pages.Accept(absorber);
```

## ステップ4: フォントを置き換える

アブソーバーによって識別されたすべてのテキスト フラグメントを走査します。テキスト フラグメントのフォント名が置換するフォントと一致する場合は、新しいフォントに置き換えます。

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    if (textFragment.TextState.Font.FontName == "Arial,Bold")
    {
        textFragment.TextState.Font = FontRepository.FindFont("Arial");
    }
}
```

## ステップ5: 変更したPDFを保存する

最後に、変更された PDF ドキュメントを指定された出力ファイルに保存します。

```csharp
dataDir = dataDir + "ReplaceFonts_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nFonts replaced successfully in the PDF document.\nFile saved at " + dataDir);
```

### Aspose.PDF for .NET を使用してフォントを置換するためのサンプル ソース コード 
```csharp
try
{
	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//ソースPDFファイルを読み込む
	Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
	//テキストの断片を検索し、編集オプションを未使用のフォントを削除するように設定します
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	//すべてのページの吸収剤を受け入れる
	pdfDocument.Pages.Accept(absorber);
	//すべてのTextFragmentsを走査する
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		//フォント名がArialMTの場合は、フォント名をArialに置き換えます。
		if (textFragment.TextState.Font.FontName == "Arial,Bold")
		{
			textFragment.TextState.Font = FontRepository.FindFont("Arial");
		}
	}
	dataDir = dataDir + "ReplaceFonts_out.pdf";
	//更新されたドキュメントを保存する
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nFonts replaced successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http://www.aspose.com/purchase/default.aspx.");
}
```

## 結論

このチュートリアルでは、.NET 用の Aspose.PDF ライブラリを使用して PDF ドキュメント内の特定のフォントを置き換える方法を学習しました。ステップ バイ ステップ ガイドに従って提供されている C# コードを実行すると、PDF ドキュメントを読み込み、テキスト フラグメントを検索し、特定のフォントを識別して置き換え、変更した PDF を保存できます。

### よくある質問

#### Q: 「PDF ファイル内のフォントの置換」チュートリアルの目的は何ですか?

A: 「PDF ファイル内のフォントの置換」チュートリアルでは、.NET 用の Aspose.PDF ライブラリを使用して PDF ドキュメント内の特定のフォントを置換する方法を説明します。PDF ドキュメントの読み込み、テキスト フラグメントの検索、置換するフォントの特定、フォントの置換、変更した PDF の保存方法について、ステップ バイ ステップ ガイドを提供します。

#### Q: PDF ドキュメント内のフォントを置き換える必要があるのはなぜですか?

A: テキストの外観を標準化したり、さまざまなデバイスやプラットフォーム間でのドキュメントの互換性を向上させたりする必要がある場合は、PDF ドキュメント内のフォントを置き換える必要があります。これにより、一貫したタイポグラフィと書式設定を確保できます。

#### Q: ドキュメント ディレクトリを設定するにはどうすればよいですか?

A: ドキュメントディレクトリを設定するには:

1. 交換する`"YOUR DOCUMENT DIRECTORY"`の`dataDir`入力 PDF ファイルが配置されているディレクトリへのパスを持つ変数。

#### Q: PDF ドキュメント内の特定のフォントを置き換えるにはどうすればよいですか?

A: チュートリアルでは、プロセスを段階的に説明します。

1.  PDF文書を読み込むには、`Document`クラス。
2. 作成する`TextFragmentAbsorber`オブジェクトを選択し、未使用のフォントを削除する編集オプションを設定します。すべてのページのアブソーバーを受け入れて、テキストの断片を検索します。
3. 識別されたテキスト フラグメントを走査します。テキスト フラグメントのフォント名が置換するフォントと一致する場合は、新しいフォントに置き換えます。

####  Q: 使用目的は何ですか？`TextFragmentAbsorber` with font replacement options?

 A:`TextFragmentAbsorber`フォント置換オプションを使用すると、テキストの断片を見つけると同時に、未使用のフォントを削除できます。これは、置換されたフォントが PDF 内の追加リソースとして追加されないようにするために重要です。

#### Q: 置き換えるフォントを特定するにはどうすればよいですか?

A: アブソーバーによって識別されたテキストフラグメントをトラバースすることで、各テキストフラグメントのフォント情報にアクセスできます。フォント名が置換するフォントと一致する場合は、置換を実行できます。

#### Q: 置換するフォントがテキスト フラグメント内に見つからない場合はどうなりますか?

A: 置換するフォントがテキスト フラグメント内に見つからない場合、テキスト フラグメントのフォントは変更されません。置換はフォント名が一致する場合にのみ行われます。

#### Q: このチュートリアルでフォントを置き換える際に制限はありますか?

A: このチュートリアルでは、テキスト フラグメント内の特定のフォントを置き換えることに焦点を当てています。注釈やフォーム フィールドなど、他のコンテキストでフォントを置き換える必要がある場合は、それに応じてアプローチを拡張する必要があります。

#### Q: 提供されたコードを実行すると、どのような結果が期待されますか?

A: チュートリアルに従って、提供されている C# コードを実行すると、PDF ドキュメント内の特定のフォントが置き換えられます。設定した基準によって識別されたフォントは、指定した新しいフォントに置き換えられます。

#### Q: この方法を使用して、PDF ドキュメント全体のフォントを置き換えることはできますか?

A: はい、すべてのテキストフラグメントを走査し、フォント置換ロジックを適用することで、PDF ドキュメント全体のフォントを置換するようにコードを適応させることができます。