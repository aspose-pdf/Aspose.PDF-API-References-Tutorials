---
title: 樣式表單元格
linktitle: 樣式表單元格
second_title: Aspose.PDF for .NET API 參考
description: 透過這個詳細的教學課程，了解如何使用 Aspose.PDF for .NET 設定 PDF 中表格單元格的樣式。按照說明建立漂亮的 PDF 表格並設定其格式。
type: docs
weight: 160
url: /zh-hant/net/programming-with-tagged-pdf/style-table-cell/
---
## 介紹

建立具有專業外觀的 PDF 表格可能很棘手，但使用 Aspose.PDF for .NET，它出奇地簡單！無論您是設計頁首、頁尾或特定的表格單元格，這個強大的庫都為您提供了創建格式精美的 PDF 文件所需的所有工具。在本教學中，我們將介紹如何使用 Aspose.PDF for .NET 設定 PDF 文件中表格單元格的樣式。別擔心——我們會將一切分解為易於遵循的步驟。

## 先決條件

在深入研究程式碼之前，請確保您符合以下先決條件：

1. Aspose.PDF for .NET：從下列位置下載並安裝最新版本的 Aspose.PDF[這裡](https://releases.aspose.com/pdf/net/).
2. IDE（如 Visual Studio）：設定 .NET 開發環境。
3. C# 程式設計的基礎：需要對 C# 有一定的了解。
4.  Aspose.PDF 許可證：取得臨時或完整許可證以解鎖該庫的全部功能。您可以獲得免費試用[這裡](https://purchase.aspose.com/temporary-license/).

## 導入包

開始之前，請確保導入必要的命名空間。您的專案中需要以下內容：

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

現在一切都已設定完畢，讓我們進入逐步指南！

我們將在 PDF 文件中建立一個表格並設定其單元格的樣式。每個步驟都會詳細解釋該過程。

## 第 1 步：建立新的 PDF 文檔

第一步是建立一個新的 PDF 文件。在Aspose.PDF中，您可以初始化一個新的`Document`對象，代表您的 PDF 檔案。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//建立新的 PDF 文檔
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");
```

在這裡，我們初始化一個 PDF 文件並設定其標題和語言。這為您的文件提供了正確的結構，這對於 PDF/UA 合規性至關重要。

## 第 2 步：設定表結構

PDF 中的表格是在結構元素內定義的。讓我們建立表格並定義表格的行和列。

```csharp
//取得根結構元素
StructureElement rootElement = taggedContent.RootElement;

//建立表格結構元素
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

我們現在已經定義了表格的頭部（`TableTHeadElement`), 身體 (`TableTBodyElement`) 和腳 (`TableTFootElement`) 部分。您可以將它們視為桌子的骨架。

## 第 3 步：設定標題單元格的樣式

設定標題單元格的樣式可以使它們脫穎而出。在這裡，我們套用背景顏色、邊框和文字對齊方式。

```csharp
int colCount = 4;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
    thElement.BackgroundColor = Color.GreenYellow;
    thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
    thElement.IsNoBorder = true;
    thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
    thElement.Alignment = HorizontalAlignment.Right;
}
```

在此步驟中，我們循環遍歷每個標題單元格，為其提供綠黃色背景、灰色邊框和右對齊文字。您可以調整這些屬性以符合您所需的設計。

## 第 4 步：填滿表體並設定其樣式

表體包含實際數據。以下介紹如何使用特定的邊距、邊框和文字設定來設定每個儲存格的樣式。

```csharp
int rowCount = 4;

for (int rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = $"Row {rowIndex}";

    for (int colIndex = 0; colIndex < colCount; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
        tdElement.BackgroundColor = Color.Yellow;
        tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
        tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
        tdElement.Alignment = HorizontalAlignment.Center;
        
        TextState cellTextState = new TextState();
        cellTextState.ForegroundColor = Color.DarkBlue;
        cellTextState.FontSize = 7.5F;
        cellTextState.FontStyle = FontStyles.Bold;
        cellTextState.Font = FontRepository.FindFont("Arial");
        tdElement.DefaultCellTextState = cellTextState;
    }
}
```

在此步驟中，我們用四行填充表格主體，並使用黃色背景和居中的粗體藍色文字設定每個儲存格的樣式。我們也使用`MarginInfo`類別來定義文字周圍的填充。

## 第 5 步：設定頁尾樣式

為了給表格一個完整的結構，我們添加頁腳單元格並設定樣式，就像我們對頁眉所做的那樣。

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText($"Foot {colIndex}");
}
```

頁尾部分的樣式與頁首類似，讓讀者可以輕鬆理解表格的結構。

## 第 6 步：儲存並驗證 PDF 文檔

最後，我們儲存 PDF 文件並檢查它是否符合 PDF/UA 標準。

```csharp
//儲存標記的 PDF 文檔
document.Save(dataDir + "StyleTableCell.pdf");

//檢查 PDF/UA 合規性
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

我們保存 PDF 並使用`Validate`確保其符合無障礙標準（PDF/UA 合規性）的方法。

## 結論

使用 Aspose.PDF for .NET 設計 PDF 中的表單既強大又靈活。只需幾行程式碼，您就可以建立自訂表格設計，使您的 PDF 文件脫穎而出。從自訂儲存格邊框和背景到確保輔助使用合規性，Aspose.PDF 可以輕鬆建立精美的 PDF 檔案。

## 常見問題解答

### 我可以對各個表格單元格套用不同的樣式嗎？  
是的，您可以透過自訂單一儲存格的樣式`TableTDElement`特性。

### 如何合併表格儲存格？  
您可以使用`ColSpan`和`RowSpan`屬性來合併表格中的儲存格。

### 是否可以建立符合 PDF/UA 標準的表格？  
是的，如本指南中所示，您可以透過使用以下方法驗證文件來確保 PDF/UA 合規性：`Validate`方法。

### 我可以在表格儲存格中使用不同的字體嗎？  
絕對地！您可以使用指定不同的字體`TextState`每個單元格的物件。

### 如何下載 .NET 版 Aspose.PDF？  
您可以從[發布頁面](https://releases.aspose.com/pdf/net/).