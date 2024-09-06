---
title: PDF ドキュメント内の複数の表を削除する
linktitle: PDF ドキュメント内の複数の表を削除する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ドキュメント内の複数のテーブルを削除する方法を学習します。
type: docs
weight: 150
url: /ja/net/programming-with-tables/remove-multiple-tables/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内の複数のテーブルを削除する方法を段階的に説明します。提供されている C# ソース コードについて説明し、実装方法を示します。

## ステップ1: 既存のPDF文書を読み込む
まず、次のコードを使用して既存の PDF ドキュメントを読み込む必要があります。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//既存のPDF文書を読み込む
Document pdfDocument = new Document(dataDir + "Table_input2.pdf");
```

## ステップ2: テーブルを見つけるためのTableAbsorberオブジェクトを作成する
次に、PDF ドキュメント内の表を見つけるための TableAbsorber オブジェクトを作成します。

```csharp
//テーブルを見つけるためのTableAbsorberオブジェクトを作成する
TableAbsorber absorber = new TableAbsorber();
```

## ステップ3: アブソーバーで2ページ目にアクセスする
次に、アブソーバーを使用して PDF ドキュメントの 2 ページ目にアクセスします。

```csharp
//吸収剤の2ページ目をご覧ください
absorb.Visit(pdfDocument.Pages[1]);
```

## ステップ4: テーブルコレクションのコピーを取得する
テーブルを削除するには、テーブル コレクションのコピーを取得する必要があります。

```csharp
//テーブルコレクションのコピーを入手する
AbsorbedTable[] tables = new AbsorbedTable[absorb.TableList.Count];
absorb.TableList.CopyTo(tables, 0);
```

## ステップ5: コレクションのコピーを参照してテーブルを削除する
次に、テーブルのコレクションのコピーを反復処理して、テーブルを 1 つずつ削除します。

```csharp
//コレクションのコピーを参照してテーブルを削除します
foreach(AbsorbedTable table in tables)
     absorb.Remove(table);
```

## ステップ6: ドキュメントを保存する
最後に、変更した PDF ドキュメントを保存します。

```csharp
//文書を保存する
pdfDocument.Save(dataDir + "Table2_out.pdf");
```

### Aspose.PDF for .NET を使用して複数のテーブルを削除するためのサンプル ソース コード

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//既存のPDF文書を読み込む
Document pdfDocument = new Document(dataDir + "Table_input2.pdf");

//テーブルを見つけるためのTableAbsorberオブジェクトを作成する
TableAbsorber absorber = new TableAbsorber();

//吸収剤付きの2ページ目をご覧ください
absorber.Visit(pdfDocument.Pages[1]);

//テーブルコレクションのコピーを取得する
AbsorbedTable[] tables = new AbsorbedTable[absorber.TableList.Count];
absorber.TableList.CopyTo(tables, 0);

//コレクションのコピーをループしてテーブルを削除する
foreach (AbsorbedTable table in tables)
	absorber.Remove(table);

//ドキュメントを保存
pdfDocument.Save(dataDir + "Table2_out.pdf");
```

## 結論
おめでとうございます！Aspose.PDF for .NET を使用して PDF ドキュメント内の複数のテーブルを削除する方法を学習しました。このステップ バイ ステップ ガイドでは、ドキュメントをアップロードし、テーブルを見つけて削除する方法を説明しました。これで、この知識を自分のプロジェクトに適用できます。

### PDF ドキュメント内の複数のテーブルを削除する方法に関する FAQ

#### Q: PDF ドキュメント内のすべての表ではなく、特定の表を削除できますか?

A: はい、Aspose.PDF for .NET を使用すると、PDF ドキュメント内のすべてのテーブルではなく、特定のテーブルを削除できます。提供されている例では、2 ページ目のすべてのテーブルが削除されます。ただし、要件に基づいて特定のテーブルを対象にして削除するようにコードを変更することもできます。これを行うには、削除するテーブルを識別し、`absorber.Remove(table)`削除する特定のテーブルごとにメソッドを使用します。

#### Q: PDF ドキュメント内の複数のページから表を削除するにはどうすればよいですか?

回答: PDF文書の複数のページから表を削除するには、各ページごとにこのプロセスを繰り返す必要があります。提供されている例では、コードは2ページ目からのみ表を削除します。`pdfDocument.Pages[1]`他のページからテーブルを削除するには、ページインデックスを置き換えることで、各目的のページに同様のコードを使用できます（例：`pdfDocument.Pages[2]`, `pdfDocument.Pages[3]`、 等々）。

#### Q: 指定されたページに存在しないテーブルを削除しようとするとどうなりますか?

A: 指定されたページに存在しないテーブルを削除しようとしても、エラーにはなりません。`absorber.Remove(table)`この方法は削除要求を無視し、PDF ドキュメントは変更されません。

#### Q: ドキュメントを保存した後でテーブルの削除を元に戻すことはできますか?

A: いいえ、表を削除した後に変更した PDF ドキュメントを保存すると、変更は永続的になり、表の削除を元に戻すことはできません。したがって、PDF ドキュメントからコンテンツを削除するときは、元のデータが失われるため、注意が必要です。

#### Q: この方法で削除できるテーブルの種類に制限はありますか?

A: このチュートリアルで紹介する方法を使用すると、表の内容に基づいて制限なく PDF ドキュメントから表を削除できます。ただし、表を削除しても残りのコンテンツや読みやすさに悪影響が及ばないように、ドキュメントの全体的な構造とレイアウトを考慮することが重要です。