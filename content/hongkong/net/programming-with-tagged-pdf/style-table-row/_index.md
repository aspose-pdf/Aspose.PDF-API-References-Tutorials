---
title: 樣式表行
linktitle: 樣式表行
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 設定 PDF 中表格行的樣式，並透過逐步指南輕鬆增強文件格式設定。
type: docs
weight: 180
url: /zh-hant/net/programming-with-tagged-pdf/style-table-row/
---
## 介紹

在建立結構良好且格式精美的 PDF 文件時，Aspose.PDF for .NET 是首選解決方案。無論您是自動化報告、發票還是建立動態表格，使用各種樣式設定表格格式都是精美文件的關鍵。在本教學中，我們將深入研究使用 Aspose.PDF for .NET 設計表格行的樣式。別擔心，我會一步步指導您，就像喝咖啡時愉快的交談一樣！

## 先決條件

在我們深入討論實際問題之前，讓我們先確保您已將所有事情安排妥當。你需要：

1. Aspose.PDF for .NET 函式庫  
   如果您還沒有，您可以從[這裡](https://releases.aspose.com/pdf/net/)。您還可以獲得[免費試用](https://releases.aspose.com/)開始吧。
2. 開發環境  
   設定 Visual Studio 或您選擇的任何 C# IDE。您還需要安裝 .NET，但我猜您已經熟悉它了。
3. C# 和 .NET 基礎知識  
   對 C# 的充分理解將使本教程變得輕而易舉。但不用擔心，我會詳細解釋每個步驟！

## 導入包

在開始使用 Aspose.PDF 之前，我們需要匯入必要的命名空間。在您的 C# 專案中，確保包含以下內容：

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

這些對於建立表格和設定表格樣式至關重要，當然對於處理標記內容以確保合規性也至關重要。

現在讓我們逐步分解任務，以便您可以像專業人士一樣設定表格行的樣式！

## 第 1 步：建立新的 PDF 文檔

首先，讓我們建立一個全新的 PDF 文件。該文件將保存所有樣式表行。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//建立文檔
Document document = new Document();
```

在這裡，我們只是初始化一個新的`Document`代表我們的 PDF 文件的對象。確保設定保存輸出檔案的目錄路徑。

## 第 2 步：使用標記內容

為了建立您的 PDF 以便於訪問，我們將使用標記的內容。這有助於建立表格等結構化元素，確保它們符合 PDF/UA 等輔助功能標準。

```csharp
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");
```

在這裡，我們設定 PDF 標記內容的標題和語言。這就像是為您的 PDF 命名並告訴它應該使用哪種語言！

## 步驟 3：定義表結構

接下來，讓我們定義要建立的表格的結構。每個表格都需要頁眉、正文和頁腳 - 就像組織良好的部落格文章一樣！

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

我們在這裡所做的是創建一個帶有標題的表（`THead`), 身體 (`TBody`) 和頁尾 (`TFoot`）。這些元素將保留我們的行。

## 步驟 4：新增表格標題行

沒有標題的表格就像沒有標題的書一樣。讓我們先建立標題行以提供資料上下文。

```csharp
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText(String.Format("Head {0}", colIndex));
}
```

在這裡，我們循環並添加三個標題單元格（`TableTHElement`），給每個人一個描述性文字。很簡單，對吧？

## 步驟5：新增有樣式的身體行

現在到了有趣的部分——設計行的樣式！讓我們使用自訂樣式建立七行。我們將設定背景顏色、邊框、填滿和文字對齊方式。

```csharp
for (int rowIndex = 0; rowIndex < 7; rowIndex++)
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

    for (int colIndex = 0; colIndex < 3; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
    }
}
```

- 背景顏色：我們使用淺黃花，營造出專業而溫暖的感覺。
- 邊框：每行都有一個深灰色的外邊框和藍色的單元格邊框，以獲得清晰的外觀。
- 高度和填充：設定行高，並添加填充以獲得乾淨的外觀。
- 分頁符號：為了讓表格更具可讀性，每隔一行就從一個新頁面開始。

## 第 6 步：新增頁尾行

與頁首非常相似，頁腳固定表格。讓我們創建一個。

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText(String.Format("Foot {0}", colIndex));
}
```

我們只需循環訪問三個頁腳單元格並添加一些文字。頁腳的替代文字是“Foot Row”，以使其易於存取。

## 第7步：儲存PDF文檔

現在桌子已經準備好了，是時候保存你的傑作了！

```csharp
document.Save(dataDir + "StyleTableRow.pdf");
```

就像這樣，您的 PDF 與我們剛剛設定樣式的所有漂亮表格行一起保存。

## 第 8 步：驗證 PDF/UA 合規性

為了確保我們的 PDF 符合輔助功能標準，我們將驗證其 PDF/UA 合規性。

```csharp
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

這可確保您的 PDF 符合 PDF/UA 標準，讓每個人都可以存取。無障礙是遊戲的名稱！

## 結論

現在你就擁有了！只需幾行程式碼，您就可以使用 Aspose.PDF for .NET 在 PDF 中建立一個完全樣式化的表格。從頁首到頁腳，我們設計了每一行的樣式，並添加了輔助功能元素，甚至驗證了文件的合規性。無論您是在處理公司報告、簡報，還是只是享受 PDF 帶來的樂趣，本指南都能滿足您的需求。現在，繼續像專業人士一樣開始設計您的桌子吧！

## 常見問題解答

### 我也可以更改表格的字體樣式嗎？  
是的！您可以使用以下命令修改字體樣式`TextState`每個單元格的對象，允許完全自訂。

### 如何在表中新增更多列？  
只需調整`colCount`變數並在頁首、正文和頁尾的循環中加入更多單元格。

### 如果我不設定行高會發生什麼事？  
如果不設定行高，表格會根據內容自動調整。

### 我可以將其用於動態行數嗎？  
絕對地！您可以從資料庫或任何其他來源取得資料並動態調整行數和列數。

### Aspose.PDF for .NET 可以免費使用嗎？  
 Aspose.PDF for .NET 是一個授權產品，但您可以使用[免費試用](https://releases.aspose.com/)或得到一個[臨時執照](https://purchase.aspose.com/temporary-license/).