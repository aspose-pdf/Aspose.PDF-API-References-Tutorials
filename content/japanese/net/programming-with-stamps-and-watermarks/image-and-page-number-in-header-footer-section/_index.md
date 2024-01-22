---
title: ヘッダー フッター セクションの画像とページ番号
linktitle: ヘッダー フッター セクションの画像とページ番号
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose を使用して PDF ドキュメントのヘッダーとフッターに画像とページ番号を追加する方法を確認してください。
type: docs
weight: 110
url: /ja/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントのヘッダーおよびフッター セクションに画像とページ番号を追加する方法を段階的に説明します。提供された C# ソース コードを使用してページを作成し、ヘッダーとフッターを設定し、ヘッダーに画像を追加し、ドキュメント フッター PDF にページ番号付きのテキストを追加する方法を示します。

## ステップ 1: 環境をセットアップする

始める前に、以下のものがあることを確認してください。

- インストールされた .NET 開発環境。
- .NET 用の Aspose.PDF ライブラリがダウンロードされ、プロジェクトで参照されます。

## ステップ 2: PDF ドキュメントとページを作成する

最初のステップは、PDF ドキュメント内に新しい Document オブジェクトとページを作成することです。その方法は次のとおりです。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//新しいドキュメントオブジェクトを作成する
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

//ドキュメント内にページを作成する
Aspose.Pdf.Page page = doc.Pages.Add();
```

上記のコードは、PDF ドキュメント内に新しい Document オブジェクトと空のページを作成します。

## ステップ 3: 画像を含むヘッダーを追加する

ページが作成されたので、画像を含むヘッダー セクションを追加できます。その方法は次のとおりです。

```csharp
//ヘッダーセクションを作成する
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//ページヘッダーを設定する
page. Header = header;

//画像オブジェクトを作成する
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

//画像パスを設定する
image1.File = dataDir + "aspose-logo.jpg";

//PDFドキュメントのページヘッダーに画像を追加します。
header.Paragraphs.Add(image1);
```

上記のコードはヘッダー セクションを作成し、このセクションでページ ヘッダーを設定し、ヘッダーに画像を追加します。

## ステップ 4: ページ番号を含むフッターを追加する

ヘッダーが追加されたので、ページ番号を含むフッター セクションを追加できます。その方法は次のとおりです。

```csharp
//フッターセクションを作成する
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

//PDF ドキュメントのフッターを定義する
page. Footer = footer;

//TextFragment オブジェクトを作成する
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P)");

//ページ番号を含むテキストを PDF ドキュメントのフッターに追加します。
footer.Paragraphs.Add(txt);
```

上記のコードはフッター セクションを作成し、このセクションでページのフッターを設定し、テキスト「Page: ($p of $P )」を含む TextFragment を追加します。

  ページ番号を表示します。

## ステップ 5: 変更した PDF ドキュメントを保存する

ヘッダーとフッターを追加したら、変更した PDF ドキュメントを保存できます。その方法は次のとおりです。

```csharp
//変更した PDF ドキュメントを保存する
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");
```

上記のコードは、編集した PDF ドキュメントを指定されたディレクトリに保存します。

### Aspose.PDF for .NET を使用したヘッダー フッター セクションの画像とページ番号のサンプル ソース コード 
```csharp

//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

//ドキュメントオブジェクトにページを作成する
Aspose.Pdf.Page page = doc.Pages.Add();

//ドキュメントのヘッダーセクションを作成する
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//PDFファイルのヘッダーを設定します。
page.Header = header;

//ページ内に画像オブジェクトを作成する
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

//画像ファイルのパスを設定します
image1.File = dataDir + "aspose-logo.jpg";

//PDFファイルのヘッダーページに画像を追加します
header.Paragraphs.Add(image1);

//ドキュメントのフッターセクションを作成する
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

//PDFファイルのフッターを設定する
page.Footer = footer;

//テキストオブジェクトを作成する
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P ) ");

//PDF ファイルのヘッダー セクションにテキストを追加する
footer.Paragraphs.Add(txt);

//PDF ファイルを保存する
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");

```

## 結論

おめでとうございます！ Aspose.PDF for .NET を使用して、PDF ドキュメントのヘッダーおよびフッター セクションに画像とページ番号を追加する方法を学習しました。この方法を使用して、PDF ドキュメントのヘッダーとフッターをカスタマイズできるようになりました。

### よくある質問

#### Q: PDF ドキュメントのヘッダーおよびフッター セクションに画像とページ番号を追加する目的は何ですか?

A: PDF ドキュメントのヘッダーおよびフッター セクションに画像とページ番号を追加すると、視覚的な魅力、ブランド化、およびナビゲーション要素を強化できます。画像はロゴ、透かし、その他のグラフィック要素を表すことができ、ページ番号はユーザーが進行状況を追跡し、特定のページを見つけるのに役立ちます。

#### Q: 提供されている C# ソース コードは、PDF ドキュメントのヘッダーとフッターに画像とページ番号を追加するのにどのように役立ちますか?

A: 提供されているコードは、PDF ドキュメントを作成し、ページを追加し、ヘッダーとフッターのセクションをカスタマイズする方法を示しています。ヘッダーに画像を追加し、フッターにページ番号付きのテキスト フラグメントを追加する方法を示します。

#### Q: ヘッダーには任意の画像形式を使用できますか?また、そのパスはどのように指定すればよいですか?

 A: はい、ヘッダー画像にはさまざまな画像形式 (JPEG、PNG、GIF など) を使用できます。画像のパスは、`File`の財産`Aspose.Pdf.Image`物体。

#### Q: ヘッダー セクションの画像の外観と位置をカスタマイズするにはどうすればよいですか?

 A: のプロパティを調整することで、画像の外観と位置をカスタマイズできます。`Aspose.Pdf.Image`オブジェクトをヘッダー セクションに追加する前に。たとえば、画像の寸法、配置、回転、不透明度などを設定できます。

####  Q：その目的は何ですか？`TextFragment` object used for the footer?

 A:`TextFragment`オブジェクトは、フッター セクションに表示されるテキストの作成と書式設定に使用されます。提供されたコードでは、ページ番号と総ページ数を表示するために使用されます。

#### Q: フッター テキストを変更して追加情報や書式設定を含めることはできますか?

 A: はい、フッター テキストは、`TextFragment`物体。要件に応じてテキストを追加したり、フォント、色、書式設定を変更したりできます。

#### Q: PDF ドキュメントの異なるページに異なるヘッダーとフッターのコンテンツを適用できますか?

 A: はい、別々に作成することで、異なるヘッダーとフッターのコンテンツを異なるページに適用できます。`HeaderFooter`オブジェクトを使用し、それらを特定のページに割り当てる`Header`そして`Footer`のプロパティ`Aspose.Pdf.Page`物体。

#### Q: フォント スタイルの変更や要素の追加など、ヘッダーとフッターをさらにカスタマイズするにはどうすればよいですか?

A: Aspose.PDF for .NET が提供するさまざまなクラスとプロパティを使用して、ヘッダーとフッターをカスタマイズできます。たとえば、さまざまなテキスト書式設定オプションを使用したり、ヘッダー セクションやフッター セクションに段落、画像、さらには表を追加したりできます。

#### Q: 必要に応じて、ヘッダーとフッターのセクションを削除またはクリアできますか?

A: はい、ヘッダーとフッターのセクションを削除またはクリアするには、`Header`そして`Footer`のプロパティ`Aspose.Pdf.Page`に反対する`null`.

#### Q: 追加された画像とページ番号が、さまざまなデバイスやビューア間で一貫性を保つようにするにはどうすればよいですか?

A: Aspose.PDF for .NET は、標準化された一貫性のある PDF ドキュメントを作成する機能を提供し、追加された画像とページ番号がさまざまなデバイスや PDF ビューア間で一貫して表示されるようにします。