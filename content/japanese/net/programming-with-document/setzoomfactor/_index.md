---
title: PDF ファイルのズーム率を設定する
linktitle: PDF ファイルのズーム率を設定する
second_title: Aspose.PDF for .NET API リファレンス
description: ステップバイステップ ガイドを使用して、Aspose.PDF for .NET を使用して PDF ファイルのズーム係数を設定する方法を学習します。
type: docs
weight: 340
url: /ja/net/programming-with-document/setzoomfactor/
---
Aspose.PDF for .NET は、開発者が .NET アプリケーションで PDF ドキュメントを操作できるようにする強力な API です。この API が提供する機能の 1 つは、PDF ドキュメントのズーム係数を設定する機能です。このステップ バイ ステップ ガイドでは、提供されている C# ソース コードを使用して、Aspose.PDF for .NET で PDF ドキュメントのズーム係数を設定する方法について説明します。

## ステップ1: ドキュメントディレクトリへのパスを設定する

最初のステップは、PDF文書が保存されているディレクトリへのパスを設定することです。これは、`dataDir`変数をディレクトリ パスに追加します。 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

「YOUR DOCUMENT DIRECTORY」を、PDF ドキュメントが配置されている実際のディレクトリ パスに置き換えます。

## ステップ2: 新しいDocumentオブジェクトをインスタンス化する

Aspose.PDF for .NETを使用してPDFドキュメントを操作するには、新しい`Document`オブジェクトを作成し、その中に PDF ファイルを読み込みます。 

```csharp
Document doc = new Document(dataDir + "SetZoomFactor.pdf");
```

このコードは新しい`Document`オブジェクトを作成し、"SetZoomFactor.pdf"という名前のPDFファイルを読み込みます。`dataDir`ディレクトリに追加します。

## ステップ3: ズーム率を設定する

一度`Document`オブジェクトが作成されると、PDF ドキュメントのズーム係数を設定できます。次のコードでは、ズーム係数を 50% に設定しています。

```csharp
GoToAction action = new GoToAction(new XYZExplicitDestination(1, 0, 0, .5));
doc.OpenAction = action;
```

このコードは、新しいものを作成してズーム率を50%に設定します。`GoToAction`オブジェクトを渡して`XYZExplicitDestination`オブジェクトを50%のズーム率で拡大します。`OpenAction`の財産`Document`オブジェクトはこれに設定されます`GoToAction`物体。

## ステップ4: PDF文書を保存する

最後に、変更したPDF文書を新しいファイルに保存します。次のコードでは、PDF文書を「Zoomed_pdf_out.pdf」という名前の新しいファイルに保存します。`dataDir`ディレクトリ。

```csharp
dataDir = dataDir + "Zoomed_pdf_out.pdf";
doc.Save(dataDir);
```

### Aspose.PDF for .NET を使用してズーム係数を設定するためのサンプル ソース コード

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//新しいDocumentオブジェクトをインスタンス化する
Document doc = new Document(dataDir + "SetZoomFactor.pdf");

GoToAction action = new GoToAction(new XYZExplicitDestination(1, 0, 0, .5));
doc.OpenAction = action;
dataDir = dataDir + "Zoomed_pdf_out.pdf";
//文書を保存する
doc.Save(dataDir);
```

## 結論

Aspose.PDF for .NET は、C# コードを使用して PDF ドキュメントのズーム係数を設定するシンプルで効率的な方法を提供します。上記の手順に従うことで、.NET アプリケーション内の任意の PDF ドキュメントのズーム係数を簡単に変更できます。

### よくある質問

#### Q: PDF ドキュメントのズーム係数とは何ですか? また、表示にどのような影響がありますか?

A: PDF ドキュメントのズーム係数は、ドキュメントを表示する際の拡大レベルを決定します。ズーム係数はドキュメントの表示スケールを指定し、画面に表示されるコンテンツの大きさに影響します。ズーム係数 1.0 は 100% ズーム (実際のサイズ) を表し、1.0 より大きい係数はズームイン、1.0 より小さい係数はズームアウトを表します。

#### Q: 同じ PDF ドキュメント内の異なるページに特定のズーム係数を設定できますか?

 A: はい、Aspose.PDF for .NETでは、同じPDFドキュメント内の異なるページに異なるズーム率を設定できます。提供されているサンプルソースコードでは、`GoToAction`オブジェクト。必要に応じてコードを変更して、他のページに異なるズーム係数を設定できます。

#### Q: ズーム率を変更すると、PDF ドキュメントの印刷と保存にどのような影響がありますか?

A: Aspose.PDF for .NET を使用してズーム係数を変更しても、PDF ドキュメント自体の実際の内容には影響しません。ドキュメントを PDF ビューアーで開いたときの表示エクスペリエンスにのみ影響します。プログラムで設定されたズーム係数は、印刷出力や保存された PDF ファイルには影響しません。