---
title: タグ付けされた画像を含む PDF を作成する
linktitle: タグ付けされた画像を含む PDF を作成する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、タグ付き画像を含む PDF を作成するためのステップバイステップ ガイド。
type: docs
weight: 40
url: /ja/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して、タグ付き画像を含む PDF ドキュメントを作成する方法について段階的なガイドを提供します。 Aspose.PDF は、PDF ドキュメントをプログラムで作成、操作、変換できる強力なライブラリです。 Aspose.PDF のタグ付きコンテンツ構造機能を使用すると、タグ付き画像を PDF ドキュメントに追加できます。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

1. Visual Studio には .NET Framework がインストールされています。
2. .NET 用の Aspose.PDF ライブラリ。

## ステップ 1: プロジェクトのセットアップ

まず、Visual Studio で新しいプロジェクトを作成し、Aspose.PDF for .NET ライブラリへの参照を追加します。 Aspose 公式 Web サイトからライブラリをダウンロードして、マシンにインストールできます。

## ステップ 2: 必要な名前空間をインポートする

C# コード ファイルで、Aspose.PDF が提供するクラスとメソッドにアクセスするために必要な名前空間をインポートします。

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## ステップ 3: タグ付けされた画像を含む PDF ドキュメントを作成する

次のコードを使用して、タグ付けされた画像を含む PDF ドキュメントを作成します。

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Creating a PDF with a tagged image");
taggedContent.SetLanguage("fr-FR");

IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Picture 1";
figure1.SetTag("Fig");
figure1.SetImage(dataDir + @"aspose-logo.jpg");
```

このコードは、空の PDF ドキュメントを作成し、Aspose.PDF が提供するメソッドを使用してタグ付き画像を追加します。画像はaltテキスト、タイトル、タグで指定します。

## ステップ 4: PDF ドキュメントを保存する

次のコードを使用して PDF ドキュメントを保存します。

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

このコードは、タグ付けされた画像を含む PDF ドキュメントを指定されたファイルに保存します。

### Aspose.PDF for .NET を使用してタグ付きイメージ付き PDF を作成するためのサンプル ソース コード 
```csharp

//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("CreatePDFwithTaggedImage");
taggedContent.SetLanguage("en-US");
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Image 1";
figure1.SetTag("Fig");
//解像度 300 DPI の画像を追加します (デフォルト)
figure1.SetImage(dataDir + @"aspose-logo.jpg");
//PDFドキュメントを保存
document.Save(dataDir + "PDFwithTaggedImage.pdf");

```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して、タグ付けされた画像を含む PDF ドキュメントを作成する方法を学習しました。タグ付けされた画像は、PDF ドキュメントに追加の構造化情報を追加します。

### よくある質問

#### Q: Aspose.PDF for .NET を使用してタグ付きイメージを含む PDF ドキュメントを作成する目的は何ですか?

A: Aspose.PDF for .NET を使用してタグ付きイメージを含む PDF ドキュメントを作成すると、ドキュメントのコンテンツにタグ付きイメージを追加できます。タグ付けされた画像は、代替テキストやタイトルなどの構造化された情報を提供し、アクセシビリティと整理を強化します。

#### Q: Aspose.PDF ライブラリは、タグ付き画像を含む PDF ドキュメントの作成をどのように支援しますか?

A: Aspose.PDF for .NET は、PDF ドキュメントをプログラムで作成、操作、変換するための機能を提供する堅牢なライブラリです。このチュートリアルでは、ライブラリのタグ付きコンテンツ構造機能を使用して、タグ付き画像を PDF ドキュメントに追加します。

#### Q: Aspose.PDF for .NET を使用してタグ付きイメージを含む PDF ドキュメントを作成するための前提条件は何ですか?

A: 始める前に、Visual Studio が .NET Framework とともにインストールされていること、およびプロジェクト内で .NET 用の Aspose.PDF ライブラリが参照されていることを確認してください。

#### Q: 提供されている C# コードは、タグ付き画像を含む PDF ドキュメントをどのように作成しますか?

A: このコードは、PDF ドキュメントを作成し、タグ付き画像要素を定義して、それをドキュメントのコンテンツに追加する方法を示しています。タグ付けされた画像には、Aspose.PDF によって提供されるメソッドを使用した代替テキスト、タイトル、およびタグが含まれます。

#### Q: タグ付き画像に異なる画像形式を使用できますか?

A: はい、タグ付き画像には JPEG、PNG、GIF などのさまざまな画像形式を使用できます。チュートリアルで提供されるコード例では JPEG 画像を使用していますが、これを次の画像ファイルへのパスに置き換えることができます。好みのフォーマット。

#### Q: タグ付き画像で代替テキスト (alt テキスト) はどのように使用されますか?

 A: 代替テキストは画像のテキストによる説明を提供し、視覚障害のあるユーザーのためにスクリーン リーダーによって読み上げられます。提供されたコードでは、代替テキストは`AlternativeText`の財産`IllustrationElement`タグ付けされた画像を表します。

####  Q: どうやって`SetTitle` method contribute to the PDF document's tagged image?

 A:`SetTitle`このメソッドは、PDF ドキュメントのタグ付きコンテンツのタイトルを設定し、タグ付き画像に追加のコンテキストを提供します。このタイトルは、タグ付けされたコンテンツの目的や主題を特定するのに役立ちます。

#### Q: タグ付けされた画像のタグとタイトルをカスタマイズできますか?

 A: はい、タグとタグ付けされた画像のタイトルは、`SetTag`そして`Title`のメソッド`IllustrationElement`。このコード例は、タグを「Fig」に、タイトルを「Picture 1」に設定する方法を示しています。

#### Q: タグ付けされた画像がアクセス可能であり、アクセシビリティ標準に準拠していることを確認するにはどうすればよいですか?

A: Aspose.PDF のタグ付きコンテンツ構造機能を使用し、代替テキストやその他の関連情報を提供することにより、タグ付き画像のアクセシビリティに貢献します。アクセシビリティ標準への準拠を確保するには、代替テキストとドキュメント構造のベスト プラクティスに従うことが必要です。

#### Q: 同様の手法を使用して、同じ PDF ドキュメントに複数のタグ付き画像を追加することはできますか?

 A: はい、同様の手法を使用して、複数のタグ付き画像を同じ PDF ドキュメントに追加できます。追加で作成することになります`IllustrationElement`タグ付けされた画像ごとにインスタンスを作成し、必要に応じてそのプロパティをカスタマイズします。