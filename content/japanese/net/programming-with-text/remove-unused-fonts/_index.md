---
title: PDF ファイル内の未使用フォントを削除する
linktitle: PDF ファイル内の未使用フォントを削除する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内の未使用のフォントを削除する方法を学習します。
type: docs
weight: 300
url: /ja/net/programming-with-text/remove-unused-fonts/
---
このチュートリアルでは、.NET 用の Aspose.PDF ライブラリを使用して PDF ファイル内の未使用フォントを削除する方法について説明します。提供されている C# ソース コードを使用して、PDF を読み込み、未使用フォントを識別して削除し、更新された PDF を保存するプロセスを段階的に説明します。

## 要件

始める前に、次のものがあることを確認してください。

- Aspose.PDF for .NET ライブラリがインストールされました。
- C# プログラミングの基本的な理解。

## ステップ1: ドキュメントディレクトリを設定する

まず、PDFファイルが保存されているディレクトリへのパスを設定する必要があります。`"YOUR DOCUMENT DIRECTORY"`の`dataDir` PDF ファイルへのパスを含む変数。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ2: ソースPDFを読み込む

次に、ソースPDF文書を読み込み、`Document` Aspose.PDF ライブラリのクラス。

```csharp
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## ステップ3: 使用されていないフォントを特定して削除する

私たちは`TextFragmentAbsorber`オブジェクト`TextEditOptions`パラメータ設定`TextEditOptions.FontReplace.RemoveUnusedFonts`このオプションを使用すると、PDF文書内の未使用のフォントを識別して削除できます。次に、`TextFragments`フォントを希望のフォントに設定します。

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## ステップ4: 更新されたPDFを保存する

最後に、更新された PDF ドキュメントを指定された出力ファイルに保存します。

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from the PDF document.\nFile saved at " + dataDir);
```

### Aspose.PDF for .NET を使用して未使用フォントを削除するためのサンプル ソース コード 
```csharp
try
{
	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//ソースPDFファイルを読み込む
	Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	doc.Pages.Accept(absorber);
	//すべてのTextFragmentsを反復処理する
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
	}
	dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
	//更新されたドキュメントを保存する
	doc.Save(dataDir);
	Console.WriteLine("\nUnused fonts removed successfully from pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http://www.aspose.com/purchase/default.aspx.");
}
```

## 結論

このチュートリアルでは、.NET 用の Aspose.PDF ライブラリを使用して、PDF ドキュメントから未使用のフォントを削除する方法を学習しました。ステップ バイ ステップ ガイドに従って、提供されている C# コードを実行すると、PDF を読み込み、未使用のフォントを識別して削除し、更新された PDF を保存できます。

### よくある質問

#### Q: 「PDF ファイル内の未使用フォントを削除する」チュートリアルの目的は何ですか?

A: 「PDF ファイル内の未使用フォントの削除」チュートリアルでは、.NET 用の Aspose.PDF ライブラリを使用して PDF ドキュメントから未使用フォントを削除する方法について説明します。このチュートリアルでは、PDF を読み込み、未使用フォントを識別して削除し、更新された PDF を保存するプロセスについて説明します。

#### Q: PDF ドキュメントから未使用のフォントを削除するのはなぜですか?

A: PDF ドキュメントから未使用のフォントを削除すると、ファイル サイズが小さくなり、ドキュメントが最適化されてパフォーマンスが向上します。これは、ドキュメントの内容で実際には使用されていない埋め込みフォントを含む PDF を処理する場合に特に便利です。

#### Q: ドキュメント ディレクトリを設定するにはどうすればよいですか?

A: ドキュメントディレクトリを設定するには:

1. 交換する`"YOUR DOCUMENT DIRECTORY"`の`dataDir` PDF ファイルが保存されているディレクトリへのパスを持つ変数。

#### Q: Aspose.PDF ライブラリを使用して PDF ドキュメントから未使用のフォントを削除するにはどうすればよいですか?

A: チュートリアルでは、プロセスを段階的に説明します。

1.  PDF文書を開くには、`Document`クラス。
2. 作成する`TextFragmentAbsorber`オブジェクト`TextEditOptions`に設定`FontReplace.RemoveUnusedFonts`.
3. アブソーバーを受け入れて、未使用のフォントを識別し、PDF から削除します。
4. すべてを繰り返す`TextFragments`フォントを希望のフォントに設定します。
5. 更新された PDF ドキュメントを保存します。

####  Q: の目的は何ですか？`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter?

 A:`TextEditOptions.FontReplace.RemoveUnusedFonts`パラメータは、`TextFragmentAbsorber`PDF ドキュメントから未使用のフォントを識別して削除します。

#### Q: 使用していないフォントを自分の好きなフォントに置き換えることはできますか?

A: はい、コードを変更して、未使用のフォントを任意のフォントに置き換えることができます。提供されているサンプル コードでは、フォント「Arial、Bold」が代替として使用されています。

####  Q:`TextFragmentAbsorber` work to remove unused fonts?

 A:`TextFragmentAbsorber`は、`TextEditOptions.FontReplace.RemoveUnusedFonts`パラメータはPDFのテキストフラグメント内の未使用フォントを識別する。吸収後、`TextFragments`フォントを希望の置換フォントに設定します。

#### Q: 提供されたコードを実行すると、どのような結果が期待されますか?

A: チュートリアルに従って提供されている C# コードを実行すると、入力 PDF ドキュメントから未使用のフォントが削除され、更新されたバージョンが出力 PDF ファイルとして保存されます。

#### Q: 特定のページまたは領域からのみフォントを削除するようにコードを変更することはできますか?

A: 提供されているコードは、PDF ドキュメント全体から未使用のフォントを削除することに重点を置いています。特定のページまたは領域を対象にフォントを削除する場合は、アプローチを変更し、より複雑なロジックを使用してそれらの領域で未使用のフォントを識別する必要があります。