---
title: PDF ファイル内のファイル情報を取得する
linktitle: PDF ファイル内のファイル情報を取得する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET の PDF ファイル機能の GetFileInfo を使用して、PDF ドキュメントに関するメタデータ情報を取得する方法を学習します。
type: docs
weight: 180
url: /ja/net/programming-with-document/getfileinfo/
---
 Aspose.PDF for .NETは、開発者が.NETアプリケーションでPDFファイルを作成、編集、変換できるようにする人気のPDF操作ライブラリです。このライブラリが提供する機能の1つは、PDFドキュメントのメタデータに関する情報を取得する機能です。このチュートリアルでは、`GetFileInfo` Aspose.PDF for .NET の機能を使用して、PDF ドキュメントのメタデータに関する情報を取得します。

## ステップ 1: Aspose.PDF for .NET をインストールする

.NETアプリケーションでAspose.PDF for .NETを使用するには、まずライブラリをインストールする必要があります。ライブラリの最新バージョンは、[Aspose.PDF for .NET ダウンロード ページ](https://releases.aspose.com/pdf/net).

ライブラリをダウンロードしたら、ZIP ファイルの内容をコンピューターのフォルダーに解凍します。次に、.NET プロジェクトに Aspose.PDF for .NET DLL への参照を追加する必要があります。

## ステップ2: PDFドキュメントを読み込む

 Aspose.PDF for .NETをインストールし、.NETプロジェクトにDLLへの参照を追加したら、`GetFileInfo` PDF ドキュメントのメタデータに関する情報を取得する機能。

この機能を使用するための最初のステップは、情報を取得する PDF ドキュメントを読み込むことです。これを行うには、次のコードを使用します。

```csharp
// PDF文書へのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF文書を開く
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");
```

上記のコードでは、`"YOUR DOCUMENT DIRECTORY"` PDF文書があるディレクトリへのパスを入力します。このコードはPDF文書を`Document`オブジェクトを使用して、ドキュメントのメタデータに関する情報を取得できます。

## ステップ3: ドキュメントのメタデータを取得する

PDF ドキュメントのメタデータに関する情報を取得するには、次のコードを使用できます。

```csharp
//ドキュメント情報を取得する
DocumentInfo docInfo = pdfDocument.Info;

//ドキュメント情報を表示
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

上記のコードでは、各行で PDF ドキュメントの異なるメタデータ プロパティを取得し、コンソールに出力します。このコードをカスタマイズして、必要なプロパティのみを取得できます。

### Aspose.PDF for .NET を使用して PDF ファイル情報を取得するサンプル ソース コード

以下はPDF文書のメタデータを取得するための完全なソースコードです。`GetFileInfo` Aspose.PDF for .NET の機能:

```csharp
// PDF文書へのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF文書を開く
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");

//ドキュメント情報を取得する
DocumentInfo docInfo = pdfDocument.Info;

//ドキュメント情報を表示
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントのメタデータに関する情報を取得する方法について説明しました。PDF ドキュメントを読み込み、そのメタデータ プロパティにアクセスすることで、ドキュメントの特性とプロパティに関する情報を収集できます。Aspose.PDF for .NET は、メタデータ情報の取得など、PDF ドキュメントを操作するためのシンプルで使いやすい API を提供するため、.NET アプリケーションで PDF を操作するための貴重なツールとなります。

### よくある質問

#### Q: PDF ドキュメントのメタデータとは何ですか?

A: PDF ドキュメントのメタデータとは、ドキュメントのプロパティと特徴を説明する情報のことです。この情報には通常、ドキュメントのタイトル、作成者、件名、キーワード、作成日、変更日などが含まれます。

#### Q: .NET プロジェクトに Aspose.PDF for .NET をインストールするにはどうすればよいですか?

 A: Aspose.PDF for .NETをインストールするには、以下のサイトからライブラリをダウンロードする必要があります。[Aspose.PDF for .NET ダウンロード ページ](https://releases.aspose.com/pdf/net)ダウンロード後、ZIP ファイルの内容を抽出し、.NET プロジェクトに Aspose.PDF for .NET DLL への参照を追加します。

#### Q: 特定のメタデータ プロパティのみを取得するようにコードをカスタマイズできますか?

A: はい、不要な行をコメント アウトすることで、特定のメタデータ プロパティを取得するようにコードをカスタマイズできます。コード内の各行は特定のメタデータ プロパティに対応しているため、要件に基づいてプロパティを含めたり除外したりできます。

#### Q: Aspose.PDF for .NET を使用して取得できるメタデータ プロパティの種類は何ですか?

A: Aspose.PDF for .NET を使用すると、作成者、タイトル、件名、キーワード、作成日、変更日など、PDF ドキュメントのさまざまなメタデータ プロパティを取得できます。