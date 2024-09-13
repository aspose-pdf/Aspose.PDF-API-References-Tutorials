---
title: PDFからすべてのテキストを削除する
linktitle: PDFからすべてのテキストを削除する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ドキュメントからすべてのテキストを削除する方法を学習します。
type: docs
weight: 290
url: /ja/net/programming-with-text/remove-all-text-from-pdf/
---
このチュートリアルでは、.NET用のAspose.PDFライブラリを使用してPDFドキュメントからすべてのテキストを削除する方法を説明します。`TextFragmentAbsorber`すべてのテキストを削除し、提供されている C# ソース コードを使用して変更された PDF を保存します。

## 要件

始める前に、次のものがあることを確認してください。

- Aspose.PDF for .NET ライブラリがインストールされました。
- C# プログラミングの基本的な理解。

## ステップ1: ドキュメントディレクトリを設定する

まず、PDFファイルが保存されているディレクトリへのパスを設定する必要があります。`"YOUR DOCUMENT DIRECTORY"`の`dataDir` PDF ファイルへのパスを含む変数。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ2: PDFドキュメントを開く

次に、PDF文書を`Document` Aspose.PDF ライブラリのクラス。

```csharp
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
```

## ステップ3: すべてのテキストを削除する

初期化する`TextFragmentAbsorber`オブジェクトを作成し、それを使用して PDF ドキュメントから吸収されたすべてのテキストを削除します。

```csharp
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb. RemoveAllText(pdfDocument);
```

## ステップ4: 変更したPDFを保存する

最後に、変更された PDF ドキュメントを指定された出力ファイルに保存します。

```csharp
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Aspose.PDF for .NET を使用して PDF からすべてのテキストを削除するためのサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントを開く
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
//TextFragmentAbsorber を開始する
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
//吸収されたテキストをすべて削除
absorber.RemoveAllText(pdfDocument);
//文書を保存する
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## 結論

このチュートリアルでは、.NET用のAspose.PDFライブラリを使用してPDFドキュメントからすべてのテキストを削除する方法を学びました。ステップバイステップのガイドに従って、提供されているC#コードを実行すると、PDFを開いて、`TextFragmentAbsorber`、変更した PDF を保存します。

### よくある質問

#### Q: 「PDF からすべてのテキストを削除する」チュートリアルの目的は何ですか?

 A: 「PDFからすべてのテキストを削除」チュートリアルでは、Aspose.PDFライブラリ for .NETを使用してPDFドキュメントからすべてのテキストを削除する方法について説明します。このチュートリアルでは、`TextFragmentAbsorber`すべてのテキストを削除し、変更された PDF を保存します。

#### Q: PDF ドキュメントからすべてのテキストを削除する必要があるのはなぜですか?

A: PDF ドキュメントからすべてのテキストを削除すると、テキスト コンテンツのないバージョンのドキュメントを作成する必要がある場合に役立ちます。これは、プライバシー上の理由から、またはテキスト情報を表示せずにドキュメントのレイアウトの視覚的表現を生成する場合に役立ちます。

#### Q: ドキュメント ディレクトリを設定するにはどうすればよいですか?

A: ドキュメントディレクトリを設定するには:

1. 交換する`"YOUR DOCUMENT DIRECTORY"`の`dataDir` PDF ファイルが保存されているディレクトリへのパスを持つ変数。

#### Q: Aspose.PDF ライブラリを使用して PDF ドキュメントからすべてのテキストを削除するにはどうすればよいですか?

A: チュートリアルでは、プロセスを段階的に説明します。

1.  PDF文書を開くには、`Document`クラス。
2. 初期化する`TextFragmentAbsorber`物体。
3. 吸収機能を使用して、PDF ドキュメントから吸収されたすべてのテキストを削除します。
4. 変更した PDF ドキュメントを保存します。

#### Q: ドキュメントの特定の領域からテキストを選択的に削除できますか?

A: このチュートリアルでは、PDF ドキュメント全体からすべてのテキストを削除することに重点を置いています。特定の領域からテキストを選択的に削除する場合は、アプローチを変更し、より複雑なロジックを使用して特定のテキスト フラグメントを識別して削除する必要があります。

#### Q:`TextFragmentAbsorber` work to remove text?

 A:`TextFragmentAbsorber`Aspose.PDFライブラリが提供するクラスで、PDF文書からテキストの断片を吸収することができます。`RemoveAllText`方法の`TextFragmentAbsorber`クラスを使用すると、吸収されたテキストフラグメントをすべてドキュメントから削除できます。

#### Q: 提供されたコードを実行すると、どのような結果が期待されますか?

A: チュートリアルに従って提供されている C# コードを実行すると、入力 PDF ドキュメントからすべてのテキストが削除され、変更されたバージョンが出力 PDF ファイルとして保存されます。

#### Q: 特定のページまたは領域からのみテキストを削除するようにコードを変更することはできますか?

A: はい、コードを変更することで実現できます。選択的なテキスト削除の場合は、PDF ドキュメント内の特定のページまたは領域を対象にするようにコードを調整する必要があります。

#### Q: このチュートリアルには有効な Aspose ライセンスが必要ですか?

A: はい、このチュートリアルのコードを正常に実行するには、有効な Aspose ライセンスが必要です。Aspose Web サイトから、フル ライセンスまたは 30 日間の一時ライセンスを取得できます。