---
title: PDF ドキュメント内のすべてのフィールドから値を取得する
linktitle: PDF ドキュメント内のすべてのフィールドから値を取得する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用すると、PDF ドキュメント内のすべてのフォーム フィールドの値を簡単に取得できます。
type: docs
weight: 150
url: /ja/net/programming-with-forms/get-values-from-all-fields/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内のすべてのフォーム フィールドの値を取得する方法を説明します。このプロセスをガイドするために、C# ソース コードを段階的に説明します。

## ステップ1: 準備

必要なライブラリがインポートされ、ドキュメント ディレクトリへのパスが設定されていることを確認してください。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: ドキュメントを開く

PDF ドキュメントを開きます:

```csharp
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
```

## ステップ3: すべてのフィールドの値を取得する

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
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントを開く
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
//すべてのフィールドから値を取得する
foreach (Field formField in pdfDocument.Form)
{
	Console.WriteLine("Field Name : {0} ", formField.PartialName);
	Console.WriteLine("Value : {0} ", formField.Value);
}
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内のすべてのフォーム フィールドの値を取得する方法を学習しました。これらの手順に従うと、Aspose.PDF を使用して PDF ドキュメントからすべてのフォーム フィールドの値を簡単に抽出できます。

### よくある質問

#### Q: Aspose.PDF for .NET を使用してフォーム フィールドの値を取得しながら、その値を変更できますか?

 A: はい、Aspose.PDF for .NETを使用してフォームフィールドの値を取得しながら変更することができます。`Field`フォームフィールドを表すオブジェクトの場合、その`Value`プロパティを目的の値に設定します。必要な変更を行った後、更新された PDF ドキュメントを保存して変更を反映できます。

#### Q: 特定のフォーム フィールドをその種類 (テキスト フィールド、チェックボックスなど) に基づいてフィルター処理して取得するにはどうすればよいですか?

 A: 特定のフォームフィールドをそのタイプに基づいて取得するには、条件文またはLINQクエリを使用して、関心のあるフィールドをフィルタリングします。各フォームフィールドのタイプは、フィールドの`FieldType`プロパティを設定し、それに応じて値を取得します。

#### Q: PDF ドキュメントにフォーム フィールドがない場合はどうなりますか?

 A: PDF文書にフォームフィールドが含まれていない場合、`pdfDocument.Form`プロパティは空のコレクションを返します。このような場合、値を取得するためのループは実行されず、値は表示されません。

#### Q: フォーム フィールドの値を特定の順序で抽出したり、アルファベット順に並べ替えたりできますか?

A: フォーム フィールドが取得される順序は、PDF ドキュメントの基になる構造によって異なります。Aspose.PDF for .NET は、ドキュメントに追加された順序でフォーム フィールドを返します。フォーム フィールドを特定の順序で表示または処理する場合は、要件に基づいてカスタムの並べ替えロジックを実装できます。

#### Q: パスワードで保護されたフォーム フィールドを持つ暗号化された PDF ドキュメントをどのように処理できますか?

 A: Aspose.PDF for .NETは、暗号化されたPDFドキュメントやパスワードで保護されたフォームフィールドを操作する機能を提供します。ドキュメントを読み込む前に、`pdfDocument.Password`セキュリティで保護された PDF ドキュメントとそのフォーム フィールドにアクセスするためのプロパティ。