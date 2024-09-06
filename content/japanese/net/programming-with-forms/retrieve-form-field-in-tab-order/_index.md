---
title: タブオーダーでフォームフィールドを取得する
linktitle: タブオーダーでフォームフィールドを取得する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用してタブ オーダーでフォーム フィールドを取得する方法を学習します。
type: docs
weight: 240
url: /ja/net/programming-with-forms/retrieve-form-field-in-tab-order/
---
Aspose.PDF for .NET を使用して C# で PDF ドキュメントを操作する場合、特定のタブ順序でフォーム フィールドを取得する必要があるシナリオに遭遇することがあります。これは、タブ順序に基づいてフォーム フィールドに対して操作を実行する場合に役立ちます。このチュートリアルでは、Aspose.PDF for .NET を使用してタブ順序でフォーム フィールドを取得する方法について、手順を追って説明します。

## 要件

始める前に、次の前提条件を満たしていることを確認してください。

- システムに Visual Studio がインストールされている
- Aspose.PDF for .NET ライブラリがインストールされている

それでは、タブ順序でフォーム フィールドを取得する手順について詳しく見ていきましょう。

## ステップ1: ドキュメントディレクトリの設定

まず、PDF文書が保存されているドキュメントディレクトリを設定する必要があります。これは、`dataDir`変数。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。

## ステップ2: PDFドキュメントの読み込み

このステップでは、Aspose.PDF for .NETを使用してPDFドキュメントを読み込み、`Document`クラスは、PDF ドキュメントを読み込み、操作する機能を提供します。

```csharp
Document doc = new Document(dataDir + "Test2.pdf");
```

ここ、`"Test2.pdf"`読み込む PDF ドキュメントの名前です。指定されたドキュメント ディレクトリにドキュメントが存在することを確認してください。

## ステップ3: タブオーダーでフォームフィールドを取得する

タブオーダーでフォームフィールドを取得するには、`FieldsInTabOrder`の財産`Page`クラス。このプロパティは、タブ順序でソートされたフォーム フィールドのリストを返します。

```csharp
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
     s += field. PartialName;
}
```

上記のコードスニペットでは、2ページ目からフォームフィールドを取得します（`doc.Pages[1]` ）を各フィールドで繰り返し処理して、部分的な名前を連結して`s`変数。このコード スニペットは、特定の要件に応じて変更できます。

## ステップ4: タブ順序の変更

フォームフィールドのタブ順序を変更したい場合は、`TabOrder`各フィールドのプロパティを変更し、新しいタブ順序の値を割り当てます。次に例を示します。

```csharp
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
```

上記のコードスニペットでは、3つのフォームフィールドに新しいタブ順序の値を割り当てています（`doc.Form[3]`, `doc.Form[1]` 、 そして`doc.Form[2]`）。特定の要件に応じて、フィールド インデックスとタブ順序の値を調整します。

## ステップ5: 変更したドキュメントを保存する

フォームフィールドのタブ順序を変更した後は、変更した文書を保存する必要があります。`Save`方法の`Document`クラス。

```csharp
doc.Save(dataDir + "39522_out.pdf");
```

ここ、`"39522_out.pdf"`変更されたドキュメントが保存される出力ファイルの名前です。出力ファイルの希望の名前と場所を指定します。

### Aspose.PDF for .NET を使用してタブ順序でフォーム フィールドを取得するためのサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Test2.pdf");
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
	s += field.PartialName;
}
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
doc.Save(dataDir + "39522_out.pdf");
Document doc1 = new Document(dataDir + "39522_out.pdf");
s = "";
foreach (Field field in doc1.Pages[1].FieldsInTabOrder)
{
	s += field.PartialName;
}
string index = "";
foreach (Field field in doc1.Form)
{
	index += field.TabOrder;
}
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用してタブ オーダーでフォーム フィールドを取得する方法を学習しました。PDF ドキュメントの読み込み、タブ オーダーでのフォーム フィールドの取得、タブ オーダーの変更、変更されたドキュメントの保存に関する手順について説明しました。これらの手順に従うことで、フォーム フィールドを効率的に操作し、要件に応じてタブ シーケンスをカスタマイズできます。


### よくある質問

#### Q: 取得したフォーム フィールドを C# コードでさらに処理するために使用するにはどうすればよいですか?

 A: 取得したフォームフィールドをC#コードで使用したい場合は、次のようなプロパティにアクセスします。`Value`, `Name`, `Rect`これらのプロパティを使用すると、必要に応じてフォーム フィールド データを読み取り、変更できます。

#### Q: PDF ドキュメントのすべてのページからタブ順にフォーム フィールドを取得できますか?

 A: はい、各ページを反復処理して、PDF文書のすべてのページからフォームフィールドを取得できます。`FieldsInTabOrder`チュートリアルに示されているように、プロパティを設定します。これにより、すべてのページでタブ シーケンスによって並べ替えられたフォーム フィールドが表示されます。

#### Q: テキスト フィールドやチェックボックスなど、特定の種類のフォーム フィールドのみをタブ オーダーで取得することは可能ですか?

A: はい、タブ順序でフォーム フィールドを取得した後、テキスト フィールドやチェックボックスなどのタイプに基づいてフォーム フィールドをフィルターできます。条件文を使用して各フォーム フィールドのタイプを確認し、それに応じて処理することができます。

#### Q: タブ順序ではなく名前に基づいてフォーム フィールドを取得できますか?

 A: はい、フォームフィールドの名前に基づいて取得することができます。`doc.Form`コレクションとフィールド名をインデックスとして指定します。たとえば、`doc.Form["fieldName"]`指定された名前のフォーム フィールドを取得します。

#### Q: Aspose.PDF for .NET は暗号化された PDF ドキュメントの操作をサポートしていますか?

A: はい、Aspose.PDF for .NET は暗号化された PDF ドキュメントの操作をサポートしています。適切なパスワード パラメータを使用して、暗号化された PDF ファイルを読み込み、操作できます。