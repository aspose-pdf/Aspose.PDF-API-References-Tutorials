---
title: テーブル要素を作成する
linktitle: テーブル要素を作成する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して配列要素を作成する手順ガイド。テーブルを含む動的な PDF を簡単に生成します。
type: docs
weight: 80
url: /ja/net/programming-with-tagged-pdf/create-table-element/
---
このステップバイステップ ガイドでは、Aspose.PDF for .NET を使用して配列要素を作成する手順を説明します。Aspose.PDF は、PDF ドキュメントをプログラムで操作できる強力なライブラリです。配列要素の作成は、動的な PDF を生成するときによく必要となる要件であり、Aspose.PDF は、これを簡単かつ効率的に実現する方法を提供します。

コードを調べて、Aspose.PDF for .NET を使用して配列要素を作成する方法を学びましょう。

## 前提条件

始める前に、次のものがあることを確認してください。

1. .NET 用の Aspose.PDF ライブラリがインストールされています。
2. C# プログラミング言語に関する基本的な知識。

## ステップ1: 環境の設定

まず、C# 開発環境を開いて新しいプロジェクトを作成します。プロジェクトに .NET 用の Aspose.PDF ライブラリへの参照を追加したことを確認します。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: ドキュメントの作成

最初のステップは、`Document`クラス。

```csharp
//ドキュメントを作成する
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Array");
taggedContent.SetLanguage("fr-FR");
```

ここでは、タグ付けされたコンテンツのタイトルと言語も設定します。

## ステップ3: 配列要素の作成

次に、配列要素を作成し、それをドキュメントに追加する必要があります。まずルート構造要素を取得し、次に新しいテーブル要素を作成します。`CreateTableElement`方法。

```csharp
//ルート構造要素を取得する
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";
headTrElement.BackgroundColor = Color.LightGray;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTHElement theElement = headTrElement.CreateTH();
thElement.SetText(String.Format("Header {0}", colIndex));
theElement.BackgroundColor = Color.GreenYellow;
theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
theElement. IsNoBorder = true;
theElement.Margin = new MarginInfo(16.0, 2

.0, 8.0, 2.0);
theElement.Alignment = HorizontalAlignment.Right;
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
keep on going;
}
else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
{
keep on going;
}
TableTDElement tdelement = trElement.CreateTD();
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
tdElement. DefaultCellTextState = cellTextState;
tdElement.IsWordWrapped = true;
tdElement.VerticalAlignment = VerticalAlignment.Center;
tdElement.ColSpan = colSpan;
tdElement. RowSpan = rowSpan;
}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTDElement tdElement = footTrElement.CreateTD();
tdElement.SetText(String.Format("Foot {0}", colIndex));
tdElement.Alignment = HorizontalAlignment.Center;
tdElement.StructureTextState.FontSize = 7F;
tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for the table");
tableAttributes.SetAttribute(summaryAttribute);

//タグ付けされたPDF文書を保存する
document.Save(dataDir + "CreateTableElement.pdf");

//PDF/UA 準拠チェック
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

### Aspose.PDF for .NET を使用してテーブル要素を作成するためのサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//ドキュメントを作成
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table");
taggedContent.SetLanguage("en-US");

//ルート構造要素を取得する
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
headTrElement.BackgroundColor = Color.LightGray;
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
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
	tdElement.Alignment = HorizontalAlignment.Center;
	tdElement.StructureTextState.FontSize = 7F;
	tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for table");
tableAttributes.SetAttribute(summaryAttribute);

//タグ付き PDF ドキュメントを保存
document.Save(dataDir + "CreateTableElement.pdf");

//PDF/UA準拠の確認
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## 結論

Aspose.PDF for .NET を使用して配列要素を作成する方法を学習しました。この方法を使用して、動的なテーブルを含む PDF ドキュメントを生成できるようになりました。Aspose.PDF のその他の機能を自由に探索して、その可能性を最大限に引き出してください。

### よくある質問

#### Q: PDF ドキュメントの配列要素とは何ですか? また、Aspose.PDF for .NET を使用して配列要素を作成する必要があるのはなぜですか?

A: PDF ドキュメント内の配列要素は構造化されたデータのコレクションを表し、テーブルやグリッドの作成によく使用されます。表形式の情報やグリッドなどの構造化されたデータの表示を必要とする動的な PDF を生成する場合は、Aspose.PDF for .NET を使用して配列要素を作成する必要があります。

#### Q: Aspose.PDF for .NET では配列要素の作成プロセスがどのように簡素化されますか?

A: Aspose.PDF for .NET は、PDF ドキュメント内の配列要素 (テーブル) をプログラムで作成、カスタマイズ、管理できる包括的なクラスとメソッドのセットを提供します。これにより、手動での PDF 操作が不要になり、構造化データ表現の作成が効率化されます。

#### Q: Aspose.PDF for .NET を使用して配列要素を作成する際の主な手順は何ですか?

A: 主な手順としては、環境の設定、ドキュメントの作成、ルート構造要素の取得、テーブル要素の作成、テーブル内の行とセルの定義、要素の書式設定とプロパティの指定などがあります。提供されているコード例は、これらの手順を示しています。

####  Q:`taggedContent` object play in creating an array element?

 A:`taggedContent`オブジェクトは、ドキュメントの`TaggedContent`プロパティを使用すると、PDF ドキュメント内のタグ付けされたコンテンツの構造を定義できます。これには、配列要素とその子要素を階層的に作成および整理することが含まれます。

#### Q: コードは、作成された配列要素のアクセシビリティとセマンティクスをどのように保証しますか?

 A: コードは次のような属性を設定します。`AlternativeText`, `BackgroundColor`, `Border`, `Margin`, `Alignment` 、 そして`ColSpan`配列要素のアクセシビリティとセマンティクスを強化します。これらの属性は、適切に構造化され、情報に富み、視覚的に魅力的なデータの表現に貢献します。

#### Q: 配列要素を作成する場合の PDF/UA 準拠の重要性は何ですか?

 A: PDF/UA (ユニバーサルアクセシビリティ) 準拠は、生成されたPDF文書が障害を持つユーザーにアクセス可能であり、特定のアクセシビリティ標準を満たしていることを保証します。コード例では、`Validate`メソッドは、包括的かつアクセスしやすいドキュメントの作成に役立ちます。

#### Q: 配列要素の書式と外観をさらにカスタマイズできますか?

A: はい、背景色、境界線のスタイル、フォント サイズ、配置などの属性を調整することで、配列要素の書式設定と外観をカスタマイズできます。Aspose.PDF for .NET には、視覚的なプレゼンテーションを要件に合わせてカスタマイズするためのさまざまなプロパティが用意されています。

#### Q: この知識を拡張して、より複雑な表構造を作成したり、配列要素を大きな PDF ドキュメントに組み込んだりするにはどうすればよいでしょうか?

A: 複数の配列要素の結合、ネストされたテーブルの作成、ヘッダーとフッターの追加、配列要素のより大きな PDF レイアウトへの統合など、Aspose.PDF for .NET の追加機能を調べることで、この知識を拡張できます。ライブラリのドキュメントと例は、これらの高度なシナリオのガイダンスを提供します。

#### Q: データベースやスプレッドシートなどの外部ソースからデータをインポートして配列要素に入力することは可能ですか?

A: はい、外部ソースからデータをインポートして配列要素を設定できます。C# のデータ取得および変換技術を使用して、データベース、スプレッドシート、またはその他のソースからデータを取得し、それに応じて配列要素を設定できます。

#### Q: このチュートリアルで得た知識を活用して、プログラムで作成する PDF ドキュメントの品質と使いやすさを向上させるにはどうすればよいですか?

A: このチュートリアルで得た知識により、PDF ドキュメント内に構造化された視覚的に魅力的な配列要素 (テーブル) を作成できます。これらのテクニックを組み込むことで、動的に生成された PDF の読みやすさ、アクセシビリティ、ユーザー エクスペリエンスが向上し、より情報量が多くユーザー フレンドリな PDF になります。