---
title: PDF から PDFA3b
linktitle: PDF から PDFA3b
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF を PDF/A-3b に変換するためのステップバイステップ ガイド。
type: docs
weight: 150
url: /ja/net/document-conversion/pdf-to-pdfa3b/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルを PDF/A-3b 形式に変換するプロセスを説明します。 PDF/A-3b は、PDF ドキュメントにファイルとデータを埋め込むための ISO 標準です。以下の手順に従って、PDF ファイルを PDF/A-3b 形式に変換できます。

## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。

- C# プログラミング言語の基本的な知識。
- .NET 用の Aspose.PDF ライブラリがシステムにインストールされています。
- Visual Studio などの開発環境。

## ステップ 1: ソース PDF ドキュメントを開く
このステップでは、Aspose.PDF for .NET を使用してソース PDF ファイルを開きます。以下のコードに従ってください。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ソース PDF ドキュメントを開きます
Document pdfDocument = new Document(dataDir + "input.pdf");
```

必ず交換してください`"YOUR DOCUMENTS DIRECTORY"`PDF ファイルが置かれている実際のディレクトリに置き換えます。

## ステップ 2: PDF/A-3b に変換する
PDF ファイルを開いた後、PDF/A-3b 形式への変換を続行できます。次のコードを使用します。

```csharp
// PDF/A-3b形式に変換
pdfDocument.Convert(new MemoryStream(), PdfFormat.PDF_A_3B, ConvertErrorAction.Delete);
```

上記のコードは、PDF ファイルを PDF/A-3b 形式に変換し、変換エラーを除去します。

## ステップ 3: 結果の PDF/A-3b ファイルを保存する
変換が完了したら、結果の PDF/A-3b ファイルを保存する必要があります。最後のステップは次のとおりです。

```csharp
dataDir = dataDir + "PDFToPDFA3b_out.pdf";
//出力ドキュメントを保存する
pdfDocument.Save(dataDir);
```

交換する`"YOUR DOCUMENTS DIRECTORY"`出力 PDF/A-3b ファイルを保存するディレクトリを指定します。

### Aspose.PDF for .NET を使用した PDF から PDFA3b へのソース コードの例

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//開いた文書
Document pdfDocument = new Document(dataDir + "input.pdf");            

pdfDocument.Convert(new MemoryStream(), PdfFormat.PDF_A_3B, ConvertErrorAction.Delete);

dataDir = dataDir + "PDFToPDFA3b_out.pdf";
//出力ドキュメントを保存する
pdfDocument.Save(dataDir);

Console.WriteLine("\nPDF file converted to PDF/A-3B format.\nFile saved at " + dataDir);
```

## 結論
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルを PDF/A-3b 形式に変換する段階的なプロセスについて説明しました。上記の手順に従うことで、PDF ファイルを PDF/A-3b 形式に変換できるようになります。この機能は、PDF/A-3b 標準に準拠する PDF ドキュメントに追加のファイルやデータを埋め込む場合に便利です。

### よくある質問

#### Q: PDF/A-3b とは何ですか?また、他の PDF/A 標準との違いは何ですか?

A: PDF/A-3b は、PDF ドキュメントにファイルとデータを埋め込み、PDF ドキュメントを自己完結型にして長期保存を保証する ISO 標準です。 PDF/A-1 や PDF/A-2 などの他の PDF/A 標準とは異なり、PDF/A-3b では、PDF ドキュメント内に追加のファイルやデータを含めることができます。この機能により、複雑でインタラクティブなドキュメントのアーカイブと交換に適しています。

#### Q: PDF/A-3b ドキュメント内に複数のファイルやデータを含めることはできますか?

A: はい、PDF/A-3b の主な利点の 1 つは、PDF ドキュメント内に複数のファイルとデータを含めることができることです。メインの PDF コンテンツに加えて、XML、スプレッドシート、画像、その他の PDF ファイルなど、さまざまなタイプのファイルを埋め込むことができます。その結果、PDF/A-3b ドキュメントは、必要な要素をすべて含む自己完結型のパッケージになります。

#### Q: PDF から PDF/A-3b への変換プロセス中にエラーが発生した場合はどうなりますか?

 A: Aspose.PDF for .NET を使用して PDF を PDF/A-3b 形式に変換する場合、エラーの処理方法を制御できます。の`Convert`メソッドの`ConvertErrorAction`パラメータは、エラーが発生したときに実行するアクションを決定します。提供されたコード例では、`ConvertErrorAction.Delete`パラメータが使用されます。これは、変換中にエラーが発生すると、エラーのあるページが削除されることを意味します。

#### Q: PDF/A-3b は文書の長期保存に適していますか?

A: はい、PDF/A-3b は電子文書の長期保存用に特別に設計されています。追加のファイルとデータを埋め込むことで、必要なすべてのコンポーネントが PDF ドキュメント自体に確実に含まれるようになり、時間の経過とともに情報損失や外部依存関係のリスクが軽減されます。この機能により、長期的なアクセス性と一貫性を保証する方法でドキュメントをアーカイブするのに適しています。