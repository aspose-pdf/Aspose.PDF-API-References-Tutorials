---
title: PDF ファイルにファイル情報を設定する
linktitle: PDF ファイルにファイル情報を設定する
second_title: Aspose.PDF for .NET API リファレンス
description: このステップバイステップ ガイドでは、Aspose.PDF for .NET を使用して PDF ファイルにファイル情報を設定する方法を学習します。
type: docs
weight: 310
url: /ja/net/programming-with-document/setfileinfo/
---
Aspose.PDF for .NET を使用して PDF ファイルを管理するプロジェクトに取り組んでいる場合、PDF ドキュメントのファイル情報を設定する機能を利用するとよいでしょう。ファイル情報には、作成者、作成日、キーワード、変更日、件名、タイトルなどのさまざまな詳細が含まれます。このガイドでは、Aspose.PDF for .NET で C# ソース コードを使用して PDF ドキュメントのファイル情報を設定する手順について説明します。

## Aspose.PDF for .NET を使用してファイル情報を設定する手順ガイド

1. Visual Studio IDE で新しい C# プロジェクトを作成します。
2. プロジェクトに Aspose.PDF for .NET ライブラリへの参照を追加します。
3. ファイル情報を変更する PDF ファイルへのパスを指定して、新しい PDF ドキュメント オブジェクトを作成します。

## ステップ 1: ドキュメント ディレクトリへのパスを設定します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ2: PDF文書を開く

```csharp
//ドキュメントを開く
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## ステップ 3: DocumentInfo オブジェクトを使用して、PDF ドキュメントのファイル情報にアクセスします。

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## 手順 4: DocumentInfo オブジェクトのプロパティを使用して、必要なファイル情報の値を設定します。

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

## ステップ 5: 更新された PDF ドキュメントを指定された場所に保存します。

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
pdfDocument.Save(dataDir);
```

## 手順 6: ファイル情報が正常に更新されたことを確認します。

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

Aspose.PDF for .NET を使用して PDF ドキュメントのファイル情報を正常に設定しました。

### Aspose.PDF for .NET を使用してファイル情報を設定するサンプル ソース コード


```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//ドキュメントを開く
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");

//文書情報を指定する
DocumentInfo docInfo = new DocumentInfo(pdfDocument);

docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";

dataDir = dataDir + "SetFileInfo_out.pdf";
//出力ドキュメントを保存する
pdfDocument.Save(dataDir);

Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

## 結論

結論として、Aspose.PDF for .NET は、PDF ドキュメントのファイル情報を設定するシンプルで効果的な方法を提供します。上記の手順に従うことで、C# ソース コードを使用して PDF ドキュメントに必要なファイル情報の値を簡単に設定できます。

### PDF ファイル内のファイル情報の設定に関する FAQ

#### Q: 例に記載されていない追加のファイル情報プロパティを設定できますか?

 A: はい、追加のファイル情報プロパティを設定するには、`DocumentInfo` Aspose.PDF for .NETのオブジェクト。`DocumentInfo`クラスには、プロデューサー、バージョン、カスタム プロパティなどの追加情報を設定できるさまざまなプロパティが用意されています。

#### Q: 既存の PDF ドキュメントからファイル情報を取得することは可能ですか?

 A: はい、Aspose.PDF for .NETを使用して既存のPDFドキュメントからファイル情報を取得できます。これを行うには、`DocumentInfo`オブジェクトを使用してファイル情報プロパティにアクセスし、PDF ドキュメントに保存されている情報を読み込みます。

#### Q: ファイル情報を設定すると、元の PDF ドキュメントは変更されますか?

A: いいえ、Aspose.PDF for .NET を使用してファイル情報を設定しても、元の PDF ドキュメントは変更されません。代わりに、更新されたファイル情報を含む新しい PDF ドキュメントが作成されます。元の PDF ドキュメントは変更されません。