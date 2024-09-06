---
title: テーブルセルのスタイル
linktitle: テーブルセルのスタイル
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用してテーブル セルにスタイルを設定する方法を学習します。テーブルの作成とカスタマイズに関するステップ バイ ステップ ガイドです。
type: docs
weight: 160
url: /ja/net/programming-with-tagged-pdf/style-table-cell/
---
Aspose.PDF for .NET を使用してテーブル セルをフォーマットする詳細なチュートリアルへようこそ。このガイドでは、提供されている C# ソース コードの各手順を詳しく説明し、テーブル セルのスタイル設定方法を理解できるようにします。開始する前に、Aspose.PDF for .NET がインストールされ、開発環境が設定されていることを確認してください。

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
taggedContent.SetTitle("Example of table cell formatting");
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
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

新しい配列構造要素を作成し、それをルート構造要素に追加しました。また、テーブルのヘッダー、本文、フッター要素も作成しました。

## ステップ5: 表のヘッダーを追加する

このステップでは、テーブルにテーブル ヘッダーを追加します。

```csharp
//表の行数と列数
int rowCount = 4;
int colCount = 4;

int rowIndex;
int colIndex;

//表のヘッダー行を作成する
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
     theElement.BackgroundColor = Color.GreenYellow;
     theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
     theElement. IsNoBorder = true;
     theElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     theElement.Alignment = HorizontalAlignment.Right;
}
```

テーブルにヘッダー行を作成し、背景色、境界線、余白、配置などの書式設定プロパティを持つヘッダー セルを追加しました。

## ステップ6: テーブル本体の行を追加する

次に、テーブル本体の行をテーブルに追加します。
```csharp
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         int colSpan = 1;
         int rowSpan = 1;

         if (colIndex == 1 && rowIndex == 1)
         {
             colSpan = 2;
             rowSpan = 2;
         }
         else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
         {
             keep on going;
         }
         else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
         {
             keep on going;
         }

         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
         tdElement.BackgroundColor = Color.Yellow;
         tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
         tdElement.IsNoBorder = false;
         tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
         tdElement.Alignment = HorizontalAlignment.Center;

         TextState cellTextState = new TextState();
         cellTextState.ForegroundColor = Color.DarkBlue;
         cellTextState.FontSize = 7.5F;
         cellTextState.FontStyle = FontStyles.Bold;
         cellTextState.Font = FontRepository.FindFont("Arial");

         tdElement. DefaultCellTextState = cellTextState;
         tdElement.IsWordWrapped = true;
         tdElement.VerticalAlignment = VerticalAlignment.Center;
         tdElement.ColSpan = colSpan;
         tdElement. RowSpan = rowSpan;
     }
}
```

ループを使用して各テーブル セルを反復処理し、テーブルの本体に行を追加しました。背景色、境界線、余白、テキストの配置など、各セルの書式設定プロパティを設定しました。

## ステップ7: フッターを追加する

最後に、テーブルにテーブルフッターを追加します。

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

テーブルのフッターを作成し、テキストを含むフッター セルを追加しました。



## ステップ8: タグ付きPDF文書を保存する

スタイル設定されたテーブルを含むドキュメントを作成したので、タグ付き PDF ドキュメントとして保存します。

```csharp
//タグ付けされたPDF文書を保存する
document.Save(dataDir + "StyleTableCell.pdf");
```

タグ付けされた PDF ドキュメントを指定されたディレクトリに保存しました。

## ステップ9: PDF/UAコンプライアンス検証

次に、ドキュメントの PDF/UA 準拠を検証します。

```csharp
//PDF/UA 準拠チェック
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

タグ付き PDF ドキュメントをアップロードし、XML レポートを生成して PDF/UA 準拠を検証しました。

### Aspose.PDF for .NET を使用したテーブル セルのスタイル設定のサンプル ソース コード 
```csharp

//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//ドキュメントを作成
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");

//ルート構造要素を取得する
StructureElement rootElement = taggedContent.RootElement;

//テーブル構造要素を作成する
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 4;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
	thElement.BackgroundColor = Color.GreenYellow;
	thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
	thElement.IsNoBorder = true;
	thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	thElement.Alignment = HorizontalAlignment.Right;
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		int colSpan = 1;
		int rowSpan = 1;
		if (colIndex == 1 && rowIndex == 1)
		{
			colSpan = 2;
			rowSpan = 2;
		}
		else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
		{
			continue;
		}
		else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
		{
			continue;
		}
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
		tdElement.BackgroundColor = Color.Yellow;
		tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
		tdElement.IsNoBorder = false;
		tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
		tdElement.Alignment = HorizontalAlignment.Center;
		TextState cellTextState = new TextState();
		cellTextState.ForegroundColor = Color.DarkBlue;
		cellTextState.FontSize = 7.5F;
		cellTextState.FontStyle = FontStyles.Bold;
		cellTextState.Font = FontRepository.FindFont("Arial");
		tdElement.DefaultCellTextState = cellTextState;
		tdElement.IsWordWrapped = true;
		tdElement.VerticalAlignment = VerticalAlignment.Center;
		tdElement.ColSpan = colSpan;
		tdElement.RowSpan = rowSpan;
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
document.Save(dataDir + "StyleTableCell.pdf");

//PDF/UA準拠の確認
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用してテーブル セルにスタイルを設定する方法を学習しました。ドキュメントを作成し、ヘッダー、本文行、フッターを含むテーブルを追加し、セル スタイルをカスタマイズする方法を確認しました。最後に、タグ付き PDF ドキュメントを保存し、PDF/UA 準拠を検証しました。これで、Aspose.PDF for .NET を使用して、.NET アプリケーションでテーブルを作成し、スタイルを設定できます。

### よくある質問

#### Q: Aspose.PDF for .NET を使用してテーブル セルをフォーマットするこのチュートリアルの目的は何ですか?

A: このチュートリアルの目的は、.NET 用の Aspose.PDF ライブラリを使用して PDF ドキュメント内のテーブル セルにスタイルを設定する方法についての包括的なガイドを提供することです。テーブル セルの書式設定を理解して実装するのに役立つ、ステップバイステップの手順と C# ソース コードの例について説明します。

#### Q: このチュートリアルに従うための前提条件は何ですか?

A: 始める前に、Aspose.PDF for .NET がインストールされ、開発環境が設定されていることを確認してください。これには、Aspose.PDF ライブラリを参照するようにプロジェクトを構成することも含まれます。

#### Q: Aspose.PDF for .NET を使用して新しい PDF ドキュメントを作成するにはどうすればよいですか?

A: 新しいPDF文書を作成するには、`Document` Aspose.PDF ライブラリからのオブジェクト。提供されている C# ソース コードは、ドキュメントを作成し、そのタイトルと言語を設定する方法を示しています。

#### Q: PDF ドキュメントのルート構造要素の重要性は何ですか?

A: ルート構造要素は、他の構造要素のコンテナとして機能し、PDF ドキュメントのコンテンツを整理および分類するのに役立ちます。ドキュメントの論理構造を確立する上で重要な役割を果たします。

#### Q: Aspose.PDF for .NET を使用してテーブル構造要素を作成し、その外観をカスタマイズするにはどうすればよいですか?

 A: テーブル構造要素を作成するには、`CreateTableElement()`メソッド。提供されているソース コードは、背景色、境界線、余白、配置などのプロパティを設定して、ヘッダー、本文、フッターを含むテーブルの外観をカスタマイズする方法を示しています。

#### Q: 表本体に複数の行と列を追加し、その書式をカスタマイズできますか?

A: はい、このチュートリアルでは、ループを使用してテーブル本体に複数の行と列を追加する方法を説明します。また、背景色、境界線、テキストの配置、フォント スタイルなど、セルの書式設定をカスタマイズする例も示します。

#### Q: PDF/UA 準拠を検証する目的は何ですか? また、この検証はどのように実行できますか?

 A: PDF/UA準拠を検証することで、PDF文書がアクセシビリティ標準に準拠していることが保証され、障害を持つユーザーにとってよりアクセスしやすくなります。このチュートリアルでは、`Validate()`メソッドを実行して XML レポートを生成します。

#### Q: これらの概念を自分の .NET アプリケーションに適用するにはどうすればよいでしょうか?

A: 提供されている C# ソース コードの例をガイドとして使用して、独自の .NET アプリケーションでテーブル セルの書式設定を実装できます。必要に応じてコードをカスタマイズし、要件に合わせてプロジェクトに統合します。

#### Q: PDF ドキュメント内の表セルのスタイル設定に関して推奨されるベスト プラクティスはありますか?

A: 表のセルをスタイル設定するときは、アクセシビリティ要件など、対象者のニーズを考慮してください。読みやすさを高めるために、対照的な色、適切なフォント、明確なセル配置を使用してください。さらに、アクセシビリティ標準が満たされていることを確認するために、PDF/UA 準拠を検証してください。

#### Q: PDF ドキュメントの操作に使用できる Aspose.PDF for .NET のその他の機能は何ですか?

A: Aspose.PDF for .NET は、テキスト抽出、画像挿入、フォーム フィールド管理、デジタル署名など、PDF ドキュメントを操作するための幅広い機能を提供します。追加機能の詳細については、公式ドキュメントとリソースを参照してください。
