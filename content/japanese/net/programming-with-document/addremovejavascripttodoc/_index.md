---
title: PDF ドキュメントに Javascript を追加削除
linktitle: ドキュメントに Javascript を追加削除
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ドキュメントに JavaScript を追加および削除する方法を学びます。ドキュメントレベルのスクリプト作成のためのコードチュートリアルを含むステップバイステップのガイド。
type: docs
weight: 30
url: /ja/net/programming-with-document/addremovejavascripttodoc/
---
PDF ドキュメントに JavaScript を追加および削除するには、Aspose.PDF for .NET ライブラリを利用します。この強力なライブラリを使用すると、.NET アプリケーションで PDF ファイルを操作できます。 Aspose.PDF for .NET を使用して JavaScript を追加および削除するには、以下の段階的な手順に従ってください。

## ステップ 1: 新しい PDF ドキュメントを作成する

まず、新しいインスタンスを作成します。`Document` Aspose.PDF for .NET によって提供されるクラス。これは、JavaScript を追加する PDF ドキュメントとして機能します。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
```

## ステップ 2: ドキュメント レベルで JavaScript を追加する

ドキュメント レベルで JavaScript を追加するには、`JavaScript`の財産`Document`クラス。 JavaScript 関数を JavaScript 辞書内のキーに割り当てます。

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");
```

このチュートリアルでは、2 つの JavaScript 関数を追加しました。`func1`そして`func2`、PDF ドキュメントに。

## ステップ 3: ドキュメント レベルの JavaScript を削除する

ドキュメント レベルで JavaScript を削除するには、PDF ドキュメントをロードし、`JavaScript`辞書。キーを反復処理し、必要な JavaScript 関数を削除します。

```csharp
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;

foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed");
```

このチュートリアルでは、`func1` PDF ドキュメントからの JavaScript 関数。

## ステップ 4: 変更を保存して確認する

変更した PDF ドキュメントを保存し、変更を確認します。

```csharp
Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

このコードは、変更された PDF ドキュメントを保存し、成功メッセージを表示します。

### Aspose.PDF for .NET を使用して PDF ドキュメントに Javascript を追加削除するソース コードの例

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");

//ドキュメントレベルのJavaScriptを削除
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
	Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed ");
Console.WriteLine("=============================== ");

Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

## 結論

この記事では、Aspose.PDF for .NET を使用して PDF ドキュメントに JavaScript を追加および削除するためのステップバイステップのガイドを提供しました。指示に従い、提供されたコードチュートリアルを利用することで、PDF ドキュメントに JavaScript を簡単に組み込み、必要に応じて削除できます。 JavaScript により、PDF ファイルの動的な機能と対話性が可能になり、ユーザー エクスペリエンスが向上します。


### PDF ドキュメントへの JavaScript の追加と削除に関する FAQ

#### Q: Aspose.PDF for .NET とは何ですか?

A: Aspose.PDF for .NET は、開発者が .NET アプリケーションで PDF ファイルを効果的に操作できるようにする強力なライブラリです。 PDF ドキュメントをプログラムで操作するための広範な機能を提供します。

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメントに JavaScript を追加するにはどうすればよいですか?

 A: JavaScript をドキュメント レベルで追加するには、`JavaScript`の財産`Document`クラス。 JavaScript 関数を JavaScript 辞書内のキーに割り当てるだけです。

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメントから JavaScript を削除できますか?

 A: はい、PDF ドキュメントから JavaScript を削除するには、`JavaScript`辞書を作成し、目的の JavaScript 関数を削除します。

#### Q: Aspose.PDF for .NET はプロフェッショナルなプロジェクトに適していますか?

A: 確かに、Aspose.PDF for .NET は、PDF の操作および生成タスクのために専門的なプロジェクトで広く使用されています。高性能で信頼性の高い機能を提供します。

#### Q: PDF ドキュメントに JavaScript を追加するとどのようなメリットがありますか?

A: PDF ドキュメントに JavaScript を追加すると、インタラクティブで動的な PDF ファイルを作成できます。フォーム検証を実装し、計算を実行し、さまざまな対話機能を追加して、ユーザー エクスペリエンスを向上させることができます。