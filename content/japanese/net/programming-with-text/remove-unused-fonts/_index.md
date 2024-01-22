---
title: PDF ファイル内の使用されていないフォントを削除する
linktitle: PDF ファイル内の使用されていないフォントを削除する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内の未使用のフォントを削除する方法を学びます。
type: docs
weight: 300
url: /ja/net/programming-with-text/remove-unused-fonts/
---
このチュートリアルでは、.NET 用の Aspose.PDF ライブラリを使用して PDF ファイル内の未使用のフォントを削除する方法を説明します。 PDF の読み込み、未使用のフォントの特定と削除、提供された C# ソース コードを使用した更新された PDF の保存のプロセスを段階的に説明します。

## 要件

始める前に、以下のものがあることを確認してください。

- Aspose.PDF for .NET ライブラリがインストールされています。
- C# プログラミングの基本的な理解。

## ステップ 1: ドキュメント ディレクトリを設定する

まず、PDF ファイルが配置されているディレクトリへのパスを設定する必要があります。交換する`"YOUR DOCUMENT DIRECTORY"`の中に`dataDir`変数を PDF ファイルへのパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: ソース PDF をロードする

次に、次のコマンドを使用してソース PDF ドキュメントをロードします。`Document` Aspose.PDF ライブラリのクラス。

```csharp
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## ステップ 3: 未使用のフォントを特定して削除する

私たちは`TextFragmentAbsorber`オブジェクトを使用して`TextEditOptions`パラメータを次のように設定`TextEditOptions.FontReplace.RemoveUnusedFonts`。このオプションを使用すると、PDF ドキュメント内の未使用のフォントを特定して削除できます。次に、すべての処理を繰り返します。`TextFragments`を選択し、フォントを希望のフォントに設定します。

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## ステップ 4: 更新された PDF を保存する

最後に、更新された PDF ドキュメントを指定した出力ファイルに保存します。

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from the PDF document.\nFile saved at " + dataDir);
```

### Aspose.PDF for .NET を使用して未使用のフォントを削除するためのサンプル ソース コード 
```csharp
try
{
	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//ソースPDFファイルをロード
	Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	doc.Pages.Accept(absorber);
	//すべての TextFragment を反復処理します。
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

このチュートリアルでは、.NET 用の Aspose.PDF ライブラリを使用して、PDF ドキュメントから未使用のフォントを削除する方法を学習しました。ステップバイステップのガイドに従って、提供されている C# コードを実行すると、PDF をロードし、未使用のフォントを特定して削除し、更新された PDF を保存できます。

### よくある質問

#### Q: 「PDF ファイル内の使用されていないフォントを削除する」チュートリアルの目的は何ですか?

A: 「PDF ファイル内の使用されていないフォントを削除する」チュートリアルでは、.NET 用の Aspose.PDF ライブラリを使用して PDF ドキュメントから使用されていないフォントを削除する方法について説明しています。このチュートリアルでは、PDF の読み込み、未使用のフォントの特定と削除、更新された PDF の保存のプロセスを説明します。

#### Q: PDF ドキュメントから未使用のフォントを削除する必要があるのはなぜですか?

A: PDF ドキュメントから未使用のフォントを削除すると、ファイル サイズが削減され、ドキュメントが最適化されてパフォーマンスが向上します。これは、ドキュメントのコンテンツで実際には使用されていない埋め込みフォントを含む PDF を扱う場合に特に便利です。

#### Q: ドキュメント ディレクトリはどのように設定すればよいですか?

A: ドキュメント ディレクトリを設定するには:

1. 交換する`"YOUR DOCUMENT DIRECTORY"`の中に`dataDir`変数には、PDF ファイルが置かれているディレクトリへのパスを指定します。

#### Q: Aspose.PDF ライブラリを使用して PDF ドキュメントから未使用のフォントを削除するにはどうすればよいですか?

A: チュートリアルでは、プロセスを段階的に説明します。

1. を使用して PDF ドキュメントを開きます。`Document`クラス。
2. を作成します`TextFragmentAbsorber`オブジェクト`TextEditOptions`に設定`FontReplace.RemoveUnusedFonts`.
3. 吸収機能を受け入れて、PDF から未使用のフォントを特定して削除します。
4. すべてを反復処理する`TextFragments`を選択し、フォントを希望のフォントに設定します。
5. 更新された PDF ドキュメントを保存します。

####  Q：その目的は何ですか？`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter?

 A:`TextEditOptions.FontReplace.RemoveUnusedFonts`パラメータは、`TextFragmentAbsorber`未使用のフォントを特定し、PDF ドキュメントから削除します。

#### Q: 使用していないフォントを自分の選択したフォントに置き換えることはできますか?

A: はい、コードを変更して、未使用のフォントを選択したフォントに置き換えることができます。提供されているサンプルコードでは、フォント「Arial, Bold」が代替として使用されています。

####  Q: どうやって`TextFragmentAbsorber` work to remove unused fonts?

 A:`TextFragmentAbsorber`で構成されています`TextEditOptions.FontReplace.RemoveUnusedFonts`パラメータ。PDF のテキスト断片内の未使用のフォントを識別します。吸収後は、次のように繰り返すことができます。`TextFragments`フォントを希望の置換フォントに設定します。

#### Q: 提供されたコードを実行すると、どのような結果が期待されますか?

A: チュートリアルに従って、提供されている C# コードを実行すると、入力 PDF ドキュメントから未使用のフォントが削除され、更新されたバージョンが出力 PDF ファイルとして保存されます。

#### Q: 特定のページまたは領域からのみフォントを削除するようにコードを変更できますか?

A: 提供されているコードは、PDF ドキュメント全体から未使用のフォントを削除することに重点を置いています。特定のページまたは領域をフォント削除の対象にしたい場合は、アプローチを変更し、より複雑なロジックを使用して、それらの領域で使用されていないフォントを特定する必要があります。