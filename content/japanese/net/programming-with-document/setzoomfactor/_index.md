---
title: PDF ファイルのズーム率を設定する
linktitle: PDF ファイルのズーム率を設定する
second_title: Aspose.PDF for .NET API リファレンス
description: ステップバイステップのガイドで、Aspose.PDF for .NET を使用して PDF ファイルのズーム率を設定する方法を学びましょう。
type: docs
weight: 340
url: /ja/net/programming-with-document/setzoomfactor/
---
Aspose.PDF for .NET は、開発者が .NET アプリケーションで PDF ドキュメントを操作できるようにする強力な API です。提供される機能の 1 つは、PDF ドキュメントのズーム率を設定する機能です。このステップバイステップ ガイドでは、Aspose.PDF for .NET を使用して、提供されている C# ソース コードを使用して PDF ドキュメントのズーム率を設定する方法を説明します。

## ステップ 1: ドキュメント ディレクトリへのパスを設定する

最初のステップは、PDF ドキュメントが配置されているディレクトリへのパスを設定することです。これは、`dataDir`変数をディレクトリパスに設定します。 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

「YOUR DOCUMENT DIRECTORY」を、PDF ドキュメントが配置されている実際のディレクトリ パスに置き換えます。

## ステップ 2: 新しい Document オブジェクトをインスタンス化する

Aspose.PDF for .NET を使用して PDF ドキュメントを操作するには、新しいファイルを作成する必要があります。`Document`オブジェクトを選択し、その中に PDF ファイルをロードします。 

```csharp
Document doc = new Document(dataDir + "SetZoomFactor.pdf");
```

このコードは新しいものを作成します`Document`オブジェクトを選択し、「SetZoomFactor.pdf」という名前の PDF ファイルを`dataDir`ディレクトリをその中に入れます。

## ステップ 3: ズーム率を設定する

一度`Document`オブジェクトが作成されたら、PDF ドキュメントのズーム率を設定できます。次のコードでは、ズーム率を 50% に設定します。

```csharp
GoToAction action = new GoToAction(new XYZExplicitDestination(1, 0, 0, .5));
doc.OpenAction = action;
```

このコードは、新しいファイルを作成してズーム率を 50% に設定します。`GoToAction`オブジェクトを渡して`XYZExplicitDestination`オブジェクトを 50% のズーム率で拡大します。の`OpenAction`の財産`Document`オブジェクトはこれに設定されます`GoToAction`物体。

## ステップ 4: PDF ドキュメントを保存する

最後に、変更した PDF ドキュメントを新しいファイルに保存できます。次のコードでは、PDF ドキュメントを「Zoomed_pdf_out.pdf」という名前の新しいファイルに保存します。`dataDir`ディレクトリ。

```csharp
dataDir = dataDir + "Zoomed_pdf_out.pdf";
doc.Save(dataDir);
```

### Aspose.PDF for .NET を使用したズーム係数の設定のソース コード例

```csharp
//ドキュメントディレクトリへのパス。
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

Aspose.PDF for .NET は、C# コードを使用して PDF ドキュメントのズーム率を設定する簡単かつ効率的な方法を提供します。上記の手順に従うことで、.NET アプリケーション内の PDF ドキュメントのズーム率を簡単に変更できます。

### よくある質問

#### Q: PDF ドキュメントのズーム倍率とは何ですか? それは表示にどのような影響を与えますか?

A: PDF ドキュメントのズーム率によって、ドキュメントを表示するときの倍率のレベルが決まります。ドキュメントを表示する縮尺を指定し、画面上に表示されるコンテンツの大きさに影響します。ズーム係数 1.0 は 100% ズーム (実際のサイズ) を表し、1.0 を超える係数はズームインし、1.0 未満の係数はズームアウトします。

#### Q: 同じ PDF ドキュメント内の異なるページに特定のズーム率を設定できますか?

 A: はい、Aspose.PDF for .NET を使用すると、同じ PDF ドキュメント内の異なるページに異なるズーム率を設定できます。提供されているサンプル ソース コードは、`GoToAction`物体。必要に応じてコードを変更して、他のページに異なるズーム率を設定できます。

#### Q: ズーム率を変更すると、PDF ドキュメントの印刷と保存にどのような影響がありますか?

A: Aspose.PDF for .NET を使用してズーム率を変更しても、PDF ドキュメント自体の実際のコンテンツには影響しません。 PDF ビューアでドキュメントを開いたときの表示エクスペリエンスにのみ影響します。プログラムで設定されたズーム率は、印刷出力や保存された PDF ファイルには影響しません。