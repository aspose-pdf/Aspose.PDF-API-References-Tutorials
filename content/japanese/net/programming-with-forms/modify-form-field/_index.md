---
title: PDFドキュメントのフォームフィールドを変更する
linktitle: PDFドキュメントのフォームフィールドを変更する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用すると、PDF ドキュメントのフォーム フィールドを簡単に編集できます。
type: docs
weight: 190
url: /ja/net/programming-with-forms/modify-form-field/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内のフォーム フィールドを編集する方法を説明します。このプロセスをガイドするために、C# ソース コードをステップごとに説明します。

## ステップ 1: 準備

必要なライブラリをインポートし、ドキュメント ディレクトリへのパスを設定していることを確認してください。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: ドキュメントをロードする

既存の PDF ドキュメントをロードします。

```csharp
Document pdfDocument = new Document(dataDir + "ModifyFormField.pdf");
```

## ステップ 3: フォームフィールドを取得する

編集するフォームフィールドを取得します。

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## ステップ 4: フィールド値を変更する

フォームフィールドの値を変更します。

```csharp
textBoxField.Value = "New Value";
```

## ステップ 5: フィールドのプロパティを編集する

必要に応じて、追加のフォーム フィールドのプロパティを変更します。たとえば、次のように読み取り専用にできます。

```csharp
textBoxField.ReadOnly = true;
```

## ステップ 6: 編集したドキュメントを保存する

変更した PDF ドキュメントを保存します。

```csharp
dataDir = dataDir + "ModifyFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Aspose.PDF for .NET を使用したフォーム フィールドの変更のサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開いた文書
Document pdfDocument = new Document(dataDir + "ModifyFormField.pdf");
//フィールドを取得する
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
//フィールド値を変更する
textBoxField.Value = "New Value";
textBoxField.ReadOnly = true;
dataDir = dataDir + "ModifyFormField_out.pdf";
//更新されたドキュメントを保存する
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field modified successfully.\nFile saved at " + dataDir);
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内のフォーム フィールドを編集する方法を学びました。これらの手順に従うことで、特定のフィールドに簡単に移動し、その値を変更し、必要に応じてそのプロパティを調整することができます。


### よくある質問

#### Q: Aspose.PDF for .NET を使用して、単一の PDF ドキュメント内の複数のフォーム フィールドを編集できますか?

A: はい、Aspose.PDF for .NET を使用すると、単一の PDF ドキュメント内の複数のフォーム フィールドを編集できます。変更したいフォームフィールドごとにこのプロセスを繰り返すだけです。

#### Q: Aspose.PDF for .NET は、.NET Framework のすべてのバージョンと互換性がありますか?

A: はい、Aspose.PDF for .NET は、.NET Core や .NET Standard を含む .NET Framework のすべてのバージョンと互換性があります。

#### Q: Aspose.PDF for .NET を使用して、チェックボックスやラジオ ボタンなどの他のタイプのフォーム フィールドを変更できますか?

A: はい、Aspose.PDF for .NET は、チェックボックス、ラジオ ボタンなどを含む、さまざまなタイプのフォーム フィールドの変更をサポートしています。

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメントに新しいフォーム フィールドを追加するにはどうすればよいですか?

 A: PDF ドキュメントに新しいフォーム フィールドを追加するには、`Form`の財産`Document`にアクセスするためのクラス`Field`コレクションを作成し、プログラムで新しいフォーム フィールドを追加します。

#### Q: Aspose.PDF for .NET は C# 以外のプログラミング言語をサポートしていますか?

A: はい、Aspose.PDF for .NET は、C# に加えて、VB.NET や ASP.NET などのさまざまなプログラミング言語をサポートしています。