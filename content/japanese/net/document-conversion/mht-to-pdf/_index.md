---
title: MHTからPDFへ
linktitle: MHTからPDFへ
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して MHT を PDF に変換するためのステップバイステップ ガイド。
type: docs
weight: 70
url: /ja/net/document-conversion/mht-to-pdf/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して MHT ファイルを PDF に変換するプロセスを説明します。 MHT (MIME HTML) は、画像や関連コンテンツを含む完全な Web ページを保存するために使用される形式です。以下の手順に従って、MHT ファイルを PDF 形式に変換できます。

## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。

- C# プログラミング言語の基本的な知識。
- .NET 用の Aspose.PDF ライブラリがシステムにインストールされています。
- Visual Studio などの開発環境。

## ステップ 1: MHT ファイルをロードする
このステップでは、Aspose.PDF for .NET を使用して MHT ファイルをロードします。以下のコードに従ってください。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

MhtLoadOptions options = new MhtLoadOptions();

//ドキュメントをロードします
Document document = new Document(dataDir + "test.mht", options);
```

必ず交換してください`"YOUR DOCUMENTS DIRECTORY"`MHT ファイルが存在する実際のディレクトリに置き換えます。

## ステップ 2: MHT から PDF への変換
MHT ファイルをロードした後、PDF への変換を続行できます。次のコードを使用します。

```csharp
//出力を PDF ドキュメントとして保存する
document.Save(dataDir + "MHTToPDF_out.pdf");
```

上記のコードは、MHT ファイルを PDF 形式に変換し、ファイル名として保存します。`"MHTToPDF_out.pdf"`.

### Aspose.PDF for .NET を使用した MHT から PDF へのソース コードの例

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
MhtLoadOptions options = new MhtLoadOptions();
//ドキュメントをロードする
Document document = new Document(dataDir  + "test.mht", options);
//出力を PDF ドキュメントとして保存する
document.Save(dataDir + "MHTToPDF_out.pdf");
```

## 結論
このチュートリアルでは、Aspose.PDF for .NET を使用して MHT ファイルを PDF に変換する段階的なプロセスについて説明しました。上記の手順に従うことで、MHT ファイルを PDF 形式に変換できるようになります。この機能は、Web ページ全体を PDF ドキュメントに変換する必要がある場合に役立ちます。

### よくある質問

#### Q: Aspose.PDF for .NET は、画像が埋め込まれた MHT ファイルの PDF への変換をサポートしていますか?

A: はい、Aspose.PDF for .NET は、画像が埋め込まれた MHT ファイルの PDF への変換をサポートしています。このライブラリは、画像や関連リソースを含む完全な Web ページ コンテンツを処理し、PDF ドキュメントに変換できます。

#### Q: MHT から PDF への変換プロセス中に PDF 出力をカスタマイズできますか?

A: はい、Aspose.PDF for .NET には、MHT から PDF への変換プロセス中に PDF 出力をカスタマイズするためのさまざまなオプションが用意されています。ページ サイズ、向き、余白などのプロパティを設定して、生成される PDF ドキュメントの外観を制御できます。

#### Q: Aspose.PDF for .NET は、元の MHT ファイルのハイパーリンクと書式設定を PDF 出力に保持しますか?

A: はい、Aspose.PDF for .NET は、元の MHT ファイルのハイパーリンクと書式設定を PDF 出力に保持します。このライブラリは、変換された PDF がソース MHT ファイルと同じレイアウトとコンテンツを保持することを保証します。

#### Q: Aspose.PDF for .NET を使用して、複数の MHT ファイルを個別の PDF ドキュメントに変換できますか?

A: はい、Aspose.PDF for .NET を使用して、複数の MHT ファイルを個別の PDF ドキュメントに変換できます。各 MHT ファイルをロードし、一意のファイル名を付けて個別の PDF ドキュメントとして保存するだけです。