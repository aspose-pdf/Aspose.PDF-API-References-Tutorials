---
title: 樣式表行
linktitle: 樣式表行
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 自訂表格行樣式和格式設定的逐步指南。
type: docs
weight: 180
url: /zh-hant/net/programming-with-tagged-pdf/style-table-row/
---
在這個詳細的教學中，我們將引導您逐步完成所提供的 C# 原始程式碼，以使用 Aspose.PDF for .NET 格式化表格行。請依照以下說明了解如何自訂表格行樣式和屬性。

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
taggedContent.SetTitle("Example of Table Row Formatting");
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
```

我們創建了一個新的陣列結構元素並將其添加到根結構元素中。

## 步驟 5：自訂表格行樣式和屬性

在此步驟中，我們將自訂表格行樣式和屬性。

```csharp
//自訂表格行樣式和屬性
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

int rowCount = 7;
int colCount = 3;
int rowIndex;
int colIndex;

//建立表格標題行
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
}

//自訂表格主體的行
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);
     trElement.BackgroundColor = Color.LightGoldenrodYellow;
     trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
     trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
     trElement.MinRowHeight = 100.0;
     trElement.FixedRowHeight = 120.0;
     trElement. IsInNewPage = (rowIndex % 3 == 1);
     trElement.IsRowBroken = true;
     TextState cellTextState = new TextState();
     cellTextState.ForegroundColor = Color.Red;
     trElement. DefaultCellTextState = cellTextState;
     trElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     trElement.VerticalAlignment = VerticalAlignment.Bottom;

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

//建立表格的頁尾行
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

我們自訂了表格行的各個方面，例如背景顏色、邊框、行高、分頁、預設儲存格樣式等。

## 步驟 6：儲存標記的 PDF 文檔

現在我們已經使用樣式表行建立了文檔，我們將其另存為帶有標籤的 PDF 文件。
```csharp
//儲存標記的 PDF 文檔
document.Save(dataDir + "StyleTableRow.pdf");
```

我們將標記的PDF文件保存在指定的目錄中。

## 第 7 步：PDF/UA 合規驗證

接下來，我們將驗證文件的 PDF/UA 一致性。

```csharp
//PDF/UA 合規性檢查
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

我們上傳了帶有標籤的 PDF 文檔，並透過產生 XML 報告來驗證其 PDF/UA 合規性。


### 使用 Aspose.PDF for .NET 的樣式表行範例原始程式碼 
```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//建立文檔
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");

//取得根結構元素
StructureElement rootElement = taggedContent.RootElement;

//建立表格結構元素
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 7;
int colCount = 3;
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
	trElement.BackgroundColor = Color.LightGoldenrodYellow;
	trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
	trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
	trElement.MinRowHeight = 100.0;
	trElement.FixedRowHeight = 120.0;
	trElement.IsInNewPage = (rowIndex % 3 == 1);
	trElement.IsRowBroken = true;
	TextState cellTextState = new TextState();
	cellTextState.ForegroundColor = Color.Red;
	trElement.DefaultCellTextState = cellTextState;
	trElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	trElement.VerticalAlignment = VerticalAlignment.Bottom;
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

//儲存標記的 PDF 文檔
document.Save(dataDir + "StyleTableRow.pdf");

//檢查 PDF/UA 合規性
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## 結論

在本教學中，我們學習如何使用 Aspose.PDF for .NET 格式化表格行。我們自訂了表格行樣式和屬性，新增了頁首、正文行和頁腳，保存了標記的 PDF 文檔，並驗證了其 PDF/UA 合規性。

### 常見問題解答

#### Q：本教學使用 Aspose.PDF for .NET 格式化表格行的目的是什麼？

答：本教學的目的是引導您完成使用 Aspose.PDF for .NET 格式化 PDF 文件中的表格行的過程。它提供逐步說明和 C# 原始程式碼範例，幫助您自訂表格行樣式和屬性。

#### Q：學習本教程的先決條件是什麼？

答：開始之前，請確保您已設定開發環境以使用 Aspose.PDF for .NET。這涉及安裝 Aspose.PDF 庫並配置您的專案以引用它。

#### Q：如何使用 Aspose.PDF for .NET 建立新的 PDF 文件並設定其標題和語言？

答：要建立一個新的 PDF 文檔，您需要建立一個`Document`來自 Aspose.PDF 庫的物件。本教學提供的 C# 原始程式碼示範如何建立文件並設定其標題和語言屬性。

#### Q：PDF 文件中的根結構元素有何意義？

答：根結構元素充當其他結構元素的容器，有助於組織和分類 PDF 文件的內容。它在建立文件的邏輯結構方面起著至關重要的作用。

#### Q：如何使用 Aspose.PDF for .NET 建立和自訂表格結構元素以格式化表格行？

答：本教學介紹如何建立表格結構元素並自訂其屬性以格式化表格行。它涵蓋了背景顏色、邊框、行高、分頁、預設儲存格樣式等方面。

#### Q：我可以自訂表格行中各個儲存格的樣式和屬性嗎？

答：是的，您可以自訂表格行中各個儲存格的樣式和屬性。本教學課程示範如何設定格式化表格行中的表格儲存格的屬性，例如背景顏色、邊框、文字顏色、填滿等。

#### Q：如何為格式化的表格行新增標題、正文行和頁尾？

答：本教學提供了建立標題、正文行和頁腳並將其新增至表格結構元素的範例。可以使用教程中描述的屬性進一步自訂這些元素。

#### Q：什麼是 PDF/UA 合規性？

答：PDF/UA 合規性可確保 PDF 文件符合輔助功能標準，從而更方便殘障使用者使用。本教學示範如何使用以下方法驗證 PDF/UA 一致性`Validate()`方法並產生 XML 合規性報表。

#### Q：如何將這些概念融入我自己的 .NET 應用程式中？

答：您可以使用提供的 C# 原始程式碼範例作為在您自己的 .NET 應用程式中實現表格行格式設定的指南。修改和調整程式碼以滿足您的要求並將其整合到您的專案中。

#### Q：對於格式化 PDF 文件中的表格行，是否有任何建議的最佳實踐？

答：格式化表格行時，請考慮內容的可讀性和可存取性。確保顏色有足夠的對比度，使用清晰易讀的字體，並保持一致的佈局。驗證 PDF/UA 合規性以確保滿足輔助功能標準。

#### Q：我可以探索 Aspose.PDF for .NET 的哪些其他功能來自訂 PDF 文件？

答：Aspose.PDF for .NET 為 PDF 文件客製化提供了廣泛的功能，包括文字操作、影像插入、表單欄位管理、數位簽章、註解等。請查閱官方文件和資源以探索其他功能。