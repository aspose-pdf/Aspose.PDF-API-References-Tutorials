---
title: デフォルトのフォント名の設定
linktitle: デフォルトのフォント名の設定
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルにデフォルトのフォント名を設定するためのステップバイステップのガイド。
type: docs
weight: 270
url: /ja/net/document-conversion/set-default-font-name/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルにデフォルトのフォント名を設定する方法を説明します。 PDF ファイルから画像を抽出するときに、フォントが見つからないという問題が発生することがあります。デフォルトのフォント名を指定すると、抽出されたテキストが正しく表示されるようになります。 PDF ファイルにデフォルトのフォント名を設定するには、次の手順に従います。

## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。

- C# プログラミング言語の基本的な知識。
- .NET 用の Aspose.PDF ライブラリがシステムにインストールされています。
- Visual Studio などの開発環境。

## ステップ 1: PDF ドキュメントをロードする
最初のステップは、PDF ドキュメントを`Document`物体。次のコードを使用します。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     //追加するコード
}
```

必ず交換してください`"YOUR DOCUMENTS DIRECTORY"`PDF ファイルが置かれている実際のディレクトリに置き換えます。

## ステップ 2: デフォルトのフォント名を設定する
次に、デフォルトのフォント名を設定します。`DefaultFontName`のオプション`RenderingOptions`物体。次のコードを使用します。

```csharp
using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
     {
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         RenderingOptions ro = new RenderingOptions();
         ro.DefaultFontName = "Arial";
         pngDevice.RenderingOptions = ro;
        
         //追加するコード
     }
}
```

必ず交換してください`"Arial"`希望のフォント名を付けます。

## ステップ 3: 画像の抽出
次に、PDF ドキュメントの指定したページから画像を抽出します。次のコードを使用します。

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```

必ず正しいページ番号を指定してください。`pdfDocument.Pages[1]`.

### Aspose.PDF for .NET を使用したデフォルトのフォント名の設定のソース コード例

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
	using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
	{
		Resolution resolution = new Resolution(300);
		PngDevice pngDevice = new PngDevice(resolution);
		RenderingOptions ro = new RenderingOptions();
		ro.DefaultFontName = "Arial";
		pngDevice.RenderingOptions = ro;
		pngDevice.Process(pdfDocument.Pages[1], imageStream);
	}
}
```

## 結論
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルにデフォルトのフォント名を設定する方法を学びました。デフォルトのフォント名を指定すると、抽出されたテキストが正しく表示されるようになります。 PDF ファイルから画像を抽出するときにフォントが見つからない問題を解決するには、この方法を使用します。

### よくある質問

#### Q: Aspose.PDF for .NET とは何ですか?

A: Aspose.PDF for .NET は、開発者が C# アプリケーションで PDF ドキュメントを操作できるようにする強力なライブラリです。 PDF ファイル内のデフォルトのフォント名を設定するなど、さまざまな機能を提供します。

#### Q: PDF ファイルにデフォルトのフォント名を設定する必要があるのはなぜですか?

A: デフォルトのフォント名を設定すると、PDF ドキュメントからテキストを抽出するときに便利です。 PDF に抽出マシンで使用できないフォントを使用したテキストが含まれている場合、デフォルトのフォント名を指定すると、テキストが正しく表示されます。

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメントをロードし、デフォルトのフォント名を設定するにはどうすればよいですか?

 A: PDF ドキュメントをロードしてデフォルトのフォント名を設定するには、`Document`PDF ファイルをロードするクラスと`RenderingOptions.DefaultFontName`プロパティを使用して、希望するデフォルトのフォント名を指定します。

#### Q: デフォルトのフォント名として任意のフォントを選択できますか?

A:はい、抽出マシンで利用可能な任意のフォントをデフォルトのフォント名として選択できます。テキストを正確にレンダリングするには、元の PDF で欠落しているフォントとよく一致するフォントを使用します。

#### Q: デフォルトのフォント名を設定すると、PDF ファイルが永続的に変更されますか?

A: いいえ、Aspose.PDF for .NET を使用したデフォルトのフォント名の設定は、テキスト抽出中に行われる一時的な変更です。元の PDF ファイルは変更されません。