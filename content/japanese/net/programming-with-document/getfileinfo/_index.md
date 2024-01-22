---
title: PDF ファイルのファイル情報を取得する
linktitle: PDF ファイルのファイル情報を取得する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET の PDF ファイル機能の GetFileInfo を使用して、PDF ドキュメントに関するメタデータ情報を取得する方法を説明します。
type: docs
weight: 180
url: /ja/net/programming-with-document/getfileinfo/
---
 Aspose.PDF for .NET は、開発者が .NET アプリケーションで PDF ファイルを作成、編集、変換できるようにする人気の PDF 操作ライブラリです。このライブラリが提供する機能の 1 つは、PDF ドキュメントのメタデータに関する情報を取得する機能です。このチュートリアルでは、`GetFileInfo` Aspose.PDF for .NET の機能を使用して、PDF ドキュメントのメタデータに関する情報を取得します。

## ステップ 1: Aspose.PDF for .NET をインストールする

 .NET アプリケーションで Aspose.PDF for .NET を使用するには、まずライブラリをインストールする必要があります。ライブラリの最新バージョンは、次の場所からダウンロードできます。[Aspose.PDF for .NET ダウンロード ページ](https://releases.aspose.com/pdf/net).

ライブラリをダウンロードしたら、ZIP ファイルの内容をコンピュータ上のフォルダに抽出します。次に、.NET プロジェクトに Aspose.PDF for .NET DLL への参照を追加する必要があります。

## ステップ 2: PDF ドキュメントをロードする

Aspose.PDF for .NET をインストールし、.NET プロジェクトに DLL への参照を追加すると、`GetFileInfo` PDF ドキュメントのメタデータに関する情報を取得する機能。

この機能を使用する最初のステップは、情報を取得する PDF ドキュメントをロードすることです。これを行うには、次のコードを使用できます。

```csharp
// PDF ドキュメントへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

//PDF ドキュメントを開く
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");
```

上記のコードでは、次のように置き換えます。`"YOUR DOCUMENT DIRECTORY"` PDF ドキュメントが置かれているディレクトリへのパスを置き換えます。このコードは PDF ドキュメントを`Document`オブジェクトを使用して、ドキュメントのメタデータに関する情報を取得できます。

## ステップ 3: ドキュメントのメタデータを取得する

PDF ドキュメントのメタデータに関する情報を取得するには、次のコードを使用できます。

```csharp
//文書情報の取得
DocumentInfo docInfo = pdfDocument.Info;

//文書情報を表示する
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

上記のコードでは、各行が PDF ドキュメントの異なるメタデータ プロパティを取得し、コンソールに出力します。このコードをカスタマイズして、関心のあるプロパティのみを取得することができます。

### Aspose.PDF for .NET を使用して PDF ファイル情報を取得するソース コードの例

以下は、PDF ドキュメントのメタデータを取得するための完全なソース コードです。`GetFileInfo` Aspose.PDF for .NET の機能:

```csharp
// PDF ドキュメントへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

//PDF ドキュメントを開く
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");

//文書情報の取得
DocumentInfo docInfo = pdfDocument.Info;

//文書情報を表示する
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントのメタデータに関する情報を取得する方法について説明しました。 PDF ドキュメントをロードし、そのメタデータ プロパティにアクセスすると、ドキュメントの特性とプロパティに関する情報を収集できます。 Aspose.PDF for .NET は、メタデータ情報の取得など、PDF ドキュメントを操作するためのシンプルで使いやすい API を提供し、.NET アプリケーションで PDF を操作するための貴重なツールとなります。

### よくある質問

#### Q: PDF ドキュメントのメタデータとは何ですか?

A: PDF ドキュメント内のメタデータは、ドキュメントのプロパティと特性を説明する情報を指します。通常、この情報には、ドキュメントのタイトル、作成者、件名、キーワード、作成日、変更日などが含まれます。

#### Q: Aspose.PDF for .NET を .NET プロジェクトにインストールするにはどうすればよいですか?

 A: Aspose.PDF for .NET をインストールするには、次の場所からライブラリをダウンロードする必要があります。[Aspose.PDF for .NET ダウンロード ページ](https://releases.aspose.com/pdf/net)。ダウンロード後、ZIP ファイルの内容を抽出し、.NET プロジェクト内の Aspose.PDF for .NET DLL への参照を追加します。

#### Q: 特定のメタデータ プロパティのみを取得するようにコードをカスタマイズできますか?

A: はい、必要のない行をコメント アウトすることで、コードをカスタマイズして特定のメタデータ プロパティを取得できます。コードの各行は特定のメタデータ プロパティに対応するため、要件に基づいてプロパティを含めたり除外したりできます。

#### Q: Aspose.PDF for .NET を使用して取得できるメタデータ プロパティの種類は何ですか?

A: Aspose.PDF for .NET を使用すると、作成者、タイトル、件名、キーワード、作成日、変更日など、PDF ドキュメントのさまざまなメタデータ プロパティを取得できます。