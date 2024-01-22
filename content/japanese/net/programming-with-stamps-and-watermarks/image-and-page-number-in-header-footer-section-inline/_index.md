---
title: ヘッダー フッター セクションの画像とページ番号インライン
linktitle: ヘッダー フッター セクションの画像とページ番号インライン
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET でインライン段落を使用してヘッダーとフッターに画像とページ番号を追加する方法を学びます。
type: docs
weight: 120
url: /ja/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントのヘッダーおよびフッター セクションに画像とページ番号を追加する方法を段階的に説明します。提供された C# ソース コードを使用して、ページを作成し、ヘッダーとフッターを設定し、PDF ドキュメントのヘッダーにインライン段落を使用して画像とテキストを追加します。

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
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

//ドキュメント内にページを作成する
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

上記のコードは、PDF ドキュメント内に新しい Document オブジェクトと空のページを作成します。

## ステップ 3: 画像とインライン テキストを含むヘッダーを追加する

ページが作成されたので、インライン段落を使用して画像とテキストを含むヘッダー セクションを追加できます。その方法は次のとおりです。

```csharp
//ヘッダーセクションを作成する
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//ページヘッダーを設定する
page. Header = header;

//最初のインライン テキストの TextFragment オブジェクトを作成する
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a robust component developed by");

//文字の色を指定する
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

//画像の Image オブジェクトを作成する
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

//画像パスを設定する
image1.File = dataDir + "aspose-logo.jpg";

//画像の寸法を定義する
image1.FixWidth = 50;
image1.FixHeight = 20;

//最初のインラインテキストが画像であることを示します
image1.IsInLineParagraph = true;

// 番目のインライン テキストを作成する
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;

//ヘッダーに項目を追加する
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

上記のコードはヘッダー セクションを作成し、このセクションでページ ヘッダーを設定し、インライン テキストとインライン Image オブジェクトを含む TextFragment を追加します。

## ステップ 4: 変更した PDF ドキュメントを保存する

画像とインライン テキストを含むヘッダーを追加したら、変更した PDF ドキュメントを保存できます。その方法は次のとおりです。

```csharp
//変更した PDF ドキュメントを保存する
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

上記のコードは、編集した PDF ドキュメントを指定されたディレクトリに保存します。

### Aspose.PDF for .NET を使用したヘッダー フッター セクションの画像とページ番号インラインのサンプル ソース コード 
```csharp

//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//空のコンストラクターを呼び出して Document オブジェクトをインスタンス化します。
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

//PDF オブジェクトにページを作成する
Aspose.Pdf.Page page = pdf1.Pages.Add();

//ドキュメントのヘッダーセクションを作成する
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//PDFファイルのヘッダーを設定します。
page.Header = header;

//テキストオブジェクトを作成する
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");

//色を指定してください
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

//セクションに画像オブジェクトを作成します
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

//画像ファイルのパスを設定します
image1.File = dataDir + "aspose-logo.jpg";

//画像の幅を設定する
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

//PDF を保存する
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");

```

## 結論

おめでとうございます！ Aspose.PDF for .NET でインライン段落を使用して、PDF ドキュメントのヘッダーとフッター セクションに画像とページ番号を追加する方法を学習しました。 PDF ドキュメントのヘッダーとフッターを柔軟にカスタマイズできるようになりました。

### よくある質問

#### Q: PDF ドキュメントのヘッダーに画像とテキストを追加するためにインライン段落を使用する利点は何ですか?

A: インライン段落を使用すると、同じ段落内に画像とテキストをシームレスに統合でき、配置と書式を正確に制御できます。この方法は、視覚要素を含むカスタマイズされたヘッダーを作成する場合に特に便利です。

#### Q: 提供されている C# ソース コードは、PDF ドキュメントのヘッダーのインライン段落をどのように実現しますか?

A: 提供されているコードは、PDF ドキュメントの作成方法、ページの追加方法、およびインライン段落を使用したヘッダーのカスタマイズ方法を示しています。インライン テキスト、インライン イメージ、および別のインライン TextFragment を含む TextFragment を追加します。

#### Q: ヘッダーのインライン テキストの色を指定するにはどうすればよいですか?

 A: インラインテキストの色は、`ForegroundColor`の財産`TextState`の`TextFragment`物体。

#### Q: ヘッダー内のインライン画像のサイズを調整できますか?

 A: はい、インライン画像の寸法は、`FixWidth`そして`FixHeight`のプロパティ`Image`物体。これにより、ヘッダー内の画像の幅と高さを制御できます。

#### Q: ヘッダーにハイパーリンクやさまざまなフォント スタイルなどの追加のインライン要素を含めることはできますか?

 A: はい、さらに多くのインライン要素を作成することで、ヘッダーに追加のインライン要素を含めることができます。`TextFragment`または`Image`必要なプロパティを持つオブジェクト。これにより、ハイパーリンク、さまざまなフォント スタイル、その他の視覚要素など、ヘッダーをさらにカスタマイズできます。

#### Q: インライン画像とテキストが、さまざまなデバイスやビューア間で適切に配置され、フォーマットされた状態を維持するにはどうすればよいですか?

A: Aspose.PDF for .NET は、インライン画像とテキストが適切に配置され、書式設定されることを保証し、その結果、さまざまなデバイスや PDF ビューア間で一貫した外観が得られます。

#### Q: インライン段落をフッター セクションにも適用できますか?

 A: はい、インライン段落を使用するのと同じテクニックをフッター セクションに適用できます。`Footer`オブジェクトを作成し、それにテキストや画像などのインライン要素を追加します。

#### Q: インライン段落を他のヘッダーまたはフッターのカスタマイズ方法と組み合わせることはできますか?

A: はい、インライン段落を Aspose.PDF for .NET が提供する他のヘッダーまたはフッターのカスタマイズ メソッドと組み合わせて、より複雑でカスタマイズされたヘッダーまたはフッターのデザインを作成できます。

#### Q: 必要に応じて、ヘッダーからインライン要素を削除またはクリアできますか?

 A: はい、インライン要素は、`HeaderFooter`オブジェクトを削除し、それぞれのインライン段落を削除します。

#### Q: PDF ドキュメントの特定のページにインライン段落を適用するにはどうすればよいですか?

 A: インライン段落を特定のページに適用するには、別個の段落を作成できます。`HeaderFooter`各ページのオブジェクトを作成し、`Header`それぞれの財産`Aspose.Pdf.Page`オブジェクト。