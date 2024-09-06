---
title: スタイルテーブル要素
linktitle: スタイルテーブル要素
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用してテーブル要素をフォーマットする方法を学びます。スタイルとプロパティをカスタマイズするためのステップバイステップ ガイド。
type: docs
weight: 170
url: /ja/net/programming-with-tagged-pdf/style-table-element/
---
この詳細なチュートリアルでは、提供されている C# ソース コードを使用して、Aspose.PDF for .NET を使用して配列要素をフォーマットする手順を段階的に説明します。配列要素のスタイルとプロパティをカスタマイズする方法を理解するには、以下の手順に従ってください。

## ステップ1: 環境の設定

始める前に、Aspose.PDF for .NET を使用するように開発環境が構成されていることを確認してください。これには、Aspose.PDF ライブラリのインストールと、それを参照するようにプロジェクトを構成することが含まれます。

## ステップ2: ドキュメントの作成

この手順では、新しいドキュメント オブジェクト Aspose.PDF を作成します。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメント作成
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of table formatting");
taggedContent.SetLanguage("fr-FR");
```

新しいドキュメントを作成し、ドキュメントのタイトルと言語を設定しました。

## ステップ3: ルート構造要素を取得する

このステップでは、ドキュメントのルート構造要素を取得します。

```csharp
//ルート構造要素を取得する
StructureElement rootElement = taggedContent.RootElement;
```

配列要素のコンテナとして機能するルート構造要素を取得しました。

## ステップ4: 配列構造要素の作成

次に、ドキュメントの新しいテーブル構造要素を作成しましょう。

```csharp
//配列構造要素を作成する
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

新しい配列構造要素を作成し、それをルート構造要素に追加しました。

## ステップ5: 配列要素のスタイルとプロパティをカスタマイズする

このステップでは、配列要素のスタイルとプロパティをカスタマイズします。

```csharp
//配列要素のスタイルとプロパティをカスタマイズする
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement. Alignment = HorizontalAlignment. Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement. ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement. DefaultColumnWidth = "70";
tableElement. IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement. Left = 0F;
tableElement. Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;

//繰り返し行のスタイルをカスタマイズする
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

背景色、境界線、配置、デフォルトのセル スタイル、余白、列幅など、さまざまなプロパティを使用してテーブル要素をカスタマイズしました。

## ステップ6: 表のヘッダー、本文、フッターを追加する

次に、テーブル要素にテーブル ヘッダー、本文、フッターを追加しましょう。
```csharp
//表のヘッダーを追加する
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

//表の行数と列数
int rowCount = 10;
int colCount = 5;
int rowIndex;
int colIndex;

//表のヘッダー行を作成する
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
}

//表本体の行を追加する
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

//表のフッターラインを追加する
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

対応する要素を使用して、ヘッダー、本文行、フッター行をテーブルに追加しました。

## ステップ7: タグ付きPDF文書を保存する

スタイル設定されたテーブル要素を使用してドキュメントを作成したので、タグ付き PDF ドキュメントとして保存します。

```csharp
//タグ付けされたPDF文書を保存する
document.Save(dataDir + "StyleTableElement.pdf");
```

タグ付けされた PDF ドキュメントを指定されたディレクトリに保存しました。

## ステップ8: PDF/UAコンプライアンス検証

次に、ドキュメントの PDF/UA 準拠を検証します。

```csharp
//PDF/UA 準拠チェック
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

タグ付き PDF ドキュメントをアップロードし、XML レポートを生成して PDF/UA 準拠を検証しました。

### Aspose.PDF for .NET を使用したスタイル テーブル要素のサンプル ソース コード 

```csharp

//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//ドキュメントを作成
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");

//ルート構造要素を取得する
StructureElement rootElement = taggedContent.RootElement;

//テーブル構造要素を作成する
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement.DefaultColumnWidth = "70";
tableElement.IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement.Left = 0F;
tableElement.Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 10;
int colCount = 5;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
	}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
}

//タグ付き PDF ドキュメントを保存
document.Save(dataDir + "StyleTableElement.pdf");

//PDF/UA準拠の確認
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して配列要素をフォーマットする方法を学習しました。テーブル要素のスタイルとプロパティをカスタマイズし、ヘッダー、本文行、フッターを追加し、タグ付き PDF ドキュメントを保存し、PDF/UA 準拠を検証しました。

### よくある質問

#### Q: Aspose.PDF for .NET を使用して配列要素をフォーマットするこのチュートリアルの目的は何ですか?

A: このチュートリアルの目的は、Aspose.PDF for .NET を使用して PDF ドキュメント内の配列要素をフォーマットするプロセスを説明することです。配列要素のスタイルとプロパティをカスタマイズするのに役立つ、ステップバイステップの手順と C# ソース コードの例を提供します。

#### Q: このチュートリアルに従うための前提条件は何ですか?

A: 開始する前に、Aspose.PDF for .NET を使用するように開発環境が設定されていることを確認してください。これには、Aspose.PDF ライブラリをインストールし、それを参照するようにプロジェクトを構成することが含まれます。

#### Q: Aspose.PDF for .NET を使用して新しい PDF ドキュメントを作成し、そのタイトルと言語を設定するにはどうすればよいでしょうか?

 A: 新しいPDF文書を作成するには、`Document` Aspose.PDF ライブラリのオブジェクトです。チュートリアルで提供される C# ソース コードは、ドキュメントを作成し、そのタイトルと言語のプロパティを設定する方法を示しています。

#### Q: PDF ドキュメントのルート構造要素の重要性は何ですか?

A: ルート構造要素は、他の構造要素のコンテナとして機能し、PDF ドキュメントのコンテンツを整理および分類するのに役立ちます。ドキュメントの論理構造を確立する上で重要な役割を果たします。

#### Q: Aspose.PDF for .NET を使用して配列構造要素を作成およびカスタマイズするにはどうすればよいですか?

 A: 配列構造要素を作成するには、`CreateTableElement()`メソッド。チュートリアルのソース コードには、背景色、境界線、配置、列幅など、テーブル要素のさまざまなプロパティをカスタマイズする例が示されています。

#### Q: 配列要素内のテーブル セルのスタイルとプロパティをカスタマイズできますか?

A: はい、チュートリアルでは、ヘッダー、本文の行、フッターなど、テーブル要素全体のスタイルとプロパティをカスタマイズする方法について説明します。ただし、個々のテーブルセルのカスタマイズについては具体的に説明していません。

#### Q: テーブル要素にヘッダー、本文行、フッターを追加するにはどうすればよいですか?

A: チュートリアルでは、Aspose.PDF for .NET が提供する適切なメソッドを使用して、ヘッダー、本文行、フッターを作成し、テーブル要素に追加する方法を説明します。

#### Q: PDF/UA 準拠とは何ですか? また、タグ付けされた PDF ドキュメントに対してこれを検証するにはどうすればよいですか?

 A: PDF/UA準拠は、PDF文書がアクセシビリティ標準に準拠していることを保証し、障害を持つユーザーにとってよりアクセスしやすくなります。このチュートリアルでは、`Validate()`メソッドを実行し、XML コンプライアンス レポートを生成します。

#### Q: これらの概念を独自の .NET アプリケーションに組み込むにはどうすればよいですか?

A: 提供されている C# ソース コードの例をガイドとして使用して、独自の .NET アプリケーションで配列要素のフォーマットを実装できます。要件に合わせてコードを変更および調整し、プロジェクトに統合します。

#### Q: PDF ドキュメント内の配列要素をフォーマットするための推奨されるベスト プラクティスはありますか?

A: 配列要素 (テーブル) をフォーマットするときは、コンテンツの読みやすさとアクセシビリティを考慮してください。明確で読みやすいフォント、適切な色を使用し、一貫したレイアウトを維持してください。アクセシビリティ標準が満たされていることを確認するために、PDF/UA 準拠を検証してください。

#### Q: PDF ドキュメントのカスタマイズには、Aspose.PDF for .NET の他にどのような機能を利用できますか?

A: Aspose.PDF for .NET は、テキスト操作、画像の挿入、フォーム フィールドの管理、デジタル署名、注釈など、PDF ドキュメントをカスタマイズするためのさまざまな機能を提供します。追加機能の詳細については、公式ドキュメントとリソースを参照してください。