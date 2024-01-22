---
title: PDF ファイルのフォントを置換する
linktitle: PDF ファイルのフォントを置換する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内のフォントを置換する方法を学びます。
type: docs
weight: 340
url: /ja/net/programming-with-text/replace-fonts/
---
このチュートリアルでは、.NET 用の Aspose.PDF ライブラリを使用して PDF ファイル内の特定のフォントを置換する方法を説明します。 PDF ドキュメントのロード、テキスト断片の検索、置換するフォントの特定、フォントの置換、提供された C# ソース コードを使用した変更された PDF の保存という段階的なプロセスを説明します。

## 前提条件

始める前に、以下のものがあることを確認してください。

- Aspose.PDF for .NET ライブラリがインストールされています。
- C# プログラミングの基本的な理解。

## ステップ 1: ドキュメント ディレクトリを設定する

まず、入力 PDF ファイルがあるディレクトリへのパスを設定する必要があります。交換する`"YOUR DOCUMENT DIRECTORY"`の中に`dataDir`変数を PDF ファイルへのパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: PDF ドキュメントをロードする

次に、次のコマンドを使用して PDF ドキュメントをロードします。`Document` Aspose.PDF ライブラリのクラス。

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## ステップ 3: フォントの検索と置換

私たちは`TextFragmentAbsorber`オブジェクトを編集し、未使用のフォントを削除するように編集オプションを設定します。次に、PDF ドキュメントのすべてのページに対してアブソーバーを受け入れ、テキストの断片を検索します。

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
pdfDocument.Pages.Accept(absorber);
```

## ステップ 4: フォントを置換する

アブソーバーによって識別されたすべてのテキスト断片を調べます。テキストフラグメントのフォント名が、置換する希望のフォントと一致する場合、それを新しいフォントに置き換えます。

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    if (textFragment.TextState.Font.FontName == "Arial,Bold")
    {
        textFragment.TextState.Font = FontRepository.FindFont("Arial");
    }
}
```

## ステップ 5: 変更した PDF を保存する

最後に、変更した PDF ドキュメントを指定した出力ファイルに保存します。

```csharp
dataDir = dataDir + "ReplaceFonts_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nFonts replaced successfully in the PDF document.\nFile saved at " + dataDir);
```

### Aspose.PDF for .NET を使用したフォントの置換のサンプル ソース コード 
```csharp
try
{
	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//ソースPDFファイルをロード
	Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
	//テキストの断片を検索し、未使用のフォントを削除するように編集オプションを設定します
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	//すべてのページに吸収体を受け入れる
	pdfDocument.Pages.Accept(absorber);
	//すべての TextFragment をトラバースする
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		//フォント名が ArialMT の場合は、フォント名を Arial に置き換えます
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

このチュートリアルでは、.NET 用の Aspose.PDF ライブラリを使用して PDF ドキュメント内の特定のフォントを置換する方法を学習しました。ステップバイステップのガイドに従って、提供されている C# コードを実行すると、PDF ドキュメントの読み込み、テキストの断片の検索、特定のフォントの識別と置換、および変更した PDF の保存を行うことができます。

### よくある質問

#### Q: 「PDF ファイルのフォントを置換」チュートリアルの目的は何ですか?

A: 「PDF ファイル内のフォントを置換する」チュートリアルでは、.NET 用の Aspose.PDF ライブラリを使用して PDF ドキュメント内の特定のフォントを置換する方法を示します。 PDF ドキュメントの読み込み、テキストの断片の検索、置換するフォントの特定、フォントの置換、および変更した PDF の保存方法について、段階的なガイドを提供します。

#### Q: PDF ドキュメント内のフォントを置き換える必要があるのはなぜですか?

A: PDF ドキュメント内のフォントの置換は、テキストの外観を標準化する場合、またはさまざまなデバイスやプラットフォーム間でのドキュメントの互換性を向上させる場合に必要になる場合があります。これにより、一貫したタイポグラフィーと書式設定を確保できます。

#### Q: ドキュメント ディレクトリはどのように設定すればよいですか?

A: ドキュメント ディレクトリを設定するには:

1. 交換する`"YOUR DOCUMENT DIRECTORY"`の中に`dataDir`変数には、入力 PDF ファイルが配置されているディレクトリへのパスを指定します。

#### Q: PDF ドキュメント内の特定のフォントを置き換えるにはどうすればよいですか?

A: チュートリアルでは、プロセスを段階的に説明します。

1. 次のコマンドを使用して PDF ドキュメントをロードします。`Document`クラス。
2. を作成します`TextFragmentAbsorber`オブジェクトを編集し、未使用のフォントを削除するように編集オプションを設定します。すべてのページでアブソーバーを受け入れてテキストの断片を検索します。
3. 識別されたテキストの断片をたどります。テキストフラグメントのフォント名が置換したいフォントと一致する場合は、新しいフォントに置き換えます。

####  Q：使用目的は何ですか？`TextFragmentAbsorber` with font replacement options?

 A:`TextFragmentAbsorber`フォント置換オプションを使用すると、テキストの断片を特定し、同時に未使用のフォントを削除できます。これは、置換されたフォントが PDF 内の追加リソースとして追加されないようにするために重要です。

#### Q: 置換する特定のフォントを特定するにはどうすればよいですか?

A: アブソーバによって識別されたテキスト断片をたどることにより、各テキスト断片のフォント情報にアクセスできます。フォント名が置換したいフォントと一致する場合は、置換を実行できます。

#### Q: 置換するフォントがテキストフラグメント内に見つからない場合はどうなりますか?

A: 置換するフォントがテキスト フラグメント内に見つからない場合、テキスト フラグメントのフォントは変更されません。置換はフォント名が一致する場合にのみ行われます。

#### Q: このチュートリアルでのフォントの置換には制限がありますか?

A: このチュートリアルは、テキスト断片内の特定のフォントを置き換えることに焦点を当てています。注釈やフォームフィールドなど、他のコンテキストでフォントを置き換える必要がある場合は、それに応じてアプローチを拡張する必要があります。

#### Q: 提供されたコードを実行すると、どのような結果が期待されますか?

A: チュートリアルに従って、提供されている C# コードを実行すると、PDF ドキュメント内の特定のフォントが置き換えられます。設定した基準によって識別されたフォントは、指定した新しいフォントに置き換えられます。

#### Q: この方法を使用して、PDF ドキュメント全体のフォントを置き換えることはできますか?

A: はい、すべてのテキスト フラグメントを調べてフォント置換ロジックを適用することで、PDF ドキュメント全体のフォントを置換するようにコードを調整できます。