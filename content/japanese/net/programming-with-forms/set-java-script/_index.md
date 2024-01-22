---
title: Javaスクリプトの設定
linktitle: Javaスクリプトの設定
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルのフォーム フィールドに JavaScript を設定する方法を学びます。
type: docs
weight: 270
url: /ja/net/programming-with-forms/set-java-script/
---
このガイドでは、.NET 用の Aspose.PDF ライブラリを使用して PDF ドキュメントのフォーム フィールドに JavaScript を定義する方法を段階的に説明します。テキスト フィールドで特定の操作を実行するように JavaScript アクションを構成する方法を示します。

## 前提条件

始める前に、以下のものがあることを確認してください。

- システムにインストールされている .NET 開発環境。
- .NET 用の Aspose.PDF ライブラリ。 Aspose公式Webサイトからダウンロードできます。

## ステップ 1: ドキュメント ディレクトリの構成

最初のステップは、作業する PDF ファイルが配置されるドキュメント ディレクトリを構成することです。使用できます`dataDir`ディレクトリパスを指定する変数。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

必ず交換してください`"YOUR DOCUMENTS DIRECTORY"`ドキュメントディレクトリへの実際のパスを含めます。

## ステップ 2: 入力 PDF ファイルをロードする

このステップでは、`Document` Aspose.PDF のクラス。

```csharp
//入力PDFファイルを読み込みます
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

入力 PDF ファイルが指定されたドキュメント ディレクトリに存在することを確認してください。

## ステップ 3: TextBox フィールドへのアクセス

JavaScript を特定のテキスト フィールドに適用するには、まずそのフィールドにアクセスする必要があります。この例では、テキスト フィールドの名前を「textbox1」とします。使用`doc.Form["textbox1"]`対応するものを取得するメソッド`TextBoxField`物体。

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

指定したテキストフィールドが入力 PDF ファイルに存在することを確認してください。

## ステップ 4: JavaScript アクションを構成する

テキスト フィールドにアクセスしたので、このフィールドに関連付けられた JavaScript アクションを設定できます。この例では、2 つのアクションを使用します。`OnModifyCharacter`そして`OnFormat` 。これらのアクションは次を使用して定義されます`JavascriptAction`オブジェクト。

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

必要に応じて JavaScript アクションをカスタマイズしてください。

## ステップ 5: フィールドの初期値を設定する

結果の PDF を保存する前に、テキスト フィールドの初期値を設定できます。この例では、フィールドに値「123」を設定します。

```csharp
field.Value = "123";
```

必要に応じてこの値をカスタマイズします。

## ステップ 6: 結果の PDF を保存する

テキスト フィールドと JavaScript アクションの設定が完了したので、結果の PDF を次のコマンドを使用して保存できます。`Save`の方法`Document`クラス。

```csharp
dataDir = dataDir + "Restricted_out.pdf";
//結果の PDF を保存する
doc.Save(dataDir);
```

生成される PDF の絶対パスとファイル名を必ず指定してください。


### Aspose.PDF for .NET を使用した Set Java Script のサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//入力PDFファイルを読み込みます
Document doc = new Document(dataDir + "SetJavaScript.pdf");
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
//小数点以下2桁
//セパレータなし
//ネガスタイル = マイナス
//通貨なし
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
//フィールドの初期値を設定する
field.Value = "123";
dataDir = dataDir + "Restricted_out.pdf";
//結果の PDF を保存する
doc.Save(dataDir);
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

## 結論

このガイドでは、.NET 用の Aspose.PDF ライブラリを使用して PDF ドキュメントのフォーム フィールドに JavaScript を設定する方法を学習しました。概要を説明した手順に従うことで、JavaScript アクションをカスタマイズして、テキスト フィールドに対してさまざまな操作を実行できます。 PDF ファイルの操作の可能性を広げるために、Aspose.PDF for .NET の機能を自由にさらに探索してください。


### よくある質問

#### Q: Aspose.PDF for .NET を使用して、チェックボックスやラジオ ボタンなどの他のフォーム要素に JavaScript を追加できますか?

 A: はい、Aspose.PDF for .NET を使用すると、チェックボックス、ラジオ ボタン、ドロップダウン リストなどのさまざまなフォーム要素に JavaScript を追加できます。使用できます`JavascriptAction`クラスを使用して、さまざまなフォーム要素の JavaScript アクションを定義します。

#### Q: フォームフィールドで JavaScript を使用してユーザー入力を検証することはできますか?

 A: はい、JavaScript を使用してフォーム フィールドへのユーザー入力を検証できます。次のような JavaScript アクションを定義することで、`OnBlur`または`OnKeystroke`フォームフィールドの場合、入力されたデータを検証し、必要に応じてエラーメッセージを表示できます。

#### Q: Aspose.PDF for .NET を使用して複雑な JavaScript 関数を実行できますか?

 A: はい、Aspose.PDF for .NET を使用して複雑な JavaScript 関数を実行できます。カスタム JavaScript 関数を柔軟に定義し、それらをメソッド内で呼び出すことができます。`JavascriptAction`.

#### Q: Aspose.PDF for .NET は、このチュートリアルで説明されているもの以外の JavaScript イベントをサポートしていますか?

 A: はい、Aspose.PDF for .NET は、次のような幅広い JavaScript イベントをサポートしています。`OnMouseEnter`, `OnMouseExit`, `OnMouseDown` 、 そして`OnMouseUp`、とりわけ。これらのイベントを使用して、ユーザーの操作に基づいて JavaScript アクションをトリガーできます。

#### Q: Aspose.PDF for .NET を使用して、既存の PDF ドキュメントから JavaScript コードを抽出できますか?

 A: Aspose.PDF for .NET は、既存の PDF ドキュメントから JavaScript コードを抽出する機能を提供します。使用できます`JavascriptAction`PDF フォーム内の JavaScript アクションにアクセスして分析するためのクラスおよびその他の関連メソッド。