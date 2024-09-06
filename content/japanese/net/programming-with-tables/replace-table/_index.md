---
title: PDF ドキュメント内の表を置換
linktitle: PDF ドキュメント内の表を置換
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ドキュメント内の表を置き換える方法を学習します。
type: docs
weight: 180
url: /ja/net/programming-with-tables/replace-table/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内の表を置き換える方法を段階的に説明します。提供されている C# ソース コードについて説明し、実装方法を示します。

## ステップ1: 既存のPDF文書を読み込む
まず、次のコードを使用して既存の PDF ドキュメントを読み込む必要があります。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//既存のPDF文書を読み込む
Document pdfDocument = new Document(dataDir + @"Table_input.pdf");
```

## ステップ2: テーブルを見つけるためのTableAbsorberオブジェクトを作成する
次に、PDF ドキュメント内の表を見つけるための TableAbsorber オブジェクトを作成します。

```csharp
//テーブルを見つけるためのTableAbsorberオブジェクトを作成する
TableAbsorber absorber = new TableAbsorber();
```

## ステップ3: アブソーバーで最初のページにアクセスする
次に、アブソーバーを使用して PDF ドキュメントの最初のページにアクセスします。

```csharp
//吸収装置付きの最初のページをご覧ください
absorb.Visit(pdfDocument.Pages[1]);
```

## ステップ4: ページの最初のテーブルを取得する
テーブルを置き換えるには、ページの最初のテーブルを取得します。

```csharp
//ページの最初のテーブルを取得する
AbsorbedTable table = absorb.TableList[0];
```

## ステップ5: 新しいテーブルを作成する
次に、必要な列とセルを含む新しいテーブルを作成します。

```csharp
Table newTable = new Table();
newTable.ColumnWidths = "100 100 100";
newTable.DefaultCellBorder = new BorderInfo(BorderSide.All, 1F);

Row row = newTable.Rows.Add();
row. Cells. Add("Col 1");
row. Cells. Add("Col 2");
row. Cells. Add("Col 3");
```

## ステップ6: 既存のテーブルを新しいテーブルに置き換える
ここで、ドキュメントの最初のページにある既存のテーブルを新しいテーブルに置き換えます。

```csharp
//テーブルを新しいテーブルに置き換える
absorb.Replace(pdfDocument.Pages[1], table, newTable);
```

## ステップ7: ドキュメントを保存する
最後に、変更した PDF ドキュメントを保存します。

```csharp
pdfDocument.Save(dataDir + "TableReplaced_out.pdf");
```

### Aspose.PDF for .NET を使用したテーブル置換のサンプル ソース コード

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//既存のPDF文書を読み込む
Document pdfDocument = new Document(dataDir + @"Table_input.pdf");

//テーブルを見つけるためのTableAbsorberオブジェクトを作成する
TableAbsorber absorber = new TableAbsorber();

//アブソーバーで最初のページにアクセス
absorber.Visit(pdfDocument.Pages[1]);

//ページの最初のテーブルを取得する
AbsorbedTable table = absorber.TableList[0];

//新しいテーブルを作成
Table newTable = new Table();
newTable.ColumnWidths = "100 100 100";
newTable.DefaultCellBorder = new BorderInfo(BorderSide.All, 1F);

Row row = newTable.Rows.Add();
row.Cells.Add("Col 1");
row.Cells.Add("Col 2");
row.Cells.Add("Col 3");

//テーブルを新しいものに交換する
absorber.Replace(pdfDocument.Pages[1], table, newTable);

//ドキュメントを保存
pdfDocument.Save(dataDir + "TableReplaced_out.pdf");
```

## 結論
おめでとうございます！Aspose.PDF for .NET を使用して PDF ドキュメント内のテーブルを置き換える方法を学習しました。このステップ バイ ステップ ガイドでは、ドキュメントを読み込み、既存のテーブルを検索し、新しいテーブルを作成して、それを置き換える方法を説明しました。これで、この知識を自分のプロジェクトに適用できます。

### PDF ドキュメント内の表の置き換えに関する FAQ

#### Q: この方法を使用して、同じ PDF ドキュメント内の複数のテーブルを置き換えることはできますか?

 A: はい、同じPDF文書内の複数の表を置き換えることができます。置き換えたい表ごとに同じ手順を実行してください。`AbsorbedTable`各テーブルにオブジェクトを使用して`TableAbsorber`対応する新しいテーブルを作成し、`absorber.Replace()`既存の各テーブルをそれぞれの新しいテーブルに置き換える方法。

#### Q: 新しいテーブルの列数が元のテーブルと異なる場合はどうなりますか?

A: 新しい表の列数が元の表と異なる場合、変更された PDF ドキュメントで予期しない動作やレイアウトの問題が発生する可能性があります。シームレスに置き換えるには、新しい表の構造 (列数と幅) が元の表の構造と一致していることを確認することが重要です。

#### Q: 最初のページ以外の特定のページの表を置き換えることはできますか?

 A: はい、最初のページ以外の特定のページのテーブルを置き換えるには、`pdfDocument.Pages[]`メソッド呼び出しを取得する際に`AbsorbedTable`オブジェクト。例えば、2ページ目の表を置き換えるには、`pdfDocument.Pages[2]`.

#### Q: 背景色や境界線を追加するなど、新しいテーブルの外観をカスタマイズできますか?

 A: はい、新しいテーブルの外観は、さまざまなプロパティを設定することでカスタマイズできます。`Table`およびそのセルを設定します。たとえば、`BackgroundColor`セルのプロパティを設定すると背景色を追加できます。`DefaultCellBorder`新しいテーブルまたは個々のセルのプロパティを使用して境界線を追加します。

#### Q: 表を置き換えると、PDF ドキュメントの残りの部分のコンテンツ レイアウトに影響しますか?

A: 新しいテーブルのサイズや構造が元のテーブルと大きく異なる場合、テーブルを置き換えるとコンテンツのレイアウトに影響する可能性があります。ページの残りのコンテンツは、新しいテーブルに合わせてリフローされます。レイアウトの問題を回避するには、新しいテーブルが既存のレイアウトにシームレスに収まるように慎重に設計することが重要です。