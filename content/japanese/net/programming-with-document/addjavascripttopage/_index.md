---
title: PDF ファイルに Java スクリプトを追加
linktitle: Java Script PDF ファイルを追加
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルに JavaScript を追加する方法を学びます。ドキュメントおよびページレベルのスクリプト作成のためのコードチュートリアルを含むステップバイステップのガイド。
type: docs
weight: 10
url: /ja/net/programming-with-document/addjavascripttopage/
---
PDF ファイルに JavaScript を追加するには、Aspose.PDF for .NET を使用します。このライブラリは、.NET アプリケーションで PDF ファイルを操作するためのシンプルかつ効率的な方法を提供します。次の手順では、Aspose.PDF for .NET を使用して PDF ファイルに JavaScript を追加するプロセスを説明します。

## ステップ 1: PDF ファイルをロードする

最初のステップは、JavaScript を追加する PDF ファイルをロードすることです。これを行うには、`Document` Aspose.PDF for .NET によって提供されるクラス。の`Document`クラスは、PDF ファイルをロード、保存、操作するためのメソッドを提供します。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//既存の PDF ファイルをロードする
Document doc = new Document(dataDir + "input.pdf");
```

## ステップ 2: ドキュメント レベルで JavaScript を追加する

ドキュメントレベルで JavaScript を追加するには、`JavascriptAction` Aspose.PDF for .NET によって提供されるクラス。このクラスを使用すると、PDF ファイルに追加する JavaScript ステートメントを指定できます。

```csharp
//ドキュメントレベルでの JavaScript の追加
//必要な JavaScript ステートメントを使用して JavaScriptAction をインスタンス化します。
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// JavascriptActionオブジェクトをDocumentの目的のアクションに割り当てます。
doc.OpenAction = javaScript;
```

このチュートリアルでは、ドキュメントを開いたときに指定されたオプションを使用して PDF ファイルを印刷する JavaScript ステートメントを追加します。

## ステップ 3: ページレベルで JavaScript を追加する

ページレベルで JavaScript を追加するには、`JavascriptAction`クラスと`Actions`Aspose.PDF for .NET によって提供されるプロパティ。このプロパティを使用すると、ページを開いたときまたは閉じたときに実行される JavaScript ステートメントを指定できます。

```csharp
//ページレベルでの JavaScript の追加
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");
```

このチュートリアルでは、ページを開いたり閉じたりしたときに警告メッセージを表示する JavaScript ステートメントを追加します。

## ステップ 4: PDF ファイルを保存する

PDF ファイルに JavaScript を追加した後、変更したファイルを保存する必要があります。これを行うには、`Save`によって提供されるメソッド`Document`クラス。

```csharp
dataDir = dataDir + "JavaScript-Added_out.pdf";
//PDFドキュメントを保存
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);
```

このコードは、変更された PDF ファイルを指定されたディレクトリに保存します。

### Aspose.PDF for .NET を使用してページに Java Script を追加するソース コードの例

```csharp
            
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//既存の PDF ファイルをロードする
Document doc = new Document(dataDir + "input.pdf");

//ドキュメントレベルでの JavaScript の追加
//指定された JavaScript ステートメントを使用して JavaScriptAction をインスタンス化します。
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// JavascriptActionオブジェクトをDocumentの目的のアクションに割り当てます。
doc.OpenAction = javaScript;

//ページレベルでの JavaScript の追加
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");

dataDir = dataDir + "JavaScript-Added_out.pdf";
//PDFドキュメントを保存
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);     
```

## 結論

この記事では、Aspose.PDF for .NET を使用して、ドキュメント レベルとページ レベルの両方で PDF ファイルに JavaScript を追加する方法を説明しました。段階的な手順を説明し、各例の完全なソース コードを含めました。この知識があれば、PDF ファイルに JavaScript を追加し、ニーズに応じて動作をカスタマイズできます。


### PDF ファイルへの Java スクリプトの追加に関する FAQ

#### Q: Aspose.PDF for .NET とは何ですか?

A: Aspose.PDF for .NET は、開発者が .NET アプリケーションで PDF ファイルを操作できるようにする強力なライブラリです。 PDF ドキュメントを作成、変更、操作するための幅広い機能を提供します。

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメントに JavaScript を追加できますか?

A: はい、Aspose.PDF for .NET を使用すると、PDF ファイルのドキュメント レベルとページ レベルの両方に JavaScript を追加でき、動的でインタラクティブな PDF ドキュメントを作成できます。

#### Q: Aspose.PDF for .NET を使用して既存の PDF ファイルをロードするにはどうすればよいですか?

 A: 既存の PDF ファイルをロードするには、`Document`ステップバイステップ ガイドに示されているように、クラスとそのメソッド。

#### Q: PDF ドキュメントにはどのような種類の JavaScript アクションを追加できますか?

A: Aspose.PDF for .NET を使用すると、印刷、警告メッセージ、フォーム フィールドの操作など、さまざまな JavaScript アクションを追加できます。

#### Q: Aspose.PDF for .NET は商用プロジェクトに適していますか?

A: はい。Aspose.PDF for .NET は、商用プロジェクトで PDF の操作および生成タスクによく使用される、信頼性が高く堅牢なライブラリです。

