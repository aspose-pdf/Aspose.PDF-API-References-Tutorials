---
title: PDF ドキュメントのフィールドから値を取得する
linktitle: PDF ドキュメントのフィールドから値を取得する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用すると、PDF ドキュメント内のフォーム フィールドの値を簡単に取得できます。
type: docs
weight: 140
url: /ja/net/programming-with-forms/get-value-from-field/
---
このチュートリアルでは、Aspose.PDF for .NET を使用してフォーム フィールドの値を取得する方法を説明します。このプロセスをガイドするために、C# ソース コードを段階的に説明します。

## ステップ1: 準備

必要なライブラリがインポートされ、ドキュメント ディレクトリへのパスが設定されていることを確認してください。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: ドキュメントを開く

PDF ドキュメントを開きます:

```csharp
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
```

## ステップ3: フィールドを取得する

目的のフォーム フィールドを取得します (この例では、「textbox1」フィールドを使用しています)。

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## ステップ4: フィールド値を取得する

フィールド値を取得するには、`Value`財産：

```csharp
Console.WriteLine("PartialName: {0}", textBoxField.PartialName);
Console.WriteLine("Value: {0}", textBoxField.Value);
```

### Aspose.PDF for .NET を使用してフィールドから値を取得するためのサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントを開く
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
//フィールドを取得する
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
//フィールド値を取得する
Console.WriteLine("PartialName : {0} ", textBoxField.PartialName);
Console.WriteLine("Value : {0} ", textBoxField.Value);
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用してフォーム フィールドの値を取得する方法を学習しました。これらの手順に従うと、Aspose.PDF を使用して PDF ドキュメント内の特定のフォーム フィールドの値を簡単に抽出できます。

### よくある質問

#### Q: フォーム フィールドの名前を事前に知らなくても、その値を取得できますか?

 A: いいえ、Aspose.PDF for .NETを使用して値を取得するには、フォームフィールドの名前または部分的な名前を知る必要があります。`pdfDocument.Form["fieldname"]`構文では、値を含むプロパティにアクセスするために、フォーム フィールドの正確な名前または部分的な名前が必要です。

#### Q: PDF ドキュメントにフォーム フィールドが存在しない場合はどうなりますか?

 A: PDF文書にフォームフィールドが存在しない場合は、`pdfDocument.Form["fieldname"]`構文は返されます`null`このようなケースでは、次の点をチェックして対処することが重要です。`null`例外を回避するために、フォーム フィールドのプロパティにアクセスする前に。

#### Q: さまざまな種類のフォーム フィールド (チェックボックス、ラジオ ボタンなど) を処理して値を取得するにはどうすればよいですか?

 A: さまざまなタイプのフォームフィールドを処理するには、Aspose.PDF for .NETで利用可能な適切なフィールドクラスを使用できます。たとえば、`CheckBoxField`チェックボックスを操作するには`RadioButtonField`ラジオ ボタンを操作します。正しいフィールド オブジェクトを取得したら、値を含むそのプロパティにアクセスできます。

#### Q: 複数のフォーム フィールドの値を一度に取得できますか?

A: はい、ループまたは LINQ クエリを使用してフォーム フィールド コレクションを反復処理することで、複数のフォーム フィールドの値を一度に取得できます。この方法では、PDF ドキュメント内の各フォーム フィールドの値にプログラムでアクセスできます。

#### Q: フォーム フィールドの値を変更し、その変更を PDF ドキュメントに保存することは可能ですか?

 A: はい、Aspose.PDF for .NETを使用してフォームフィールドの値を変更し、変更内容をPDFドキュメントに保存することができます。`Value`フォームフィールドのプロパティでは、`pdfDocument.Save()`元の PDF ドキュメントへの変更を保存する方法。