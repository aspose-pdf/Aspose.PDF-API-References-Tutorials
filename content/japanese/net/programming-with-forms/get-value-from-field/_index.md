---
title: PDFドキュメントのフィールドから値を取得
linktitle: PDFドキュメントのフィールドから値を取得
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用すると、PDF ドキュメント内のフォーム フィールドの値を簡単に取得できます。
type: docs
weight: 140
url: /ja/net/programming-with-forms/get-value-from-field/
---
このチュートリアルでは、Aspose.PDF for .NET を使用してフォーム フィールドの値を取得する方法を示します。このプロセスをガイドするために、C# ソース コードをステップごとに説明します。

## ステップ 1: 準備

必要なライブラリをインポートし、ドキュメント ディレクトリへのパスを設定していることを確認してください。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: ドキュメントを開く

PDF ドキュメントを開きます。

```csharp
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
```

## ステップ 3: フィールドを取得する

目的のフォーム フィールドを取得します (この例では、「textbox1」フィールドを使用しています)。

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## ステップ 4: フィールド値を取得する

を使用してフィールド値を取得します。`Value`財産：

```csharp
Console.WriteLine("PartialName: {0}", textBoxField.PartialName);
Console.WriteLine("Value: {0}", textBoxField.Value);
```

### Aspose.PDF for .NET を使用したフィールドからの値の取得のサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開いた文書
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
//フィールドを取得する
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
//フィールド値を取得する
Console.WriteLine("PartialName : {0} ", textBoxField.PartialName);
Console.WriteLine("Value : {0} ", textBoxField.Value);
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用してフォーム フィールドの値を取得する方法を学びました。これらの手順に従うと、Aspose.PDF を使用して PDF ドキュメント内の特定のフォーム フィールドの値を簡単に抽出できます。

### よくある質問

#### Q: フォームフィールドの名前を事前に知らなくても、その値を取得できますか?

 A: いいえ、Aspose.PDF for .NET を使用して値を取得するには、フォーム フィールドの名前または名前の一部を知っている必要があります。の`pdfDocument.Form["fieldname"]`構文では、値を含むフォーム フィールドのプロパティにアクセスするには、フォーム フィールドの正確な名前または名前の一部が必要です。

#### Q: PDF ドキュメントにフォームフィールドが存在しない場合はどうすればよいですか?

 A: PDF ドキュメントにフォーム フィールドが存在しない場合、`pdfDocument.Form["fieldname"]`構文が返されます`null`。このような場合には、次のことを確認して対処することが重要です。`null`例外を避けるために、フォームフィールドのプロパティにアクセスする前に。

#### Q: さまざまなタイプのフォームフィールド (チェックボックス、ラジオボタンなど) を処理して値を取得するにはどうすればよいですか?

 A: さまざまな種類のフォーム フィールドを処理するには、Aspose.PDF for .NET で利用可能な適切なフィールド クラスを使用できます。たとえば、次のように使用します。`CheckBoxField`チェックボックスを操作するには、`RadioButtonField`ラジオボタンを操作します。正しいフィールド オブジェクトを取得すると、値を含むそのプロパティにアクセスできるようになります。

#### Q: 複数のフォームフィールドの値を一度に取得できますか?

A: はい、ループまたは LINQ クエリを使用してフォーム フィールド コレクションを反復処理することで、複数のフォーム フィールドの値を一度に取得できます。このようにして、PDF ドキュメント内の各フォーム フィールドの値にプログラムでアクセスできます。

#### Q: フォームフィールドの値を変更し、その変更を PDF ドキュメントに保存し直すことはできますか?

 A: はい、Aspose.PDF for .NET を使用してフォーム フィールドの値を変更し、変更を PDF ドキュメントに保存し直すことができます。アップデート後、`Value`フォームフィールドのプロパティでは、`pdfDocument.Save()`元の PDF ドキュメントへの変更を保存するメソッド。