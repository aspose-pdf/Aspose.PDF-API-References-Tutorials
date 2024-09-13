---
title: タグ付き画像付きPDFを作成
linktitle: タグ付き画像付きPDFを作成
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、タグ付き画像を含む PDF を作成する手順ガイド。
type: docs
weight: 40
url: /ja/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して、タグ付き画像を含む PDF ドキュメントを作成する方法をステップ バイ ステップで説明します。Aspose.PDF は、PDF ドキュメントをプログラムで作成、操作、変換できる強力なライブラリです。Aspose.PDF のタグ付きコンテンツ構造機能を使用すると、タグ付き画像を PDF ドキュメントに追加できます。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

1. .NET フレームワークとともにインストールされた Visual Studio。
2. .NET 用の Aspose.PDF ライブラリ。

## ステップ1: プロジェクトのセットアップ

まず、Visual Studio で新しいプロジェクトを作成し、Aspose.PDF for .NET ライブラリへの参照を追加します。ライブラリは Aspose の公式 Web サイトからダウンロードして、マシンにインストールできます。

## ステップ2: 必要な名前空間をインポートする

C# コード ファイルで、Aspose.PDF によって提供されるクラスとメソッドにアクセスするために必要な名前空間をインポートします。

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## ステップ3: タグ付き画像を含むPDFドキュメントを作成する

タグ付き画像を含む PDF ドキュメントを作成するには、次のコードを使用します。

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

このコードは、空の PDF ドキュメントを作成し、Aspose.PDF が提供するメソッドを使用してタグ付き画像を追加します。画像は、代替テキスト、タイトル、およびタグで指定されます。

## ステップ4: PDFドキュメントを保存する

PDF ドキュメントを保存するには、次のコードを使用します。

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

このコードは、タグ付けされた画像を含む PDF ドキュメントを指定されたファイルに保存します。

### Aspose.PDF for .NET を使用してタグ付き画像付き PDF を作成するためのサンプル ソース コード 
```csharp

//ドキュメント ディレクトリへのパス。
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
//解像度300 DPIの画像を追加（デフォルト）
figure1.SetImage(dataDir + @"aspose-logo.jpg");
// PDF文書を保存
document.Save(dataDir + "PDFwithTaggedImage.pdf");

```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して、タグ付き画像を含む PDF ドキュメントを作成する方法を学習しました。タグ付き画像は、PDF ドキュメントに追加の構造化された情報を追加します。

### よくある質問

#### Q: Aspose.PDF for .NET を使用してタグ付き画像を含む PDF ドキュメントを作成する目的は何ですか?

A: Aspose.PDF for .NET を使用してタグ付き画像を含む PDF ドキュメントを作成すると、ドキュメントのコンテンツにタグ付き画像を追加できます。タグ付き画像は、代替テキストやタイトルなどの構造化された情報を提供し、アクセシビリティと整理を強化します。

#### Q: Aspose.PDF ライブラリは、タグ付き画像を含む PDF ドキュメントの作成にどのように役立ちますか?

A: Aspose.PDF for .NET は、PDF ドキュメントをプログラムで作成、操作、変換する機能を提供する強力なライブラリです。このチュートリアルでは、ライブラリのタグ付きコンテンツ構造機能を使用して、タグ付き画像を PDF ドキュメントに追加します。

#### Q: Aspose.PDF for .NET を使用してタグ付き画像を含む PDF ドキュメントを作成するための前提条件は何ですか?

A: 始める前に、.NET フレームワークとともに Visual Studio がインストールされており、プロジェクトで .NET 用の Aspose.PDF ライブラリが参照されていることを確認してください。

#### Q: 提供された C# コードはどのようにしてタグ付き画像を含む PDF ドキュメントを作成しますか?

A: このコードは、PDF ドキュメントを作成し、タグ付き画像要素を定義し、それをドキュメントのコンテンツに追加する方法を示しています。タグ付き画像には、Aspose.PDF が提供するメソッドを使用して、代替テキスト、タイトル、タグが含まれます。

#### Q: タグ付けされた画像に異なる画像形式を使用できますか?

A: はい、タグ付けされた画像には、JPEG、PNG、GIF などのさまざまな画像形式を使用できます。チュートリアルで提供されているコード例では JPEG 画像を使用していますが、好みの形式の画像ファイルへのパスに置き換えることができます。

#### Q: タグ付けされた画像では代替テキスト (alt テキスト) はどのように使用されますか?

 A: 代替テキストは、視覚障害のあるユーザー向けのスクリーンリーダーによって読み上げられる画像の説明文です。提供されているコードでは、代替テキストは次のように設定されています。`AlternativeText`の財産`IllustrationElement`タグ付けされた画像を表します。

#### Q:`SetTitle` method contribute to the PDF document's tagged image?

 A:`SetTitle`メソッドは、PDF ドキュメントのタグ付けされたコンテンツのタイトルを設定し、タグ付けされた画像に追加のコンテキストを提供します。このタイトルは、タグ付けされたコンテンツの目的や主題を識別するのに役立ちます。

#### Q: タグ付けされた画像のタグとタイトルをカスタマイズできますか?

 A: はい、タグ付き画像のタグとタイトルをカスタマイズできます。`SetTag`そして`Title`の`IllustrationElement`コード例では、タグを「Fig」に設定し、タイトルを「Picture 1」に設定する方法を示しています。

#### Q: タグ付けされた画像がアクセス可能であり、アクセシビリティ標準に準拠していることをどのように確認すればよいですか?

A: Aspose.PDF のタグ付きコンテンツ構造機能を使用し、代替テキストやその他の関連情報を提供することで、タグ付き画像のアクセシビリティに貢献できます。アクセシビリティ標準への準拠を確保するには、代替テキストとドキュメント構造のベスト プラクティスに従う必要があります。

#### Q: 同様の手法を使用して、同じ PDF ドキュメントに複数のタグ付き画像を追加することは可能ですか?

A: はい、同様のテクニックを使って、同じPDF文書に複数のタグ付き画像を追加できます。`IllustrationElement`タグ付けされた画像ごとにインスタンスを作成し、必要に応じてプロパティをカスタマイズします。