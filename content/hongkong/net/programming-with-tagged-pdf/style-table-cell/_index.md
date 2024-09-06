---
title: 樣式表單元格
linktitle: 樣式表單元格
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 設定表格儲存格的樣式。建立和自訂表格的逐步指南。
type: docs
weight: 160
url: /zh-hant/net/programming-with-tagged-pdf/style-table-cell/
---
歡迎閱讀使用 Aspose.PDF for .NET 設定表格儲存格格式的詳細教學。在本指南中，我們將詳細解釋所提供的 C# 原始程式碼的每個步驟，以幫助您了解如何設定表格單元格的樣式。在開始之前，請確保您已安裝 Aspose.PDF for .NET 並設定您的開發環境。

## 第一步：建構環境

在開始之前，請確保您已將開發環境配置為使用 Aspose.PDF for .NET。這包括安裝 Aspose.PDF 庫並配置您的專案以引用它。

## 第 2 步：建立文檔

在這一步驟中，我們將建立一個新的文檔物件Aspose.PDF。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//文件創建
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of table cell formatting");
taggedContent.SetLanguage("fr-FR");
```

我們建立了一個新文件並設定了文件標題和語言。

## 第三步：取得根結構元素

在此步驟中，我們將取得文件的根結構元素。

```csharp
//取得根結構元素
StructureElement rootElement = taggedContent.RootElement;
```

我們得到了根結構元素，它將用作數組元素的容器。

## 第四步：建立數組結構元素

現在讓我們為文件建立一個新的表結構元素。

```csharp
//建立數組結構元素
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

我們創建了一個新的陣列結構元素並將其添加到根結構元素中。我們也創建了表頭、正文和頁尾元素。

## 第 5 步：新增表頭

在此步驟中，我們將表頭新增到表中。

```csharp
//表中的行數和列數
int rowCount = 4;
int colCount = 4;

int rowIndex;
int colIndex;

//建立表格標題行
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

我們為表格建立了一個標題行，並新增了具有格式屬性（例如背景顏色、邊框、邊距和對齊方式）的標題儲存格。

## 步驟 6：新增表格主體行

現在讓我們將表格主體行加入到表中。
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

我們使用循環迭代每個表格單元格將行新增至表格主體。我們為每個單元格設定格式屬性，例如背景顏色、邊框、邊距、文字對齊方式等。

## 第7步：新增頁腳

最後，我們將表頁腳加入表格中。

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

我們為表格建立了頁腳，並新增了帶有文字的頁腳儲存格。



## 步驟 8：儲存標記的 PDF 文檔

現在我們已經使用樣式表建立了文檔，我們將其另存為帶有標籤的 PDF 文件。

```csharp
//儲存標記的 PDF 文檔
document.Save(dataDir + "StyleTableCell.pdf");
```

我們將標記的PDF文件保存在指定的目錄中。

## 第 9 步：PDF/UA 合規驗證

接下來，我們將驗證文件的 PDF/UA 一致性。

```csharp
//PDF/UA 合規性檢查
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

我們上傳了帶有標籤的 PDF 文檔，並透過產生 XML 報告來驗證其 PDF/UA 合規性。

### 使用 Aspose.PDF for .NET 的樣式表單元格範例原始程式碼 
```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//建立文檔
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");

//取得根結構元素
StructureElement rootElement = taggedContent.RootElement;

//建立表格結構元素
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

//儲存標記的 PDF 文檔
document.Save(dataDir + "StyleTableCell.pdf");

//檢查 PDF/UA 合規性
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## 結論

在本教學中，我們學習如何使用 Aspose.PDF for .NET 設定表格儲存格的樣式。我們已經了解如何建立文件、新增包含標題、正文行和頁腳的表格以及自訂儲存格樣式。最後，我們保存了帶有標籤的 PDF 文件並驗證了其 PDF/UA 合規性。現在您可以使用 Aspose.PDF for .NET 在 .NET 應用程式中建立表格並設定表格樣式。

### 常見問題解答

#### Q：本教學關於使用 Aspose.PDF for .NET 格式化表格單元格的目的是什麼？

答：本教學課程旨在提供如何使用 .NET 的 Aspose.PDF 庫設定 PDF 文件中的表格單元格樣式的全面指南。它涵蓋逐步說明和 C# 原始程式碼範例，可幫助您理解和實現表格單元格格式設定。

#### Q：學習本教程的先決條件是什麼？

答：開始之前，請確保您已經安裝了 Aspose.PDF for .NET 並設定了開發環境。這包括配置您的項目以引用 Aspose.PDF 庫。

#### Q：如何使用 Aspose.PDF for .NET 建立新的 PDF 文件？

A：要建立一個新的PDF文檔，您需要實例化一個`Document`來自 Aspose.PDF 庫的物件。提供的 C# 原始程式碼示範如何建立文件並設定其標題和語言。

#### Q：PDF 文件中的根結構元素有何意義？

答：根結構元素充當其他結構元素的容器，幫助組織和分類 PDF 文件的內容。它在建立文件的邏輯結構方面起著至關重要的作用。

#### Q：如何使用 Aspose.PDF for .NET 建立表格結構元素並自訂其外觀？

答：您可以使用以下命令建立表格結構元素`CreateTableElement()`方法。提供的原始程式碼示範如何透過設定背景顏色、邊框、邊距和對齊等屬性來自訂表格的外觀，包括其頁首、正文和頁尾。

#### Q：我可以在表體中新增多行和多列並自訂其格式嗎？

答：是的，教學課程示範如何使用循環為表體新增多行和多列。它還提供了自訂單元格格式的範例，例如背景顏色、邊框、文字對齊方式、字體樣式等。

#### Q：驗證 PDF/UA 合規性的目的是什麼？

答：驗證 PDF/UA 合規性可確保 PDF 文件符合輔助功能標準，從而更方便殘障使用者使用。本教學課程展示如何使用以下方法驗證 PDF/UA 一致性`Validate()`方法並產生 XML 報告。

#### Q：如何將這些概念應用到我自己的 .NET 應用程式中？

答：您可以使用提供的 C# 原始程式碼範例作為在您自己的 .NET 應用程式中實作表格單元格格式的指南。根據需要自訂程式碼以滿足您的要求並將其整合到您的專案中。

#### Q：對於 PDF 文件中的表格單元格樣式，是否有任何建議的最佳實踐？

答：在設計表格單元格樣式時，請考慮受眾的需求，包括可訪問性要求。使用對比色、適當的字體和清晰的單元格對齊來增強可讀性。此外，驗證 PDF/UA 合規性以確保滿足輔助功能標準。

#### Q：我可以探索 Aspose.PDF for .NET 的哪些其他功能來進行 PDF 文件操作？

答：Aspose.PDF for .NET 提供了廣泛的 PDF 文件操作功能，包括文字擷取、影像插入、表單欄位管理、數位簽章等等。瀏覽官方文件和資源以了解其他功能。
