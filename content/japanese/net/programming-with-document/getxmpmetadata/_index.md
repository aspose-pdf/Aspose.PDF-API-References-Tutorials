---
title: XMP メタデータの取得
linktitle: XMP メタデータの取得
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET の GetXmpMetadata 機能を使用して、C# ソース コードを使用して PDF ドキュメントから XMP メタデータを抽出する方法を学習します。
type: docs
weight: 200
url: /ja/net/programming-with-document/getxmpmetadata/
---
 Aspose.PDF for .NET は、開発者が .NET アプリケーションで PDF ファイルを作成、編集、変換できるようにする人気の PDF 操作ライブラリです。このライブラリが提供する機能の 1 つは、PDF ドキュメントから XMP メタデータを抽出する機能です。このチュートリアルでは、`GetXmpMetadata` Aspose.PDF for .NET の機能を使用して、PDF ドキュメントから XMP メタデータを抽出します。

## ステップ 1: Aspose.PDF for .NET をインストールする

 .NET アプリケーションで Aspose.PDF for .NET を使用するには、まずライブラリをインストールする必要があります。ライブラリの最新バージョンは、次の場所からダウンロードできます。[Aspose.PDF for .NET ダウンロード ページ](https://releases.aspose.com/pdf/net).

ライブラリをダウンロードしたら、ZIP ファイルの内容をコンピュータ上のフォルダに抽出します。次に、.NET プロジェクトに Aspose.PDF for .NET DLL への参照を追加する必要があります。

## ステップ 2: PDF ドキュメントをロードする

Aspose.PDF for .NET をインストールし、.NET プロジェクトに DLL への参照を追加すると、`GetXmpMetadata` PDF ドキュメントから XMP メタデータを抽出する機能。

この機能を使用する最初のステップは、XMP メタデータを抽出する PDF ドキュメントをロードすることです。これを行うには、次のコードを使用できます。

```csharp
// PDF ドキュメントへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

//PDF ドキュメントを開く
Document pdfDocument = new Document(dataDir + "GetXMPMetadata.pdf");
```

上記のコードでは、次のように置き換えます。`"YOUR DOCUMENT DIRECTORY"` PDF ドキュメントが置かれているディレクトリへのパスを置き換えます。このコードは PDF ドキュメントを`Document`オブジェクトを使用して、XMP メタデータを抽出できます。

## ステップ 3: XMP メタデータを抽出する

PDF ドキュメントから XMP メタデータを抽出するには、次のコードを使用できます。

```csharp
Console.WriteLine(pdfDocument.Metadata["xmp:CreateDate"]);
Console.WriteLine(pdfDocument.Metadata["xmp:Nickname"]);
Console.WriteLine(pdfDocument.Metadata["xmp:CustomProperty"]);
```

上記のコードでは、`xmp:CreateDate`, `xmp:Nickname` 、 そして`xmp:CustomProperty`以下は、PDF ドキュメントから抽出できる XMP メタデータ プロパティの例です。これらのプロパティ名は、抽出する他の XMP メタデータ プロパティの名前に置き換えることができます。

### Aspose.PDF for .NET を使用して XMP メタデータを取得するためのソース コードの例

以下は、PDF ドキュメントから XMP メタデータを抽出する完全なソース コードです。`GetXmpMetadata` Aspose.PDF for .NET の機能:

```csharp
// PDF ドキュメントへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

//PDF ドキュメントを開く
Document pdfDocument = new Document(dataDir + "GetXMPMetadata.pdf");

// XMPメタデータを抽出する
Console.WriteLine(pdfDocument.Metadata["xmp:CreateDate"]);
Console.WriteLine(pdfDocument.Metadata["xmp:Nickname"]);
Console.WriteLine(pdfDocument.Metadata["xmp:CustomProperty"]);
```

上記のコードでは、次のように置き換えます。`"YOUR DOCUMENT DIRECTORY"`PDF ドキュメントが置かれているディレクトリへのパスを置き換えます。このコードは、PDF ドキュメントから XMP メタデータを抽出し、コンソールに出力します。

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントから XMP メタデータを抽出する方法について説明しました。 XMP メタデータはドキュメントに関する貴重な情報を提供し、Aspose.PDF for .NET を使用すると、開発者は必要に応じてこの情報にアクセスし、アプリケーションで使用できます。 XMP メタデータを抽出することで、開発者はドキュメントの作成日、作成者、その他の記述データについての洞察を得ることができます。この情報は、PDF アプリケーションの機能とユーザー エクスペリエンスを向上させるために使用できます。 Aspose.PDF for .NET は、XMP メタデータにアクセスするためのシンプルで直接的な API を提供し、この機能を .NET アプリケーションに簡単に統合できます。

### よくある質問

#### Q: PDF ドキュメント内の XMP メタデータとは何ですか?

A: PDF ドキュメント内の XMP メタデータは、ドキュメント内に埋め込まれている Extensible Metadata Platform (XMP) 情報を指します。 XMP メタデータは、作成者、作成日、キーワード、その他の説明データなどのドキュメントに関する情報を保存する標準的な方法を提供します。これにより、さまざまなシステムやアプリケーション間でメタデータを簡単に取得および交換できるようになります。

#### Q: GetXmpMetadata 機能を使用して抽出できる情報の種類は何ですか?

 A: GetXmpMetadata 機能を使用すると、開発者は PDF ドキュメントからさまざまな XMP メタデータ プロパティを抽出できます。抽出できる XMP メタデータ プロパティの例をいくつか示します。`xmp:CreateDate`, `xmp:Nickname` 、 そして`xmp:CustomProperty`。開発者は、必要に応じてこれらのプロパティにアクセスし、アプリケーションで使用できます。

#### Q: Aspose.PDF for .NET を使用してカスタム XMP メタデータ プロパティを抽出できますか?

A: はい、Aspose.PDF for .NET を使用してカスタム XMP メタデータ プロパティを抽出できます。カスタム XMP メタデータ プロパティを PDF ドキュメントに含めて、アプリケーションまたは要件に固有の追加情報を保存できます。必要に応じて、これらのカスタム プロパティを抽出して使用できます。

#### Q: Aspose.PDF for .NET は PDF ドキュメントから他のメタデータ情報を抽出できますか?

A: はい。Aspose.PDF for .NET は、PDF ドキュメントからメタデータ情報を抽出するためのさまざまな機能を提供します。 XMP メタデータとは別に、ドキュメント情報 (タイトル、作成者、件名、キーワード)、PDF バージョン、暗号化の詳細などの情報を抽出することもできます。