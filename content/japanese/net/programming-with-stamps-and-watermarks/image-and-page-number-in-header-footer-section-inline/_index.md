---
title: ヘッダー フッター セクションのインラインの画像とページ番号
linktitle: ヘッダー フッター セクションのインラインの画像とページ番号
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET でインライン段落を使用してヘッダーとフッターに画像とページ番号を追加する方法を学習します。
type: docs
weight: 120
url: /ja/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントのヘッダーとフッターのセクションに画像とページ番号を追加する方法を段階的に説明します。提供されている C# ソース コードを使用してページを作成し、ヘッダーとフッターを設定し、PDF ドキュメントのヘッダーにインライン段落を使用して画像とテキストを追加します。

## ステップ1: 環境の設定

始める前に、次のものがあることを確認してください。

- インストールされた .NET 開発環境。
- .NET 用の Aspose.PDF ライブラリがダウンロードされ、プロジェクトで参照されます。

## ステップ2: PDFドキュメントとページの作成

最初のステップは、新しい Document オブジェクトと PDF ドキュメントのページを作成することです。手順は次のとおりです。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//新しいドキュメントオブジェクトを作成する
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

//ドキュメントにページを作成する
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

上記のコードは、新しい Document オブジェクトと PDF ドキュメント内の空のページを作成します。

## ステップ3: 画像とインラインテキストを含むヘッダーを追加する

ページが作成されたので、インライン段落を使用して画像とテキストを含むヘッダー セクションを追加できます。手順は次のとおりです。

```csharp
//ヘッダーセクションを作成する
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//ページヘッダーを設定する
page. Header = header;

//最初のインラインテキスト用のTextFragmentオブジェクトを作成する
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a robust component developed by");

//テキストの色を指定
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

//画像のImageオブジェクトを作成する
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

//画像パスを設定する
image1.File = dataDir + "aspose-logo.jpg";

//画像の寸法を定義する
image1.FixWidth = 50;
image1.FixHeight = 20;

//最初のインラインテキストが画像であることを示す
image1.IsInLineParagraph = true;

//2番目のインラインテキストを作成する
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;

//ヘッダーに項目を追加する
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

上記のコードは、ヘッダー セクションを作成し、このセクションでページ ヘッダーを設定し、インライン テキストとインライン Image オブジェクトを含む TextFragment を追加します。

## ステップ4: 変更したPDF文書を保存する

画像とインライン テキストを含むヘッダーを追加したら、変更した PDF ドキュメントを保存できます。手順は次のとおりです。

```csharp
//変更したPDF文書を保存する
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

上記のコードは、編集された PDF ドキュメントを指定されたディレクトリに保存します。

### Aspose.PDF for .NET を使用した、ヘッダー フッター セクションのインラインでの画像とページ番号のサンプル ソース コード 
```csharp

//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//空のコンストラクタを呼び出してDocumentオブジェクトをインスタンス化する
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

//Pdfオブジェクトにページを作成する
Aspose.Pdf.Page page = pdf1.Pages.Add();

//ドキュメントのヘッダーセクションを作成する
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//PDFファイルのヘッダーを設定する
page.Header = header;

//テキストオブジェクトを作成する
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");

//色を指定する
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

//セクションに画像オブジェクトを作成する
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

//画像ファイルのパスを設定する
image1.File = dataDir + "aspose-logo.jpg";

//画像の幅を設定する情報
image1.FixWidth = 50;
image1.FixHeight = 20;

//seg1 の InlineParagraph が画像であることを示します。
image1.IsInLineParagraph = true;
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);

//PDFを保存する
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");

```

## 結論

おめでとうございます！Aspose.PDF for .NET でインライン段落を使用して PDF ドキュメントのヘッダーとフッターのセクションに画像とページ番号を追加する方法を学習しました。これで、PDF ドキュメントのヘッダーとフッターを柔軟にカスタマイズできるようになりました。

### よくある質問

#### Q: PDF ドキュメントのヘッダーに画像とテキストを追加するためにインライン段落を使用する利点は何ですか?

A: インライン段落を使用すると、画像とテキストを同じ段落内にシームレスに統合し、配置と書式設定を正確に制御できます。この方法は、視覚的な要素を使用してカスタマイズされたヘッダーを作成する場合に特に便利です。

#### Q: 提供されている C# ソース コードは、PDF ドキュメントのヘッダーのインライン段落をどのように実現するのでしょうか?

A: 提供されているコードは、PDF ドキュメントを作成し、ページを追加し、インライン段落を使用してヘッダーをカスタマイズする方法を示しています。インライン テキスト、インライン イメージ、および別のインライン TextFragment を含む TextFragment を追加します。

#### Q: ヘッダー内のインラインテキストの色を指定するにはどうすればよいですか?

 A: インラインテキストの色は、`ForegroundColor`の財産`TextState`の`TextFragment`物体。

#### Q: ヘッダー内のインライン画像のサイズを調整できますか?

 A: はい、インライン画像のサイズは、`FixWidth`そして`FixHeight`の特性`Image`オブジェクト。これにより、ヘッダー内の画像の幅と高さを制御できます。

#### Q: ヘッダーにハイパーリンクや異なるフォント スタイルなどの追加のインライン要素を含めることができますか?

 A: はい、ヘッダーにインライン要素を追加することができます。`TextFragment`または`Image`必要なプロパティを持つオブジェクト。これにより、ハイパーリンク、さまざまなフォント スタイル、その他の視覚要素など、ヘッダーをさらにカスタマイズできます。

#### Q: さまざまなデバイスやビューア間でインライン画像とテキストが適切に配置され、フォーマットされた状態を維持するにはどうすればよいでしょうか?

A: Aspose.PDF for .NET は、インライン画像とテキストが適切に配置およびフォーマットされるようにし、さまざまなデバイスや PDF ビューアー間で一貫した外観を実現します。

#### Q: フッターセクションにもインライン段落を適用できますか?

 A: はい、インライン段落を使用する同じテクニックをフッターセクションに適用するには、`Footer`オブジェクトを作成し、テキストや画像などのインライン要素を追加します。

#### Q: インライン段落を他のヘッダーまたはフッターのカスタマイズ方法と組み合わせることは可能ですか?

A: はい、インライン段落を Aspose.PDF for .NET が提供する他のヘッダーまたはフッターのカスタマイズ方法と組み合わせて、より複雑でカスタマイズされたヘッダーまたはフッターのデザインを作成できます。

#### Q: 必要に応じて、ヘッダーからインライン要素を削除またはクリアできますか?

 A: はい、インライン要素の内容を変更することで、インライン要素を削除またはクリアできます。`HeaderFooter`オブジェクトを削除し、それぞれのインライン段落を削除します。

#### Q: PDF ドキュメントの特定のページにインライン段落を適用するにはどうすればよいですか?

 A: 特定のページにインライン段落を適用するには、別の`HeaderFooter`各ページのオブジェクトを作成し、`Header`それぞれの財産`Aspose.Pdf.Page`オブジェクト。