---
title: スタイルテーブルセル
linktitle: スタイルテーブルセル
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用してテーブルのセルをスタイル設定する方法を学びます。テーブルの作成とカスタマイズに関するステップバイステップのガイド。
type: docs
weight: 160
url: /ja/net/programming-with-tagged-pdf/style-table-cell/
---
Aspose.PDF for .NET を使用したテーブル セルの書式設定に関するこの詳細なチュートリアルへようこそ。このガイドでは、テーブルのセルのスタイルを設定する方法を理解できるように、提供されている C# ソース コードの各ステップを詳細に説明します。始める前に、Aspose.PDF for .NET がインストールされ、開発環境がセットアップされていることを確認してください。

## ステップ 1: 環境をセットアップする

始める前に、Aspose.PDF for .NET を使用するように開発環境が構成されていることを確認してください。これには、Aspose.PDF ライブラリのインストールと、それを参照するようにプロジェクトを構成することが含まれます。

## ステップ 2: ドキュメントの作成

このステップでは、新しいドキュメント オブジェクト Aspose.PDF を作成します。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//書類作成
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of table cell formatting");
taggedContent.SetLanguage("fr-FR");
```

新しいドキュメントを作成し、ドキュメントのタイトルと言語を設定しました。

## ステップ 3: ルート構造要素の取得

このステップでは、ドキュメントのルート構造要素を取得します。

```csharp
//ルート構造要素の取得
StructureElement rootElement = taggedContent.RootElement;
```

配列要素のコンテナとして機能するルート構造要素を取得しました。

## ステップ 4: 配列構造要素の作成

次に、ドキュメント用に新しいテーブル構造要素を作成しましょう。

```csharp
//配列構造要素を作成する
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

新しい配列構造要素を作成し、ルート構造要素に追加しました。テーブルのヘッダー、本文、フッター要素も作成しました。

## ステップ 5: テーブルヘッダーの追加

このステップでは、テーブルヘッダーをテーブルに追加します。

```csharp
//テーブル内の行と列の数
int rowCount = 4;
int colCount = 4;

int rowIndex;
int colIndex;

//テーブルのヘッダー行を作成する
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

テーブルのヘッダー行を作成し、背景色、枠線、余白、配置などの書式設定プロパティを備えたヘッダー セルを追加しました。

## ステップ 6: テーブル本体の行を追加する

次に、テーブル本体の行をテーブルに追加しましょう。
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

ループを使用してテーブルの本体に行を追加し、テーブルの各セルを反復処理しました。背景色、枠線、余白、テキストの配置など、各セルの書式設定プロパティを設定します。

## ステップ 7: フッターを追加する

最後に、表のフッターを表に追加します。

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



## ステップ 8: タグ付けされた PDF ドキュメントを保存する

スタイル付きの表を含むドキュメントを作成したので、それをタグ付き PDF ドキュメントとして保存します。

```csharp
//タグ付けされた PDF ドキュメントを保存する
document.Save(dataDir + "StyleTableCell.pdf");
```

タグ付けされた PDF ドキュメントを指定されたディレクトリに保存しました。

## ステップ 9: PDF/UA 準拠の検証

次に、ドキュメントの PDF/UA 準拠を検証します。

```csharp
//PDF/UA 準拠チェック
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

タグ付けされた PDF ドキュメントをアップロードし、XML レポートを生成してその PDF/UA 準拠を検証しました。

### Aspose.PDF for .NET を使用したスタイル テーブル セルのサンプル ソース コード 
```csharp

//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//文書の作成
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");

//ルート構造要素の取得
StructureElement rootElement = taggedContent.RootElement;

//テーブル構造要素の作成
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

//PDF/UA 準拠の確認
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用してテーブルのセルをスタイル設定する方法を学びました。ドキュメントを作成し、ヘッダー、本文行、フッターを含む表を追加し、セル スタイルをカスタマイズする方法を説明しました。最後に、タグ付けされた PDF ドキュメントを保存し、その PDF/UA 準拠を検証しました。 Aspose.PDF for .NET を使用して、.NET アプリケーションでテーブルを作成およびスタイル設定できるようになりました。

### よくある質問

#### Q: Aspose.PDF for .NET を使用したテーブル セルの書式設定に関するこのチュートリアルの目的は何ですか?

A: このチュートリアルは、.NET 用の Aspose.PDF ライブラリを使用して PDF ドキュメント内の表のセルをスタイルする方法に関する包括的なガイドを提供することを目的としています。表のセルの書式設定を理解して実装するのに役立つ、段階的な手順と C# ソース コードの例について説明します。

#### Q: このチュートリアルを実行するための前提条件は何ですか?

A: 始める前に、Aspose.PDF for .NET がインストールされ、開発環境がセットアップされていることを確認してください。これには、Aspose.PDF ライブラリを参照するようにプロジェクトを構成することが含まれます。

#### Q: Aspose.PDF for .NET を使用して新しい PDF ドキュメントを作成するにはどうすればよいですか?

A: 新しい PDF ドキュメントを作成するには、`Document` Aspose.PDF ライブラリのオブジェクト。提供されている C# ソース コードは、ドキュメントを作成し、そのタイトルと言語を設定する方法を示しています。

#### Q: PDF ドキュメント内のルート構造要素の重要性は何ですか?

A: ルート構造要素は他の構造要素のコンテナとして機能し、PDF ドキュメントのコンテンツの整理と分類に役立ちます。文書の論理構造を確立する上で重要な役割を果たします。

#### Q: Aspose.PDF for .NET を使用してテーブル構造要素を作成し、その外観をカスタマイズするにはどうすればよいですか?

 A: テーブル構造要素は、`CreateTableElement()`方法。提供されているソース コードは、背景色、境界線、余白、配置などのプロパティを設定して、ヘッダー、本文、フッターを含むテーブルの外観をカスタマイズする方法を示しています。

#### Q: テーブル本体に複数の行と列を追加して、その書式設定をカスタマイズできますか?

A: はい、チュートリアルでは、ループを使用してテーブル本体に複数の行と列を追加する方法を示します。また、背景色、枠線、テキストの配置、フォント スタイルなどのセルの書式設定をカスタマイズする例も示します。

#### Q: PDF/UA 準拠を検証する目的は何ですか?また、この検証はどのように実行すればよいですか?

 A: PDF/UA コンプライアンスを検証すると、PDF ドキュメントがアクセシビリティ標準に準拠していることが保証され、障害を持つユーザーがよりアクセスしやすくなります。このチュートリアルでは、`Validate()`メソッドを作成し、XML レポートを生成します。

#### Q: これらの概念を自分の .NET アプリケーションに適用するにはどうすればよいですか?

A: 提供されている C# ソース コードの例は、独自の .NET アプリケーションでテーブルのセルの書式設定を実装するためのガイドとして使用できます。要件に合わせて必要に応じてコードをカスタマイズし、プロジェクトに統合します。

#### Q: PDF ドキュメント内の表のセルのスタイルを設定するための推奨されるベスト プラクティスはありますか?

A: 表のセルのスタイルを設定するときは、アクセシビリティ要件など、視聴者のニーズを考慮してください。可読性を高めるために、対照的な色、適切なフォント、明確なセルの配置を使用します。さらに、PDF/UA への準拠を検証して、アクセシビリティ基準が満たされていることを確認します。

#### Q: PDF ドキュメントを操作するために Aspose.PDF for .NET の他の機能を探索できますか?

A: Aspose.PDF for .NET は、テキスト抽出、画像挿入、フォーム フィールド管理、デジタル署名などを含む、PDF ドキュメント操作のための幅広い機能を提供します。追加の機能については、公式ドキュメントとリソースを参照してください。
