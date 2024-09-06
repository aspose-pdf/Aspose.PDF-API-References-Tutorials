---
title: PDF ファイルに XMPMetadata を設定する
linktitle: PDF ファイルに XMPMetadata を設定する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルに XMPMetadata を設定する方法を学びます。このステップバイステップ ガイドに従ってください。
type: docs
weight: 330
url: /ja/net/programming-with-document/setxmpmetadata/
---
この記事では、Aspose.PDF for .NET を使用して PDF ファイルに XMP メタデータを設定する方法について、ステップ バイ ステップ ガイドを提供します。記事の最後に、完全なサンプル ソース コードを提供します。

## ステップ1: ドキュメントディレクトリへのパスを設定する

始める前に、PDF ドキュメントが保存されているディレクトリへのパスを設定する必要があります。このパスは、「dataDir」という変数に保存します。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

必ず交換してください`YOUR DOCUMENT DIRECTORY` PDF ファイルへの実際のパスを入力します。

## ステップ2: PDFファイルを開く

最初のステップは、XMPメタデータを設定するPDFファイルを開くことです。これを行うには、新しい`Document`オブジェクトを作成し、PDF ファイルへのパスを渡します。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//ドキュメントを開く
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");
```

## ステップ3: XMPメタデータプロパティを設定する

PDF ファイルを開いたら、XMP メタデータ プロパティの設定を開始できます。設定するプロパティは特定のニーズによって異なりますが、設定するとよい一般的なプロパティを次に示します。

- `xmp:CreateDate`: PDF ファイルの作成日。
- `xmp:Nickname`: PDF ファイルのニックネームまたはエイリアス。
- `xmp:CustomProperty`: 指定した値を持つカスタム プロパティ。

これらのプロパティを設定するには、`Metadata`の財産`Document`オブジェクト。次に例を示します。

```csharp
//プロパティを設定する
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";
```

このチュートリアルでは、作成日を現在の日時、ニックネームを「ニックネーム」、カスタム プロパティを「カスタム値」に設定します。これらの値は独自の値に置き換えることができます。

## ステップ4: PDFファイルを保存する

XMPメタデータプロパティを設定したら、PDFファイルを保存する必要があります。これを行うには、`Save`方法の`Document`オブジェクトを追加し、更新された PDF ファイルを保存する場所へのパスを渡します。

```csharp
dataDir = dataDir + "SetXMPMetadata_out.pdf";
//ドキュメントを保存
pdfDocument.Save(dataDir);
```

### Aspose.PDF for .NET を使用して XMPMetadata を設定するためのサンプル ソース コード

Aspose.PDF for .NET を使用して XMPMetadata を設定するための完全なサンプル ソース コードは次のとおりです。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//ドキュメントを開く
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");

//プロパティを設定する
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";

dataDir = dataDir + "SetXMPMetadata_out.pdf";
//ドキュメントを保存
pdfDocument.Save(dataDir);

Console.WriteLine("\nXMP metadata in a pdf file setup successfully.\nFile saved at " + dataDir);
```

## 結論

Aspose.PDF for .NET は、PDF ファイルに XMP メタデータを設定する簡単な方法を提供し、ドキュメントに説明情報やプロパティを追加できるようにします。上記のステップ バイ ステップ ガイドでは、C# ソース コードを使用してさまざまな XMP メタデータ プロパティを設定する方法を説明しています。さらに、特定のニーズやビジネス要件に合わせて XMP メタデータをカスタマイズすることもできます。Aspose.PDF for .NET を使用すると、PDF メタデータの管理が効率化され、PDF ドキュメントの整理と検索性が向上します。

### PDF ファイルに XMPMetadata を設定するための FAQ

#### Q: PDF ファイル内の XMP メタデータとは何ですか? また、なぜ重要ですか?

A: XMP (Extensible Metadata Platform) は、PDF を含むさまざまなファイル形式にメタデータを埋め込むための標準です。PDF ファイルの XMP メタデータを使用すると、作成日、作成者、タイトル、キーワード、カスタム プロパティなどの説明情報やプロパティをドキュメントに追加できます。これは、PDF ドキュメントの整理、検索、アーカイブを向上させるために不可欠です。

#### Q: 例に記載されているもの以外に、他の XMP メタデータ プロパティを設定できますか?

 A: はい、特定の要件に応じて、幅広いXMPメタデータプロパティを設定できます。一般的なプロパティには次のものがあります。`dc:title` (文書タイトル)、`dc:creator` （文書作成者）、`dc:description` （文書の説明）、`pdf:Keywords` (ドキュメント キーワード) など。XMP 仕様では、さまざまな種類のメタデータを設定するためのさまざまな標準名前空間とカスタム名前空間が提供されています。

#### Q: 既存の PDF ファイルから XMP メタデータを取得して読み取ることは可能ですか?

 A: はい、Aspose.PDF for .NETは既存のPDFファイルからXMPメタデータを読み込んで取得する機能を提供します。`Metadata`の財産`Document` XMP メタデータにアクセスし、特定のプロパティの値を取得するためのクラス。