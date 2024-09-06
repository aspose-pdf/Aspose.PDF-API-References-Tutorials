---
title: 建立表元素
linktitle: 建立表元素
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 建立陣列元素的逐步指南。輕鬆產生帶有表格的動態 PDF。
type: docs
weight: 80
url: /zh-hant/net/programming-with-tagged-pdf/create-table-element/
---
在本逐步指南中，我們將引導您完成使用 Aspose.PDF for .NET 建立陣列元素的過程。 Aspose.PDF 是一個功能強大的程式庫，可讓您以程式設計方式操作 PDF 文件。建立陣列元素是產生動態 PDF 時的常見要求，Aspose.PDF 提供了一個簡單有效的方法來完成此任務。

讓我們深入研究程式碼並了解如何使用 Aspose.PDF for .NET 建立陣列元素。

## 先決條件

在開始之前，請確保您具備以下條件：

1. 安裝了適用於.NET 的 Aspose.PDF 庫。
2. C# 程式語言的基礎知識。

## 第一步：建構環境

首先，開啟 C# 開發環境並建立一個新專案。請確定您已在專案中新增對 .NET 的 Aspose.PDF 庫的參考。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：建立文檔

第一步是使用以下命令建立新的 PDF 文檔`Document`班級。

```csharp
//建立文檔
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Array");
taggedContent.SetLanguage("fr-FR");
```

在這裡我們也設定標記內容的標題和語言。

## 步驟 3：建立陣列元素

接下來，我們需要建立數組元素並將其新增到文件中。我們首先取得根結構元素，然後使用以下命令建立新的表元素`CreateTableElement`方法。

```csharp
//取得根結構元素
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

//儲存標記的 PDF 文檔
document.Save(dataDir + "CreateTableElement.pdf");

//PDF/UA 合規性檢查
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

### 使用 Aspose.PDF for .NET 建立表格元素的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//建立文檔
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table");
taggedContent.SetLanguage("en-US");

//取得根結構元素
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

//儲存標記的 PDF 文檔
document.Save(dataDir + "CreateTableElement.pdf");

//檢查 PDF/UA 合規性
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## 結論

您已經學習如何使用 Aspose.PDF for .NET 建立陣列元素。現在您可以使用此方法產生具有動態表格的 PDF 文件。請隨意探索 Aspose.PDF 的更多功能，以發現其全部潛力。

### 常見問題解答

#### Q：什麼是 PDF 文件中的陣列元素？

答：PDF 文件中的陣列元素表示結構化資料集合，通常用於建立表格或網格。在產生需要結構化資料呈現（例如表格資訊或網格）的動態 PDF 時，您可能需要使用 Aspose.PDF for .NET 建立陣列元素。

#### Q：Aspose.PDF for .NET 如何簡化建立陣列元素的過程？

答：Aspose.PDF for .NET 提供了一套全面的類別和方法，可讓您以程式設計方式建立、自訂和管理 PDF 文件中的陣列元素（表）。這消除了手動 PDF 操作的需要，並簡化了結構化資料表示的建立。

#### Q：使用 Aspose.PDF for .NET 建立陣列元素涉及哪些關鍵步驟？

答：關鍵步驟包括設定環境、建立文件、取得根結構元素、建立表格元素、定義表格內的行和儲存格以及指定元素的格式和屬性。提供的程式碼範例演示了這些步驟。

####  Q： 有何作用`taggedContent` object play in creating an array element?

答： 的`taggedContent`對象，從文件中取得`TaggedContent`屬性，可讓您定義 PDF 文件中標記內容的結構。這包括以分層方式建立和組織數組元素及其子元素。

#### Q：程式碼如何確保創建的陣列元素的可訪問性和語義？

 A：代碼設定屬性，例如`AlternativeText`, `BackgroundColor`, `Border`, `Margin`, `Alignment`， 和`ColSpan`增強數組元素的可訪問性和語義。這些屬性有助於形成結構良好、資訊豐富且具有視覺吸引力的資料表示。

#### Q：在建立陣列元素時，PDF/UA 合規性有何意義？

答：PDF/UA（一般輔助功能）合規性可確保產生的 PDF 文件可供殘障使用者存取，並符合某些輔助功能標準。此程式碼範例使用以下命令檢查 PDF/UA 合規性`Validate`方法，幫助您建立包容且易於存取的文件。

#### Q：我可以進一步自訂陣列元素的格式和外觀嗎？

答：是的，您可以透過調整背景顏色、邊框樣式、字體大小和對齊方式等屬性來自訂陣列元素的格式和外觀。 Aspose.PDF for .NET 提供了廣泛的屬性來根據您的要求自訂視覺呈現。

#### Q：如何擴展這些知識來創建更複雜的表格結構或將陣列元素合併到更大的 PDF 文件中？

答：您可以透過探索Aspose.PDF for .NET 的其他功能來擴展這些知識，例如合併多個陣列元素、建立巢狀表格、新增頁首和頁尾以及將陣列元素整合到更大的PDF 佈局中。該庫的文檔和範例為這些高級場景提供了指導。

#### Q：是否可以從外部來源（例如資料庫或電子表格）匯入資料來填入陣列元素？

答：是的，您可以從外部來源匯入資料來填入陣列元素。您可以使用 C# 中的數據檢索和轉換技術從資料庫、電子表格或其他來源獲取數據，然後相應地填充數組元素。

#### Q：如何利用從本教程中獲得的知識來提高以程式設計方式建立的 PDF 文件的品質和可用性？

答：從本教程中獲得的知識使您能夠在 PDF 文件中創建結構化且具有視覺吸引力的數組元素（表格）。透過結合這些技術，您可以提高動態產生的 PDF 的可讀性、可存取性和使用者體驗，使其資訊更豐富且使用者友好。