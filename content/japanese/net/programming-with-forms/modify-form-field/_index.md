---
title: PDF ドキュメントのフォーム フィールドを変更する
linktitle: PDF ドキュメントのフォーム フィールドを変更する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用すると、PDF ドキュメント内のフォーム フィールドを簡単に編集できます。
type: docs
weight: 190
url: /ja/net/programming-with-forms/modify-form-field/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントのフォーム フィールドを編集する方法を説明します。このプロセスをガイドするために、C# ソース コードを段階的に説明します。

## ステップ1: 準備

必要なライブラリがインポートされ、ドキュメント ディレクトリへのパスが設定されていることを確認してください。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: ドキュメントを読み込む

既存の PDF ドキュメントを読み込みます:

```csharp
Document pdfDocument = new Document(dataDir + "ModifyFormField.pdf");
```

## ステップ3: フォームフィールドを取得する

編集したいフォーム フィールドを取得します。

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## ステップ4: フィールド値を変更する

フォームフィールドの値を変更します。

```csharp
textBoxField.Value = "New Value";
```

## ステップ5: フィールドプロパティを編集する

必要に応じて追加のフォーム フィールド プロパティを変更します。たとえば、読み取り専用にすることができます。

```csharp
textBoxField.ReadOnly = true;
```

## ステップ6: 編集した文書を保存する

変更した PDF ドキュメントを保存します。

```csharp
dataDir = dataDir + "ModifyFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Aspose.PDF for .NET を使用してフォーム フィールドを変更するためのサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントを開く
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

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内のフォーム フィールドを編集する方法を学習しました。これらの手順に従うことで、特定のフィールドに簡単に移動してその値を変更し、必要に応じてそのプロパティを調整できます。


### よくある質問

#### Q: Aspose.PDF for .NET を使用して、単一の PDF ドキュメント内の複数のフォーム フィールドを編集できますか?

A: はい、Aspose.PDF for .NET を使用すると、単一の PDF ドキュメント内の複数のフォーム フィールドを編集できます。変更するフォーム フィールドごとにこのプロセスを繰り返すだけです。

#### Q: Aspose.PDF for .NET は、すべてのバージョンの .NET Framework と互換性がありますか?

A: はい、Aspose.PDF for .NET は、.NET Core および .NET Standard を含むすべてのバージョンの .NET Framework と互換性があります。

#### Q: Aspose.PDF for .NET を使用して、チェックボックスやラジオ ボタンなどの他の種類のフォーム フィールドを変更できますか?

A: はい、Aspose.PDF for .NET は、チェックボックス、ラジオ ボタンなど、さまざまな種類のフォーム フィールドの変更をサポートしています。

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメントに新しいフォーム フィールドを追加するにはどうすればよいですか?

 A: PDF文書に新しいフォームフィールドを追加するには、`Form`の財産`Document`アクセスするためのクラス`Field`コレクションを作成し、プログラムで新しいフォーム フィールドを追加します。

#### Q: Aspose.PDF for .NET は C# 以外のプログラミング言語もサポートしていますか?

A: はい、Aspose.PDF for .NET は C# に加えて、VB.NET や ASP.NET などのさまざまなプログラミング言語をサポートしています。