---
title: PDF ファイルに XMPMetadata を設定する
linktitle: PDF ファイルに XMPMetadata を設定する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルに XMPMetadata を設定する方法を学習します。このステップバイステップのガイドに従ってください。
type: docs
weight: 330
url: /ja/net/programming-with-document/setxmpmetadata/
---
この記事では、Aspose.PDF for .NET を使用して PDF ファイルに XMP メタデータを設定する方法についてステップバイステップのガイドを提供します。記事の最後に完全なソース コードの例を示します。

## ステップ 1: ドキュメント ディレクトリへのパスを設定する

始める前に、PDF ドキュメントが配置されているディレクトリへのパスを設定する必要があります。このパスを「dataDir」という変数に保存します。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

必ず交換してください`YOUR DOCUMENT DIRECTORY` PDF ファイルへの実際のパスを含めます。

## ステップ 2: PDF ファイルを開く

最初のステップは、XMP メタデータを設定する PDF ファイルを開くことです。これを行うには、新しいファイルを作成する必要があります`Document`オブジェクトを指定し、PDF ファイルへのパスを渡します。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//開いた文書
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");
```

## ステップ 3: XMP メタデータのプロパティを設定する

PDF ファイルを開いたので、XMP メタデータ プロパティの設定を開始できます。設定するプロパティは特定のニーズによって異なりますが、設定する必要がある一般的なプロパティをいくつか示します。

- `xmp:CreateDate`：PDFファイルの作成日。
- `xmp:Nickname`: PDF ファイルのニックネームまたはエイリアス。
- `xmp:CustomProperty`: 値を指定したカスタム プロパティ。

これらのプロパティを設定するには、`Metadata`の財産`Document`物体。以下に例を示します。

```csharp
//プロパティを設定する
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";
```

このチュートリアルでは、作成日を現在の日時に設定し、ニックネームを「ニックネーム」に、カスタム プロパティを「カスタム値」に設定します。これらの値を独自の値に置き換えることができます。

## ステップ 4: PDF ファイルを保存する

 XMP メタデータ プロパティを設定した後、PDF ファイルを保存する必要があります。これを行うには、`Save`の方法`Document`オブジェクトを指定し、更新された PDF ファイルを保存する場所へのパスを渡します。

```csharp
dataDir = dataDir + "SetXMPMetadata_out.pdf";
//文書の保存
pdfDocument.Save(dataDir);
```

### Aspose.PDF for .NET を使用した Set XMPMetadata のソース コード例

Aspose.PDF for .NET を使用して XMPMetadata を設定するための完全なソース コードの例を次に示します。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//開いた文書
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");

//プロパティを設定する
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";

dataDir = dataDir + "SetXMPMetadata_out.pdf";
//文書の保存
pdfDocument.Save(dataDir);

Console.WriteLine("\nXMP metadata in a pdf file setup successfully.\nFile saved at " + dataDir);
```

## 結論

Aspose.PDF for .NET は、PDF ファイルに XMP メタデータを設定する簡単な方法を提供し、説明情報とプロパティをドキュメントに追加できるようにします。上記のステップバイステップ ガイドでは、C# ソース コードを使用してさまざまな XMP メタデータ プロパティを設定する方法を示します。さらに、特定のニーズやビジネス要件に合わせて XMP メタデータをカスタマイズできます。 Aspose.PDF for .NET を使用すると、PDF メタデータの管理が効率的になり、PDF ドキュメントの整理と検索が容易になります。

### PDF ファイルに XMPMetadata を設定するための FAQ

#### Q: PDF ファイル内の XMP メタデータとは何ですか?なぜ重要ですか?

A: XMP (Extensible Metadata Platform) は、PDF を含むさまざまなファイル形式にメタデータを埋め込むための標準です。 PDF ファイル内の XMP メタデータを使用すると、作成日、作成者、タイトル、キーワード、カスタム プロパティなどの説明情報とプロパティをドキュメントに追加できます。これは、PDF ドキュメントの整理、検索性、およびアーカイブを改善するために不可欠です。

#### Q: 例で挙げたもの以外の XMP メタデータ プロパティを設定できますか?

 A: はい、特定の要件に応じて、幅広い XMP メタデータ プロパティを設定できます。いくつかの一般的なプロパティには次のものがあります。`dc:title` （ドキュメントのタイトル）、`dc:creator` (文書作成者)、`dc:description` (文書の説明)、`pdf:Keywords` (ドキュメントのキーワード) など。 XMP 仕様では、さまざまなタイプのメタデータを設定するためのさまざまな標準名前空間とカスタム名前空間が提供されています。

#### Q: 既存の PDF ファイルから XMP メタデータを取得して読み取ることはできますか?

 A: はい、Aspose.PDF for .NET は、既存の PDF ファイルから XMP メタデータを読み取って取得する機能を提供します。使用できます`Metadata`の財産`Document`クラスを使用して XMP メタデータにアクセスし、特定のプロパティの値を取得します。