---
title: PDF ファイルに有効期限を設定する
linktitle: PDF ファイルに有効期限を設定する
second_title: Aspose.PDF for .NET API リファレンス
description: このステップバイステップのガイドでは、Aspose.PDF for .NET を使用して PDF ファイルに有効期限を設定する方法を学びます。
type: docs
weight: 300
url: /ja/net/programming-with-document/setexpirydate/
---
Aspose.PDF for .NET は、PDF ファイルを操作するためのさまざまな機能を提供する強力なライブラリです。そのような機能の 1 つは、PDF ドキュメントの有効期限を設定する機能です。このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントの有効期限を設定するプロセスについて説明します。 

## ステップ 1: ドキュメント ディレクトリへのパスを設定する

始める前に、PDF ドキュメントが配置されているディレクトリへのパスを設定する必要があります。このパスを「dataDir」という変数に保存します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: 新しい PDF ドキュメントを作成する

新しい PDF ドキュメントを作成するには、新しい PDF ドキュメントをインスタンス化する必要があります。`Aspose.Pdf.Document`物体。次のコードを使用してこれを行うことができます。

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## ステップ 3: PDF ドキュメントに新しいページを追加する

PDF ドキュメントを作成したら、それに新しいページを追加できます。次のコードを使用してこれを行うことができます。

```csharp
doc.Pages.Add();
```

## ステップ 4: PDF ドキュメントにテキストを追加する

PDF ドキュメントにページを追加した後、`Paragraphs`コレクション。次のコードを使用してこれを行うことができます。

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

## ステップ 5: JavaScript を使用して PDF の有効期限を設定する

PDF の有効期限を設定するには、JavaScript オブジェクトを作成する必要があります。次のコードを使用してこれを行うことができます。

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");

// JavaScript を PDF を開くアクションとして設定する
doc.OpenAction = javaScript;
```

このコードでは、有効期限を 2017 年 5 月に設定しています。

## ステップ 6: PDF ファイルを保存する

有効期限を設定したら、PDF ファイルを保存する必要があります。これを行うには、`Save`の方法`Document`オブジェクトを指定し、更新された PDF ファイルを保存する場所へのパスを渡します。

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
//PDFドキュメントを保存
doc.Save(dataDir);
```

### Aspose.PDF for .NET を使用した有効期限の設定のソース コード例

Aspose.PDF for .NET を使用して有効期限を設定するための完全なソース コードの例を次に示します。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Documentオブジェクトをインスタンス化する
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// PDF ファイルのページコレクションにページを追加
doc.Pages.Add();
//ページオブジェクトの段落コレクションにテキストフラグメントを追加します
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
//PDF の有効期限を設定する JavaScript オブジェクトを作成する
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
// JavaScript を PDF を開くアクションとして設定する
doc.OpenAction = javaScript;

dataDir = dataDir + "SetExpiryDate_out.pdf";
//PDFドキュメントを保存
doc.Save(dataDir);
```

## 結論

Aspose.PDF for .NET を使用して PDF ドキュメントの有効期限を設定することは、ドキュメントが指定された期間のみ有効であることを確認するのに便利な機能です。ステップバイステップのガイドに従い、提供されている C# ソース コードを使用することで、開発者は有効期限を簡単に設定し、有効期限が制限された PDF を作成できます。この機能は、限られた期間にアクセスまたは配布する必要があるドキュメントに特に役立ちます。

### PDFファイルの有効期限設定に関するFAQ

#### Q: PDF ドキュメントに別の有効期限を設定できますか?

 A: はい、ステップ 5 の JavaScript コードを変更することで、PDF ドキュメントに別の有効期限を設定できます。この例では、有効期限は 2017 年 5 月に設定されています。別の有効期限を設定するには、`year`そして`month` JavaScript コード内の変数を目的の年と月に置き換えます。

#### Q: PDF ドキュメントの有効期限が切れるとどうなりますか?

A: JavaScript コードで指定されているように PDF ドキュメントの有効期限が切れると、ビューアにはファイルの有効期限が切れており、ユーザーに新しいファイルが必要であることを示す警告メッセージが表示されます。この警告メッセージは、PDF を開いたときに表示されます。

#### Q: 有効期限として日付だけでなく特定の時間を使用できますか?

 A: はい、JavaScript コードで有効期限の特定の時刻を設定できます。を変更することで、`expiry` JavaScript コード内の変数に希望の時刻を含めると、有効期限として特定の時刻を設定できます。