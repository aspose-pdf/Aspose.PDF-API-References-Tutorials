---
title: フォントの埋め込みを解除し、PDF ファイルを最適化する
linktitle: フォントの埋め込みを解除し、PDF ファイルを最適化する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して非埋め込みフォントを取得し、PDF ファイルを最適化する方法を学びます。ステップバイステップのガイド。
type: docs
weight: 370
url: /ja/net/programming-with-document/unembedfonts/
---
Aspose.PDF for .NET は、PDF ドキュメントを操作するための幅広い機能を提供する強力なライブラリです。その機能の 1 つは、PDF ドキュメントからフォントの埋め込みを解除することです。これは、PDF ドキュメントからフォントを抽出して他のアプリケーションで使用する必要がある場合に役立ちます。

Aspose.PDF for .NET の埋め込み解除フォントの取得機能の次の C# ソース コードを説明するステップバイステップ ガイドを提供します。

## ステップ 1: ドキュメント ディレクトリへのパスを設定する

始める前に、PDF ドキュメントが配置されているディレクトリへのパスを設定する必要があります。このパスを「dataDir」という変数に保存します。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

「YOUR DOCUMENT DIRECTORY」を、PDF ドキュメントが配置されているディレクトリへの実際のパスに置き換えます。

## ステップ 2: PDF ドキュメントを開く

最初のステップは、これを行う PDF ドキュメントをロードすることです。`Document` Aspose.PDF for .NET のクラス。次のコード スニペットは、PDF ドキュメントをロードする方法を示しています。

```csharp
//開いた文書
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## ステップ 3: UnembedFonts オプションを設定する

PDF ドキュメントからフォントの埋め込みを解除するには、`UnembedFonts`というオプション`true`。このオプションは、`OptimizationOptions`クラス。次のコード スニペットは、`UnembedFonts`オプション：

```csharp
// UnembedFonts オプションを設定する
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## ステップ 4: PDF ドキュメントを最適化する

を設定した後、`UnembedFonts`オプションを使用すると、PDF ドキュメントを最適化できます。`OptimizeResources`の方法`Document`クラス。次のコード スニペットは、PDF ドキュメントを最適化する方法を示しています。

```csharp
//OptimizationOptions を使用して PDF ドキュメントを最適化する
pdfDocument.OptimizeResources(optimizeOptions);
```

## ステップ 5: 更新されたドキュメントを保存する

 PDF ドキュメントが最適化されたら、更新されたドキュメントを保存できます。`Save`の方法`Document`クラス。次のコード スニペットは、更新されたドキュメントを保存する方法を示しています。

```csharp
//更新されたドキュメントを保存する
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## ステップ 6: 元のファイル サイズと縮小されたファイル サイズを取得する

最後に、`FileInfo` System.IO のクラス。次のコード スニペットは、元のファイル サイズと縮小されたファイル サイズを取得する方法を示しています。

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### Aspose.PDF for .NET を使用して非埋め込みフォントを取得するためのソース コードの例

Aspose.PDF for .NET を使用して PDF ドキュメントから埋め込み解除されたフォントを取得するための完全なソース コードの例を次に示します。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開いた文書
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// UnembedFonts オプションを設定する
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
Console.WriteLine("Start");
//OptimizationOptions を使用して PDF ドキュメントを最適化する
pdfDocument.OptimizeResources(optimizeOptions);
//更新されたドキュメントを保存する
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントからフォントの埋め込みを解除する方法を説明しました。ステップバイステップのガイドに従うことで、この機能を C# アプリケーションに簡単に実装できます。フォントの非埋め込みは、抽出したフォントを個別に操作する必要がある場合や、さまざまなプラットフォーム間で一貫したフォントの使用を確保する必要がある場合に有利です。

## よくある質問

#### Q: PDF ドキュメントからフォントの埋め込みを解除する目的は何ですか?

A: PDF ドキュメントからフォントの埋め込みを解除すると、埋め込まれたフォントを抽出して他のアプリケーションで使用できるようになります。これは、一貫したフォントのレンダリングを確保し、ドキュメントの外観を維持するのに役立ちます。

#### Q: C# コードでドキュメント ディレクトリへのパスを指定するにはどうすればよいですか?

 A: ドキュメント ディレクトリへのパスを指定するには、次のように置き換えます。`"YOUR DOCUMENT DIRECTORY"`コードでは、PDF ドキュメントが配置されているディレクトリへの実際のパスを含めます。

####  Q: とは何ですか?`UnembedFonts` option do, and where is it set?

 A:`UnembedFonts`オプション、で利用可能`OptimizationOptions`クラスで、PDF ドキュメントからのフォントの埋め込み解除を有効または無効にします。このオプションを次のように設定するには`true`、次のコードを使用します。

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### Q: 最適化プロセス中に加えた変更を元に戻すことはできますか?

A: Aspose.PDF for .NET は、最適化中に元の PDF ドキュメントに永続的な変更を加えません。最適化プロセスはドキュメントのコピーに対して実行され、オリジナルはそのまま残ります。

#### Q: 最適化後に元のファイル サイズと縮小されたファイル サイズを確認するにはどうすればよいですか?

A: を使用できます。`FileInfo`のクラス`System.IO`元の縮小されたファイル サイズを取得します。これを実現するためのコード スニペットの例を次に示します。

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```