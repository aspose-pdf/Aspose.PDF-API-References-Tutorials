---
title: フォントの埋め込みを解除して PDF ファイルを最適化する
linktitle: フォントの埋め込みを解除して PDF ファイルを最適化する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して埋め込みフォントを取得し、PDF ファイルを最適化する方法を学びます。ステップバイステップ ガイド。
type: docs
weight: 370
url: /ja/net/programming-with-document/unembedfonts/
---
Aspose.PDF for .NET は、PDF ドキュメントを操作するための幅広い機能を提供する強力なライブラリです。その機能の 1 つは、PDF ドキュメントから埋め込み解除されたフォントを取得することです。これは、PDF ドキュメントからフォントを抽出して他のアプリケーションで使用する必要がある場合に役立ちます。

Aspose.PDF for .NET の埋め込みフォント取得機能の次の C# ソース コードを説明するステップ バイ ステップ ガイドを提供します。

## ステップ1: ドキュメントディレクトリへのパスを設定する

始める前に、PDF ドキュメントが保存されているディレクトリへのパスを設定する必要があります。このパスは、「dataDir」という変数に保存します。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

「YOUR DOCUMENT DIRECTORY」を、PDF ドキュメントが保存されているディレクトリへの実際のパスに置き換えます。

## ステップ2: PDFドキュメントを開く

最初のステップは、これを行うPDF文書を読み込むことです。`Document` Aspose.PDF for .NET のクラス。次のコード スニペットは、PDF ドキュメントを読み込む方法を示しています。

```csharp
//ドキュメントを開く
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## ステップ3: UnembedFontsオプションを設定する

PDF文書から埋め込みフォントを取得するには、`UnembedFonts`オプション`true`このオプションは、`OptimizationOptions`クラス。次のコードスニペットは、`UnembedFonts`オプション：

```csharp
// UnembedFontsオプションを設定する
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## ステップ4: PDFドキュメントを最適化する

設定後`UnembedFonts`オプションを使用すると、PDF文書を`OptimizeResources`方法の`Document`クラス。次のコード スニペットは、PDF ドキュメントを最適化する方法を示しています。

```csharp
// OptimizationOptionsを使用してPDFドキュメントを最適化する
pdfDocument.OptimizeResources(optimizeOptions);
```

## ステップ5: 更新したドキュメントを保存する

 PDF文書が最適化されたら、`Save`方法の`Document`クラス。次のコード スニペットは、更新されたドキュメントを保存する方法を示しています。

```csharp
//更新されたドキュメントを保存する
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## ステップ6: 元のファイルサイズと縮小されたファイルサイズを取得する

最後に、PDF文書の元のファイルサイズと縮小されたファイルサイズを取得するには、`FileInfo` System.IO のクラスです。次のコード スニペットは、元のファイル サイズと縮小されたファイル サイズを取得する方法を示しています。

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### Aspose.PDF for .NET を使用して埋め込みフォントを取得するためのサンプル ソース コード

以下は、Aspose.PDF for .NET を使用して PDF ドキュメントから埋め込みフォントを取得するための完全なサンプル ソース コードです。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントを開く
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// UnembedFontsオプションを設定する
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
Console.WriteLine("Start");
// OptimizationOptionsを使用してPDFドキュメントを最適化する
pdfDocument.OptimizeResources(optimizeOptions);
//更新されたドキュメントを保存する
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントから埋め込み解除されたフォントを取得する方法を説明しました。ステップ バイ ステップ ガイドに従うことで、この機能を C# アプリケーションに簡単に実装できます。フォントの埋め込み解除は、抽出されたフォントを個別に操作する必要がある場合や、さまざまなプラットフォーム間で一貫したフォント使用を確保する必要がある場合に便利です。

## よくある質問

#### Q: PDF ドキュメントからフォントの埋め込みを解除する目的は何ですか?

A: PDF ドキュメントからフォントの埋め込みを解除すると、埋め込まれたフォントを抽出して他のアプリケーションで使用できるようになります。これは、一貫したフォント レンダリングを保証し、ドキュメントの外観を維持するのに役立ちます。

#### Q: C# コードでドキュメント ディレクトリへのパスを指定するにはどうすればよいですか?

 A: ドキュメントディレクトリへのパスを指定するには、`"YOUR DOCUMENT DIRECTORY"`コード内に、PDF ドキュメントが配置されているディレクトリへの実際のパスを含めます。

####  Q:`UnembedFonts` option do, and where is it set?

 A:`UnembedFonts`オプションは、`OptimizationOptions`クラスは、PDF文書からフォントの埋め込み解除を有効または無効にします。このオプションを`true`次のコードを使用します。

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### Q: 最適化プロセス中に行った変更を元に戻すことはできますか?

A: Aspose.PDF for .NET は、最適化中に元の PDF ドキュメントに永続的な変更を加えません。最適化プロセスはドキュメントのコピーに対して実行され、元のドキュメントはそのまま残ります。

#### Q: 最適化後の元のファイルサイズと縮小されたファイルサイズを確認するにはどうすればよいですか?

 A:`FileInfo`クラスの`System.IO`元のファイル サイズと縮小されたファイル サイズを取得します。これを実現するためのサンプル コード スニペットを次に示します。

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```