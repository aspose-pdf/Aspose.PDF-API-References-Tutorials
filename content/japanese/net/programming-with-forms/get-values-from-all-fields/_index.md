---
title: PDF ドキュメントのすべてのフィールドから値を取得
linktitle: PDF ドキュメントのすべてのフィールドから値を取得
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用すると、PDF ドキュメント内のすべてのフォーム フィールドの値を簡単に取得できます。
type: docs
weight: 150
url: /ja/net/programming-with-forms/get-values-from-all-fields/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内のすべてのフォーム フィールドの値を取得する方法を説明します。このプロセスをガイドするために、C# ソース コードをステップごとに説明します。

## ステップ 1: 準備

必要なライブラリをインポートし、ドキュメント ディレクトリへのパスを設定していることを確認してください。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: ドキュメントを開く

PDF ドキュメントを開きます。

```csharp
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
```

## ステップ 3: すべてのフィールドの値を取得する

ドキュメント内のすべてのフォーム フィールドをループし、その名前と値を取得します。

```csharp
foreach(Field formField in pdfDocument.Form)
{
Console.WriteLine("Field name: {0} ", formField.PartialName);
Console.WriteLine("Value: {0}", formField.Value);
}
```

### Aspose.PDF for .NET を使用してすべてのフィールドから値を取得するためのサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開いた文書
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
//すべてのフィールドから値を取得する
foreach (Field formField in pdfDocument.Form)
{
	Console.WriteLine("Field Name : {0} ", formField.PartialName);
	Console.WriteLine("Value : {0} ", formField.Value);
}
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内のすべてのフォーム フィールドの値を取得する方法を学びました。これらの手順に従うと、Aspose.PDF を使用して PDF ドキュメントからすべてのフォーム フィールドの値を簡単に抽出できます。

### よくある質問

#### Q: Aspose.PDF for .NET を使用してフォーム フィールドを取得するときに、その値を変更できますか?

 A: はい、Aspose.PDF for .NET を使用してフォーム フィールドを取得しながら、その値を変更できます。入手したら、`Field`フォームフィールドを表すオブジェクトがある場合は、そのオブジェクトを更新できます`Value`プロパティに必要な値を設定します。必要な変更を加えた後、更新された PDF ドキュメントを保存して変更を反映できます。

#### Q: 特定のフォームフィールドをタイプ (テキストフィールド、チェックボックスなど) に基づいてフィルタリングして取得するにはどうすればよいですか?

 A: 型に基づいて特定のフォーム フィールドを取得するには、条件ステートメントまたは LINQ クエリを使用して、対象のフィールドをフィルター処理します。各フォームフィールドのタイプは、フィールドの`FieldType`プロパティを選択し、それに応じて値を取得します。

#### Q: PDF ドキュメントにフォームフィールドがない場合はどうなりますか?

 A: PDF ドキュメントにフォーム フィールドが含まれていない場合、`pdfDocument.Form`プロパティは空のコレクションを返します。このような場合、値を取得するループは実行されず、値は表示されません。

#### Q: フォームフィールドの値を特定の順序で抽出したり、アルファベット順に並べ替えたりすることはできますか?

A: フォーム フィールドが取得される順序は、PDF ドキュメントの基礎となる構造によって異なります。 Aspose.PDF for .NET は、ドキュメントに追加された順序でフォーム フィールドを返します。フォームフィールドを特定の順序で表示または処理したい場合は、要件に基づいてカスタム並べ替えロジックを実装できます。

#### Q: パスワードで保護されたフォームフィールドを持つ暗号化された PDF ドキュメントを処理するにはどうすればよいですか?

 A: Aspose.PDF for .NET は、暗号化された PDF ドキュメントとパスワードで保護されたフォーム フィールドを操作する機能を提供します。ドキュメントをロードする前に、`pdfDocument.Password`プロパティを使用して、セキュリティで保護された PDF ドキュメントとそのフォーム フィールドにアクセスします。