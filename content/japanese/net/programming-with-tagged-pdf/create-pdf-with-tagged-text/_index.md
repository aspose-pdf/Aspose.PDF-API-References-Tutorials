---
title: タグ付きテキストを含むPDFを作成する
linktitle: タグ付きテキストを含むPDFを作成する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、タグ付きテキストを含む PDF を作成する手順ガイド。
type: docs
weight: 50
url: /ja/net/programming-with-tagged-pdf/create-pdf-with-tagged-text/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して、タグ付きテキストを含む PDF ドキュメントを作成する方法をステップ バイ ステップで説明します。Aspose.PDF は、PDF ドキュメントをプログラムで作成、操作、変換できる強力なライブラリです。Aspose.PDF のタグ付きコンテンツ構造機能を使用すると、PDF ドキュメントにタグ付きテキストを追加できます。

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

## ステップ3: タグ付きテキストを含むPDF文書を作成する

タグ付きテキストを含む PDF ドキュメントを作成するには、次のコードを使用します。

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");

HeaderElement headerElement = taggedContent.CreateHeaderElement();
headerElement.ActualText = "Header 1";

ParagraphElement paragraphElement1 = taggedContent.CreateParagraphElement();
paragraphElement1.ActualText = "test1";

//ここに段落を追加

// PDF文書を保存する
document.Save(dataDir + "PDFwithTagText.pdf");
```

このコードは、空の PDF ドキュメントを作成し、Aspose.PDF が提供するメソッドを使用してタグ付きテキストを追加します。適切なメソッドを使用して、見出しや段落などの他のタグ付きテキスト要素を追加できます。

### Aspose.PDF for .NET を使用してタグ付きテキストを含む PDF を作成するためのサンプル ソース コード 
```csharp

//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//PDFドキュメントを作成
Document document = new Document();
//TaggedPdfで作業用のコンテンツを取得する
ITaggedContent taggedContent = document.TaggedContent;
//ドキュメントのタイトルと言語を設定する
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
//テキストブロックレベルの構造要素を作成する
HeaderElement headerElement = taggedContent.CreateHeaderElement();
headerElement.ActualText = "Heading 1";
ParagraphElement paragraphElement1 = taggedContent.CreateParagraphElement();
paragraphElement1.ActualText = "test1";
ParagraphElement paragraphElement2 = taggedContent.CreateParagraphElement();
paragraphElement2.ActualText = "test 2";
ParagraphElement paragraphElement3 = taggedContent.CreateParagraphElement();
paragraphElement3.ActualText = "test 3";
ParagraphElement paragraphElement4 = taggedContent.CreateParagraphElement();
paragraphElement4.ActualText = "test 4";
ParagraphElement paragraphElement5 = taggedContent.CreateParagraphElement();
paragraphElement5.ActualText = "test 5";
ParagraphElement paragraphElement6 = taggedContent.CreateParagraphElement();
paragraphElement6.ActualText = "test 6";
ParagraphElement paragraphElement7 = taggedContent.CreateParagraphElement();
paragraphElement7.ActualText = "test 7";
// PDF文書を保存
document.Save( dataDir + "PDFwithTaggedText.pdf");

```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して、タグ付きテキストを含む PDF ドキュメントを作成する方法を学習しました。Aspose.PDF のマークされたコンテンツ構造機能を使用すると、テキストを構造化して整理し、アクセシビリティとセマンティクスを向上させることができます。

### よくある質問

#### Q: Aspose.PDF for .NET を使用してタグ付きテキストを含む PDF ドキュメントを作成する目的は何ですか?

A: Aspose.PDF for .NET を使用してタグ付きテキストを含む PDF ドキュメントを作成すると、PDF ドキュメント内のテキスト コンテンツを構造化して整理できます。タグ付きテキストによりセマンティックな意味が追加され、ユーザー、特に支援技術を使用するユーザーのアクセシビリティが向上します。

#### Q: Aspose.PDF は、タグ付きテキストを含む PDF ドキュメントの作成にどのように役立ちますか?

A: Aspose.PDF for .NET は、PDF ドキュメントをプログラムで作成、操作、変換する機能を提供する強力なライブラリです。このチュートリアルでは、ライブラリのタグ付きコンテンツ構造機能を使用して、構造化され意味的に意味のあるテキストを PDF ドキュメントに追加します。

#### Q: Aspose.PDF for .NET を使用してタグ付きテキストを含む PDF ドキュメントを作成するための前提条件は何ですか?

A: 始める前に、.NET フレームワークとともに Visual Studio がインストールされており、プロジェクトで .NET 用の Aspose.PDF ライブラリが参照されていることを確認してください。

#### Q: 提供された C# コードはどのようにしてタグ付きテキストを含む PDF ドキュメントを作成しますか?

A: コード例では、PDF ドキュメントを作成し、さまざまなタグ付きテキスト要素 (ヘッダーや段落など) を定義して、それらをドキュメントのコンテンツに追加する方法を示しています。これは、Aspose.PDF が提供するタグ付きコンテンツ構造機能を使用して実現されます。

#### Q: ヘッダーや段落などのタグ付けされたテキスト要素をカスタマイズするにはどうすればよいですか?

 A: 適切な方法を使用して、タグ付きテキスト要素をカスタマイズできます。`CreateHeaderElement`そして`CreateParagraphElement` 、次のようなプロパティを設定します`ActualText`意味のあるテキストとセマンティクスを提供する。

#### Q: 同様の手法を使用して、リストやリンクなどの他のタグ付きテキスト要素を追加できますか?

A: はい、同様の手法を使用して、リスト、リンク、その他のカスタム構造などの他のタグ付きテキスト要素を追加できます。Aspose.PDF には、さまざまな種類のタグ付きコンテンツを作成するためのさまざまな方法が用意されており、ドキュメントのセマンティクスを強化できます。

####  Q:`SetTitle` method contribute to the PDF document's tagged text?

 A:`SetTitle`メソッドは、PDF ドキュメントのタグ付けされたコンテンツのタイトルを設定し、ドキュメントの目的または主題の簡単な説明を提供します。この情報は、ユーザーがタグ付けされたテキストのコンテキストを理解するのに役立ちます。

#### Q: タグ付きテキストを使用すると、PDF ドキュメントのアクセシビリティはどのように向上しますか?

A: タグ付きテキストはドキュメントに意味論的な意味を追加し、障害を持つユーザーや支援技術を使用するユーザーがドキュメントにアクセスしやすくなります。スクリーン リーダーやその他の支援デバイスは、タグ付きテキストを解釈して表示し、ユーザー エクスペリエンスを向上させます。

####  Q:`SetLanguage` method enhance the tagged text in a PDF document?

 A:`SetLanguage`メソッドは、PDF ドキュメントのタグ付けされたコンテンツの言語属性を設定します。これにより、タグ付けされたテキストが記述されている言語が示され、アクセシビリティが向上し、適切な言語固有のレンダリングが可能になります。

#### Q: 同様の手法を使用して、タグ付けされたテキストの横に画像やマルチメディアなどの他の要素を追加することは可能ですか?

A: はい、同様の手法を使用して、タグ付きテキストの横に画像、マルチメディア、注釈などの他の要素を追加できます。Aspose.PDF には、ドキュメント内でさまざまな種類のコンテンツを組み合わせるための幅広い機能が用意されています。