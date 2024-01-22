---
title: PDF ファイルのデフォルトのフォントを設定する
linktitle: PDF ファイルのデフォルトのフォントを設定する
second_title: Aspose.PDF for .NET API リファレンス
description: このステップバイステップのガイドでは、Aspose.PDF for .NET を使用して PDF ファイルにデフォルトのフォントを設定する方法を学びます。
type: docs
weight: 280
url: /ja/net/programming-with-document/setdefaultfont/
---
.NET で PDF ドキュメントを操作している場合、PDF で使用されているフォントが表示または印刷されるシステムで使用できないという問題が発生する可能性があります。これにより、テキストが正しく表示されなかったり、まったく表示されなかったりする可能性があります。 Aspose.PDF for .NET は、ドキュメントのデフォルト フォントを設定できるようにすることで、この問題の解決策を提供します。この例では、Aspose.PDF for .NET を使用してデフォルトのフォントを設定する方法を説明します。

## ステップ 1: ドキュメント ディレクトリへのパスを設定する

PDF ドキュメントが配置されているディレクトリへのパスを設定する必要があります。このパスを「dataDir」という変数に保存します。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: PDF ドキュメントをロードする

まず、フォントが欠落している既存の PDF ドキュメントをロードします。この例では、PDF ドキュメントが、`dataDir`変数。

```csharp
string documentName = dataDir + "input.pdf";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
    //ここにコードが入ります
}
```

## ステップ 3: デフォルトのフォントを設定する

次に、次のコマンドを使用して PDF ドキュメントのデフォルトのフォントを設定します。`PdfSaveOptions`クラス。この例では、デフォルトのフォントを「Arial」に設定します。

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## ステップ 4: 更新されたドキュメントを保存する

最後に、更新されたドキュメントを新しいファイルに保存します。この例では、更新されたドキュメントを入力ファイルと同じディレクトリにある「output_out.pdf」という名前のファイルに保存します。

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### Aspose.PDF for .NET を使用したデフォルト フォントの設定のソース コード例

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//フォントが欠落している既存の PDF ドキュメントをロードする
string documentName = dataDir + "input.pdf";
string newName = "Arial";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
	PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
	//デフォルトのフォント名の指定
	pdfSaveOptions.DefaultFontName = newName;
	document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
}
```

## 結論

Aspose.PDF for .NET を使用して PDF ドキュメントにデフォルトのフォントを設定することは、元のフォントが利用できない場合でもテキストが正しく表示されることを保証する簡単かつ効果的な方法です。ステップバイステップのガイドに従い、提供されている C# ソース コードを使用することで、開発者はデフォルトのフォントを簡単に設定し、さまざまな環境間で一貫した信頼性の高い表示エクスペリエンスを提供する PDF を作成できます。この機能は、異なるフォント セットがインストールされているさまざまなシステムで PDF を表示または印刷するシナリオで特に役立ちます。

### PDF ファイルのデフォルトフォントの設定に関する FAQ

#### Q: PDF ドキュメントでデフォルトのフォントの設定が重要なのはなぜですか?

A: PDF ドキュメントのデフォルト フォントを設定することは、PDF を表示または印刷するシステムで元のフォントが利用できない場合でもテキストが正しく表示されるようにするため、重要です。テキストの欠落や文字化けなどの問題を防ぎ、一貫した信頼性の高い表示エクスペリエンスを保証します。

#### Q: Aspose.PDF for .NET を使用して、任意のフォントをデフォルト フォントとして選択できますか?

 A: はい、Aspose.PDF for .NET を使用すると、システムで利用可能な任意のフォントをデフォルト フォントとして選択できます。フォントの名前を指定するだけです。`DefaultFontName`の財産`PdfSaveOptions`クラス。

#### Q: 指定されたデフォルトのフォントがシステムで利用できない場合はどうなりますか?

A: 指定されたデフォルトのフォントがシステムで利用できない場合、PDF ビューアは代替フォントを使用してテキストを表示します。さまざまなシステム間で互換性を確保するには、Arial や Times New Roman などの一般的に入手可能なフォントを選択することをお勧めします。