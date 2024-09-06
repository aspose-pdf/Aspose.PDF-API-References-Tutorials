---
title: PDF ファイルのデフォルトフォントを設定する
linktitle: PDF ファイルのデフォルトフォントを設定する
second_title: Aspose.PDF for .NET API リファレンス
description: このステップバイステップ ガイドでは、Aspose.PDF for .NET を使用して PDF ファイルの既定のフォントを設定する方法を学習します。
type: docs
weight: 280
url: /ja/net/programming-with-document/setdefaultfont/
---
.NET で PDF ドキュメントを操作している場合、PDF で使用されているフォントが、それを表示または印刷するシステムで使用できないという問題が発生することがあります。その結果、テキストが正しく表示されないか、まったく表示されないことがあります。Aspose.PDF for .NET では、ドキュメントの既定のフォントを設定できるようにすることで、この問題を解決できます。この例では、Aspose.PDF for .NET を使用して既定のフォントを設定する方法を説明します。

## ステップ1: ドキュメントディレクトリへのパスを設定する

PDF ドキュメントが保存されているディレクトリへのパスを設定する必要があります。このパスは「dataDir」という変数に保存します。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ2: PDF文書を読み込む

まず、フォントが不足している既存のPDF文書を読み込みましょう。この例では、PDF文書が`dataDir`変数。

```csharp
string documentName = dataDir + "input.pdf";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
    //コードはここに
}
```

## ステップ3: デフォルトのフォントを設定する

次に、PDF文書のデフォルトのフォントを設定します。`PdfSaveOptions`クラス。この例では、デフォルトのフォントを「Arial」に設定します。

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## ステップ4: 更新したドキュメントを保存する

最後に、更新されたドキュメントを新しいファイルに保存します。この例では、更新されたドキュメントを入力ファイルと同じディレクトリ内の「output_out.pdf」という名前のファイルに保存します。

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### Aspose.PDF for .NET を使用して既定のフォントを設定するためのサンプル ソース コード

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//フォントが欠落している既存のPDF文書を読み込む
string documentName = dataDir + "input.pdf";
string newName = "Arial";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
	PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
	//デフォルトのフォント名を指定する
	pdfSaveOptions.DefaultFontName = newName;
	document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
}
```

## 結論

Aspose.PDF for .NET を使用して PDF ドキュメントに既定のフォントを設定することは、元のフォントが利用できない場合でもテキストが正しく表示されるようにするための簡単で効果的な方法です。開発者は、ステップ バイ ステップ ガイドに従い、提供されている C# ソース コードを使用することで、既定のフォントを簡単に設定し、さまざまな環境で一貫性のある信頼性の高い表示エクスペリエンスを提供する PDF を作成できます。この機能は、異なるフォント セットがインストールされている可能性のあるさまざまなシステムで PDF を表示または印刷するシナリオで特に役立ちます。

### PDF ファイルのデフォルト フォントの設定に関する FAQ

#### Q: PDF ドキュメントでデフォルトのフォントを設定することが重要なのはなぜですか?

A: PDF ドキュメントにデフォルトのフォントを設定することは重要です。PDF を表示または印刷するシステムで元のフォントが利用できない場合でも、テキストが正しく表示されるためです。これにより、テキストの欠落や文字化けなどの問題を防ぎ、一貫性のある信頼性の高い表示エクスペリエンスを確保できます。

#### Q: Aspose.PDF for .NET を使用して、任意のフォントを既定のフォントとして選択できますか?

 A: はい、Aspose.PDF for .NETを使用して、システムで利用可能な任意のフォントをデフォルトのフォントとして選択できます。`DefaultFontName`の財産`PdfSaveOptions`クラス。

#### Q: 指定したデフォルトのフォントがシステムで使用できない場合はどうなりますか?

A: 指定されたデフォルト フォントがシステムで使用できない場合、PDF ビューアは代替フォントを使用してテキストを表示します。異なるシステム間での互換性を確保するには、Arial や Times New Roman などの一般的に使用可能なフォントを選択することをお勧めします。