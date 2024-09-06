---
title: XMPメタデータを取得
linktitle: XMPメタデータを取得
second_title: Aspose.PDF for .NET API リファレンス
description: C# ソース コードを使用して、Aspose.PDF for .NET の GetXmpMetadata 機能を使用して PDF ドキュメントから XMP メタデータを抽出する方法を学習します。
type: docs
weight: 200
url: /ja/net/programming-with-document/getxmpmetadata/
---
 Aspose.PDF for .NETは、開発者が.NETアプリケーションでPDFファイルを作成、編集、変換できるようにする人気のPDF操作ライブラリです。このライブラリが提供する機能の1つは、PDFドキュメントからXMPメタデータを抽出する機能です。このチュートリアルでは、`GetXmpMetadata` Aspose.PDF for .NET の機能を使用して、PDF ドキュメントから XMP メタデータを抽出します。

## ステップ 1: Aspose.PDF for .NET をインストールする

.NETアプリケーションでAspose.PDF for .NETを使用するには、まずライブラリをインストールする必要があります。ライブラリの最新バージョンは、[Aspose.PDF for .NET ダウンロード ページ](https://releases.aspose.com/pdf/net).

ライブラリをダウンロードしたら、ZIP ファイルの内容をコンピューターのフォルダーに解凍します。次に、.NET プロジェクトに Aspose.PDF for .NET DLL への参照を追加する必要があります。

## ステップ2: PDFドキュメントを読み込む

 Aspose.PDF for .NETをインストールし、.NETプロジェクトにDLLへの参照を追加したら、`GetXmpMetadata` PDF ドキュメントから XMP メタデータを抽出する機能。

この機能を使用するための最初の手順は、XMP メタデータを抽出する PDF ドキュメントを読み込むことです。これを行うには、次のコードを使用します。

```csharp
// PDF文書へのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF文書を開く
Document pdfDocument = new Document(dataDir + "GetXMPMetadata.pdf");
```

上記のコードでは、`"YOUR DOCUMENT DIRECTORY"` PDF文書があるディレクトリへのパスを入力します。このコードはPDF文書を`Document`オブジェクトを作成し、これを使用して XMP メタデータを抽出できます。

## ステップ3: XMPメタデータの抽出

PDF ドキュメントから XMP メタデータを抽出するには、次のコードを使用できます。

```csharp
Console.WriteLine(pdfDocument.Metadata["xmp:CreateDate"]);
Console.WriteLine(pdfDocument.Metadata["xmp:Nickname"]);
Console.WriteLine(pdfDocument.Metadata["xmp:CustomProperty"]);
```

上記のコードでは、`xmp:CreateDate`, `xmp:Nickname` 、 そして`xmp:CustomProperty`これらは、PDF ドキュメントから抽出できる XMP メタデータ プロパティの例です。これらのプロパティ名は、抽出する他の XMP メタデータ プロパティの名前に置き換えることができます。

### Aspose.PDF for .NET を使用して XMP メタデータを取得するためのサンプル ソース コード

以下は、PDF文書からXMPメタデータを抽出するための完全なソースコードです。`GetXmpMetadata` Aspose.PDF for .NET の機能:

```csharp
// PDF文書へのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF文書を開く
Document pdfDocument = new Document(dataDir + "GetXMPMetadata.pdf");

// XMPメタデータの抽出
Console.WriteLine(pdfDocument.Metadata["xmp:CreateDate"]);
Console.WriteLine(pdfDocument.Metadata["xmp:Nickname"]);
Console.WriteLine(pdfDocument.Metadata["xmp:CustomProperty"]);
```

上記のコードでは、`"YOUR DOCUMENT DIRECTORY"`PDF ドキュメントが保存されているディレクトリへのパスを指定します。このコードは PDF ドキュメントから XMP メタデータを抽出し、コンソールに出力します。

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントから XMP メタデータを抽出する方法について説明しました。XMP メタデータはドキュメントに関する貴重な情報を提供します。Aspose.PDF for .NET を使用すると、開発者はこの情報にアクセスし、必要に応じてアプリケーションで使用できます。XMP メタデータを抽出することで、開発者はドキュメントの作成日、作成者、およびその他の説明データに関する洞察を得ることができます。この情報を使用して、PDF アプリケーションの機能とユーザー エクスペリエンスを強化できます。Aspose.PDF for .NET は、XMP メタデータにアクセスするためのシンプルでわかりやすい API を提供するため、この機能を .NET アプリケーションに簡単に統合できます。

### よくある質問

#### Q: PDF ドキュメント内の XMP メタデータとは何ですか?

A: PDF ドキュメント内の XMP メタデータは、ドキュメント内に埋め込まれた Extensible Metadata Platform (XMP) 情報を指します。XMP メタデータは、作成者、作成日、キーワード、その他の説明データなど、ドキュメントに関する情報を保存するための標準的な方法を提供します。これにより、さまざまなシステムやアプリケーション間でメタデータを簡単に取得および交換できます。

#### Q: GetXmpMetadata 機能を使用して抽出できる情報の種類は何ですか?

 A: GetXmpMetadata機能を使用すると、開発者はPDF文書からさまざまなXMPメタデータプロパティを抽出できます。抽出できるXMPメタデータプロパティの例は次のとおりです。`xmp:CreateDate`, `xmp:Nickname` 、 そして`xmp:CustomProperty`開発者はこれらのプロパティにアクセスし、必要に応じてアプリケーションで使用できます。

#### Q: Aspose.PDF for .NET を使用してカスタム XMP メタデータ プロパティを抽出できますか?

A: はい、Aspose.PDF for .NET を使用してカスタム XMP メタデータ プロパティを抽出できます。カスタム XMP メタデータ プロパティを PDF ドキュメントに含めることで、アプリケーションや要件に固有の追加情報を保存できます。必要に応じてこれらのカスタム プロパティを抽出して使用できます。

#### Q: Aspose.PDF for .NET は PDF ドキュメントから他のメタデータ情報を抽出できますか?

A: はい、Aspose.PDF for .NET は PDF ドキュメントからメタデータ情報を抽出するためのさまざまな機能を提供します。XMP メタデータ以外にも、ドキュメント情報 (タイトル、作成者、件名、キーワード)、PDF バージョン、暗号化の詳細などの情報を抽出することもできます。