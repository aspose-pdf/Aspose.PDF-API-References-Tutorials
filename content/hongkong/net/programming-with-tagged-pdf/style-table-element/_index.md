---
title: 樣式表元素
linktitle: 樣式表元素
second_title: Aspose.PDF for .NET API 參考
description: 透過逐步說明、自訂樣式和 PDF/UA 合規性，了解如何在 Aspose.PDF for .NET 中建立表格元素並為其設定樣式。
type: docs
weight: 170
url: /zh-hant/net/programming-with-tagged-pdf/style-table-element/
---
## 介紹

在本文中，我們將深入探討如何使用 Aspose.PDF for .NET 建立表格元素並設定其樣式。您將學習如何建立表格、應用自訂樣式以及驗證文件的 PDF/UA 合規性。學完本教學後，您將能夠輕鬆在 PDF 中建立具有專業外觀的表格！

## 先決條件

在開始學習本教學之前，您需要確保具備以下條件：

1. 您的電腦上安裝了 Visual Studio 或類似的 IDE。
2. 用於運行應用程式的.NET Framework 或.NET Core SDK。
3. 下載 Aspose.PDF for .NET 程式庫並在您的專案中引用。您可以從以下位置取得最新版本[這裡](https://releases.aspose.com/pdf/net/).
4. 有效的 Aspose 許可證或[臨時執照](https://purchase.aspose.com/temporary-license/)解鎖庫的全部功能。

## 導入包

首先，將必要的命名空間匯入到您的專案中：

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

這些命名空間涵蓋核心 PDF 操作、標記內容、表格和文字格式。

現在讓我們分解一下在 Aspose.PDF 中建立表格並設定表格樣式的過程。我們將詳細介紹每個部分，以便您可以遵循。

## 步驟 1：建立新的 PDF 文件並設定標記內容

在第一步驟中，我們將建立一個空白 PDF 文件並設定其標記內容。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//建立新的 PDF 文檔
Document document = new Document();

//設定標記內容
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");
```

我們首先創建一個新的`Document`對象，代表我們的 PDF。這`TaggedContent`物件用於管理文件的結構，確保符合可訪問性標準。我們設定文件的標題和語言以進行正確的標記。

## 第 2 步：定義根元素

接下來，我們將建立根結構元素，它充當 PDF 中所有內容的容器。

```csharp
//取得根結構元素
StructureElement rootElement = taggedContent.RootElement;
```

這`RootElement`作為所有結構化元素（包括我們的表格）的基礎容器。它有助於維護文件的結構層次結構，這對於組織和可訪問性都很重要。

## 第 3 步：建立表格元素並設定其樣式

現在根元素已經設定完畢，我們將建立一個`TableElement`並套用背景顏色、邊框和對齊方式等樣式。

```csharp
//建立表格結構元素
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);

//設計表格樣式
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
```

我們創建一個`TableElement`，它定義了我們的表格結構。這`BackgroundColor`, `Border`， 和`Alignment`屬性允許我們自訂表格的外觀。這`Broken`屬性確保如果表格跨頁中斷，它會垂直中斷。

## 步驟 4：設定表格尺寸和儲存格樣式

在此步驟中，我們將定義列數、儲存格填入和其他重要的表格屬性。

```csharp
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
```

我們指定列寬以確保表中每一列的間距均勻。這`DefaultCellBorder`, `DefaultCellPadding`， 和`DefaultCellTextState`定義儲存格的預設樣式，包括邊框、填滿、文字顏色和字體大小。

## 第 5 步：新增重複行和自訂樣式

我們也可以定義重複行和其他特定表格元素（例如頁首和頁尾）的樣式。

```csharp
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

這`RepeatingRowsCount`如果表格跨越多個頁面，請確保前三行重複。我們設定`RepeatingRowsStyle`將自訂背景顏色套用至這些行。

## 第 6 步：新增桌頭、桌身和桌腳元素

現在，讓我們建立表頭、正文和頁腳部分並用內容填充它們。

```csharp
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

//建立標題行
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 5; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
}

//填充表體
for (int rowIndex = 0; rowIndex < 10; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    for (int colIndex = 0; colIndex < 5; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
    }
}
```

桌子分為三個部分：頭、身、腳。我們首先使用建立標題行`TableTHElement`並新增列標題。然後，我們用以下內容填滿表格主體`TableTDElement`，用包含其位置的標籤填滿每個單元格。

## 步驟7：儲存文檔

最後，我們將PDF文檔儲存到指定目錄。

```csharp
//儲存標記的 PDF 文檔
document.Save(dataDir + "StyleTableElement.pdf");
```

此步驟透過儲存帶有樣式表的 PDF 檔案來完成文件建立過程。

## 第 8 步：驗證 PDF/UA 合規性

儲存文件後，必須確保其符合 PDF/UA（通用輔助功能）標準。

```csharp
//檢查 PDF/UA 合規性
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

在這裡，我們重新載入文件並根據 PDF/UA 標準對其進行驗證。合規性可確保您的 PDF 符合輔助功能要求，使其適合廣泛的使用者。

## 結論

使用 Aspose.PDF for .NET，在 PDF 文件中建立表格並設定樣式變得簡單直觀。透過遵循本教學中概述的步驟，您可以建立具有自訂樣式的表格，並確保您的 PDF 符合輔助功能標準。無論您是產生報告還是建立結構化文檔，表格都是清晰呈現資料的強大工具。

## 常見問題解答

### 我可以在表格單元格內新增圖像嗎？
是的，您可以使用以下命令將圖像插入到表格單元格中`Image`元素。

### 如何動態調整列寬？
您可以設定`ColumnAdjustment`財產給`AutoFitToWindow`根據內容自動調整列寬。

### 所有文件都必須遵守 PDF/UA 規定嗎？
雖然不是強制性的，但建議用於需要高可訪問性標準的文件。

### 我可以對特定行套用不同的樣式嗎？
是的，您可以透過調整各個行或儲存格來自訂它們`TextState`或者`BackgroundColor`.

### 使用標記內容有什麼好處？
標籤的內容提高了文件的可訪問性，並有助於確保符合 PDF/UA 等標準。