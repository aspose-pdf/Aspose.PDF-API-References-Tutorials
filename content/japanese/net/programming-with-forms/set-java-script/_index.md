---
title: Java Scriptを設定する
linktitle: Java Scriptを設定する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルのフォーム フィールドに JavaScript を設定する方法を学習します。
type: docs
weight: 270
url: /ja/net/programming-with-forms/set-java-script/
---
このガイドでは、.NET 用の Aspose.PDF ライブラリを使用して PDF ドキュメントのフォーム フィールドに JavaScript を定義する方法を段階的に説明します。テキスト フィールドで特定の操作を実行するように JavaScript アクションを構成する方法を説明します。

## 前提条件

始める前に、次のものがあることを確認してください。

- システムにインストールされた .NET 開発環境。
- .NET 用の Aspose.PDF ライブラリ。Aspose の公式 Web サイトからダウンロードできます。

## ステップ1: ドキュメントディレクトリの構成

最初のステップは、作業したいPDFファイルが保存されているドキュメントディレクトリを設定することです。`dataDir`ディレクトリ パスを指定する変数。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

必ず交換してください`"YOUR DOCUMENTS DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。

## ステップ2: 入力PDFファイルの読み込み

このステップでは、入力PDFファイルを読み込みます。`Document` Aspose.PDF のクラス。

```csharp
//入力PDFファイルを読み込む
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

入力 PDF ファイルが指定されたドキュメント ディレクトリに存在することを確認します。

## ステップ3: TextBoxフィールドにアクセスする

特定のテキストフィールドにJavaScriptを適用するには、まずそのフィールドにアクセスする必要があります。この例では、テキストフィールドの名前は「textbox1」であると仮定します。`doc.Form["textbox1"]`対応するものを取得する方法`TextBoxField`物体。

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

指定されたテキスト フィールドが入力 PDF ファイルに存在することを確認します。

## ステップ4: JavaScriptアクションを構成する

テキスト フィールドにアクセスしたので、このフィールドに関連付けられた JavaScript アクションを構成できます。この例では、次の 2 つのアクションを使用します。`OnModifyCharacter`そして`OnFormat`これらのアクションは次のように定義されます。`JavascriptAction`オブジェクト。

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

必要に応じて JavaScript アクションをカスタマイズしてください。

## ステップ5: 初期フィールド値の設定

結果の PDF を保存する前に、テキスト フィールドの初期値を設定できます。この例では、フィールドに値「123」を設定します。

```csharp
field.Value = "123";
```

必要に応じてこの値をカスタマイズします。

## ステップ6: 結果のPDFを保存する

テキストフィールドとJavaScriptアクションの設定が完了したので、結果のPDFを`Save`方法の`Document`クラス。

```csharp
dataDir = dataDir + "Restricted_out.pdf";
//結果のPDFを保存する
doc.Save(dataDir);
```

結果の PDF の完全なパスとファイル名を必ず指定してください。


### Aspose.PDF for .NET を使用して Java Script を設定するためのサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//入力PDFファイルを読み込む
Document doc = new Document(dataDir + "SetJavaScript.pdf");
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
//小数点以下の2桁
//区切りなし
//ネガティブスタイル = マイナス
//通貨なし
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
//初期フィールド値を設定する
field.Value = "123";
dataDir = dataDir + "Restricted_out.pdf";
//結果のPDFを保存する
doc.Save(dataDir);
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

## 結論

このガイドでは、Aspose.PDF ライブラリ for .NET を使用して PDF ドキュメントのフォーム フィールドに JavaScript を設定する方法を学習しました。説明されている手順に従うことで、JavaScript アクションをカスタマイズし、テキスト フィールドでさまざまな操作を実行できます。Aspose.PDF for .NET の機能をさらに詳しく調べて、PDF ファイルの操作の可能性を広げてください。


### よくある質問

#### Q: Aspose.PDF for .NET を使用して、チェックボックスやラジオ ボタンなどの他のフォーム要素に JavaScript を追加できますか?

 A: はい、Aspose.PDF for .NETでは、チェックボックス、ラジオボタン、ドロップダウンリストなど、さまざまなフォーム要素にJavaScriptを追加できます。`JavascriptAction`さまざまなフォーム要素の JavaScript アクションを定義するクラス。

#### Q: フォーム フィールドで JavaScript を使用してユーザー入力を検証することは可能ですか?

 A: はい、JavaScriptを使用してフォームフィールドのユーザー入力を検証できます。次のようなJavaScriptアクションを定義することで、`OnBlur`または`OnKeystroke`フォーム フィールドでは、入力されたデータを検証し、必要に応じてエラー メッセージを表示できます。

#### Q: Aspose.PDF for .NET を使用して複雑な JavaScript 関数を実行できますか?

 A: はい、Aspose.PDF for .NETを使用して複雑なJavaScript関数を実行できます。カスタムJavaScript関数を定義し、それを`JavascriptAction`.

#### Q: Aspose.PDF for .NET は、このチュートリアルで説明されている以外の JavaScript イベントをサポートしていますか?

 A: はい、Aspose.PDF for .NETは、次のような幅広いJavaScriptイベントをサポートしています。`OnMouseEnter`, `OnMouseExit`, `OnMouseDown` 、 そして`OnMouseUp`などがあります。これらのイベントを使用して、ユーザーの操作に基づいて JavaScript アクションをトリガーできます。

#### Q: Aspose.PDF for .NET を使用して既存の PDF ドキュメントから JavaScript コードを抽出できますか?

 A: Aspose.PDF for .NETは、既存のPDFドキュメントからJavaScriptコードを抽出する機能を提供します。`JavascriptAction`クラスとその他の関連メソッドを使用して、PDF フォーム内の JavaScript アクションにアクセスし、分析します。