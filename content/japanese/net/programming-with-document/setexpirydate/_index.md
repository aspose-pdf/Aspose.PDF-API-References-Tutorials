---
title: PDF ファイルに有効期限を設定する
linktitle: PDF ファイルに有効期限を設定する
second_title: Aspose.PDF for .NET API リファレンス
description: このステップバイステップ ガイドでは、Aspose.PDF for .NET を使用して PDF ファイルに有効期限を設定する方法を学習します。
type: docs
weight: 300
url: /ja/net/programming-with-document/setexpirydate/
---
Aspose.PDF for .NET は、PDF ファイルの操作にさまざまな機能を提供する強力なライブラリです。そのような機能の 1 つは、PDF ドキュメントの有効期限を設定する機能です。このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントの有効期限を設定する手順について説明します。 

## ステップ1: ドキュメントディレクトリへのパスを設定する

始める前に、PDF ドキュメントが保存されているディレクトリへのパスを設定する必要があります。このパスは、「dataDir」という変数に保存します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ2: 新しいPDFドキュメントを作成する

新しいPDF文書を作成するには、新しい`Aspose.Pdf.Document`オブジェクト。次のコードを使用してこれを実行できます。

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## ステップ3: PDF文書に新しいページを追加する

PDF ドキュメントを作成したら、新しいページを追加できます。これは次のコードを使用して実行できます。

```csharp
doc.Pages.Add();
```

## ステップ4: PDF文書にテキストを追加する

PDF文書にページを追加した後、`Paragraphs`コレクション。次のコードを使用してこれを実行できます。

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

## ステップ5: JavaScriptを使用してPDFの有効期限を設定する

PDF の有効期限を設定するには、JavaScript オブジェクトを作成する必要があります。これは次のコードを使用して実行できます。

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");

// PDFを開くアクションとしてJavaScriptを設定する
doc.OpenAction = javaScript;
```

このコードでは、有効期限を 2017 年 5 月に設定しています。

## ステップ6: PDFファイルを保存する

有効期限を設定したら、PDFファイルを保存する必要があります。これを行うには、`Save`方法の`Document`オブジェクトを追加し、更新された PDF ファイルを保存する場所へのパスを渡します。

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
// PDF文書を保存
doc.Save(dataDir);
```

### Aspose.PDF for .NET を使用して有効期限を設定するためのサンプル ソース コード

Aspose.PDF for .NET を使用して有効期限を設定する完全なサンプル ソース コードは次のとおりです。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Documentオブジェクトをインスタンス化する
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// PDFファイルのページコレクションにページを追加する
doc.Pages.Add();
//ページオブジェクトの段落コレクションにテキストフラグメントを追加する
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
//PDFの有効期限を設定するJavaScriptオブジェクトを作成する
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
// PDFを開くアクションとしてJavaScriptを設定する
doc.OpenAction = javaScript;

dataDir = dataDir + "SetExpiryDate_out.pdf";
// PDF文書を保存
doc.Save(dataDir);
```

## 結論

Aspose.PDF for .NET を使用して PDF ドキュメントの有効期限を設定することは、ドキュメントが指定された期間のみ有効であることを保証する便利な機能です。開発者は、ステップバイステップのガイドに従い、提供されている C# ソース コードを使用することで、有効期限を簡単に設定し、有効期限が制限された PDF を作成できます。この機能は、限られた期間にアクセスまたは配布する必要があるドキュメントに特に役立ちます。

### PDF ファイルで有効期限を設定するための FAQ

#### Q: PDF ドキュメントに別の有効期限を設定できますか?

 A: はい、ステップ5のJavaScriptコードを変更することで、PDF文書の有効期限を変更できます。提供された例では、有効期限は2017年5月に設定されています。別の有効期限を設定するには、`year`そして`month` JavaScript コード内の変数を希望の年と月に設定します。

#### Q: PDF ドキュメントの有効期限が切れるとどうなりますか?

A: PDF ドキュメントの有効期限が JavaScript コードで指定されているとおりに切れると、ビューアには、ファイルが期限切れであり、新しいファイルが必要であることを示す警告メッセージが表示されます。この警告メッセージは、PDF を開いたときに表示されます。

#### Q: 有効期限として日付だけでなく特定の時間を指定できますか?

 A: はい、JavaScriptコードで有効期限の特定の時間を設定できます。`expiry` JavaScript コード内の変数に希望の時間を含めることで、有効期限の特定の時間を設定できます。