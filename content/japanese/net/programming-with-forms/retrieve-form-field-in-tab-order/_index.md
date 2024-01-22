---
title: フォームフィールドをタブオーダーで取得
linktitle: フォームフィールドをタブオーダーで取得
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用してフォーム フィールドをタブ オーダーで取得する方法を学びます。
type: docs
weight: 240
url: /ja/net/programming-with-forms/retrieve-form-field-in-tab-order/
---
Aspose.PDF for .NET を使用して C# で PDF ドキュメントを操作する場合、特定のタブ オーダーでフォーム フィールドを取得する必要があるシナリオに遭遇することがあります。これは、タブ シーケンスに基づいてフォーム フィールドに対して操作を実行する場合に便利です。このチュートリアルでは、Aspose.PDF for .NET を使用してフォーム フィールドをタブ オーダーで取得する方法を段階的に説明します。

## 要件

始める前に、次の前提条件を満たしていることを確認してください。

- システムにインストールされている Visual Studio
- Aspose.PDF for .NET ライブラリがインストールされている

次に、タブ オーダーでフォーム フィールドを取得する手順を見てみましょう。

## ステップ 1: ドキュメント ディレクトリの設定

まず、PDF ドキュメントが配置されるドキュメント ディレクトリを設定する必要があります。これを行うには、ディレクトリへのパスを指定します。`dataDir`変数。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを置き換えます。

## ステップ 2: PDF ドキュメントをロードする

このステップでは、Aspose.PDF for .NET を使用して PDF ドキュメントを読み込みます。の`Document`このクラスは、PDF ドキュメントをロードして操作する機能を提供します。

```csharp
Document doc = new Document(dataDir + "Test2.pdf");
```

ここ、`"Test2.pdf"`は、ロードする PDF ドキュメントの名前です。指定したドキュメント ディレクトリにドキュメントが存在することを確認してください。

## ステップ 3: タブ オーダーでフォーム フィールドを取得する

フォームフィールドをタブオーダーで取得するには、`FieldsInTabOrder`の財産`Page`クラス。このプロパティは、タブシーケンスでソートされたフォームフィールドのリストを返します。

```csharp
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
     s += field. PartialName;
}
```

上記のコード スニペットでは、2 ページ目 (`doc.Pages[1]` )、各フィールドを反復処理して、部分的な名前を連結します。`s`変数。特定の要件に基づいてこのコード スニペットを変更できます。

## ステップ 4: タブの順序を変更する

フォームフィールドのタブオーダーを変更したい場合は、`TabOrder`各フィールドのプロパティを設定し、新しいタブ オーダー値を割り当てます。以下に例を示します。

```csharp
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
```

上記のコード スニペットでは、新しいタブ オーダーの値を 3 つのフォーム フィールド (`doc.Form[3]`, `doc.Form[1]` 、 そして`doc.Form[2]`）。特定の要件に応じてフィールド インデックスとタブ オーダーの値を調整します。

## ステップ 5: 変更したドキュメントを保存する

フォームフィールドのタブオーダーを変更した後、変更したドキュメントを保存する必要があります。これを行うには、`Save`の方法`Document`クラス。

```csharp
doc.Save(dataDir + "39522_out.pdf");
```

ここ、`"39522_out.pdf"`変更されたドキュメントが保存される出力ファイルの名前です。出力ファイルの目的の名前と場所を指定します。

### Aspose.PDF for .NET を使用したタブ オーダーでフォーム フィールドを取得するサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
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

このチュートリアルでは、Aspose.PDF for .NET を使用してフォーム フィールドをタブ オーダーで取得する方法を学びました。 PDF ドキュメントのロード、タブ オーダーでのフォーム フィールドの取得、タブ オーダーの変更、および変更されたドキュメントの保存に関連する手順について説明しました。これらの手順に従うことで、フォーム フィールドを効率的に操作し、要件に応じてタブの順序をカスタマイズできます。


### よくある質問

#### Q: 取得したフォーム フィールドを C# コードでさらに処理するために使用するにはどうすればよいですか?

 A: 取得したフォーム フィールドは、次のようなプロパティにアクセスすることで C# コードで使用できます。`Value`, `Name`, `Rect`これらのプロパティを使用すると、必要に応じてフォーム フィールド データを読み取り、変更できます。

#### Q: PDF ドキュメントのすべてのページからフォーム フィールドをタブ オーダーで取得できますか?

 A: はい、各ページを反復処理して、`FieldsInTabOrder`チュートリアルで示されているプロパティ。これにより、すべてのページにわたってフォーム フィールドがタブの順序で並べ替えられます。

#### Q: テキスト フィールドやチェックボックスなど、特定の種類のフォーム フィールドのみをタブ オーダーで取得することはできますか?

A: はい、タブ オーダーでフォーム フィールドを取得した後、テキスト フィールドやチェックボックスなどのタイプに基づいてフォーム フィールドをフィルタリングできます。条件ステートメントを使用して、各フォームフィールドのタイプを確認し、それに応じて処理することができます。

#### Q: タブ オーダーではなく名前に基づいてフォーム フィールドを取得できますか?

 A: はい、フォームフィールドを名前に基づいて取得するには、`doc.Form`コレクションを作成し、インデックスとしてフィールド名を指定します。例えば、`doc.Form["fieldName"]`指定された名前のフォームフィールドを取得します。

#### Q: Aspose.PDF for .NET は、暗号化された PDF ドキュメントの操作をサポートしていますか?

A: はい、Aspose.PDF for .NET は、暗号化された PDF ドキュメントの操作をサポートします。適切なパスワード パラメーターを使用して、暗号化された PDF ファイルをロードして操作できます。