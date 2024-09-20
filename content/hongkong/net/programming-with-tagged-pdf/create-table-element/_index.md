---
title: 建立表元素
linktitle: 建立表元素
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 建立陣列元素的逐步指南。輕鬆產生帶有表格的動態 PDF。
type: docs
weight: 80
url: /zh-hant/net/programming-with-tagged-pdf/create-table-element/
---
## 介紹

您是否想過如何使用 .NET 輕鬆建立和自訂 PDF 中的表格元素？那麼，Aspose.PDF for .NET 是您的首選解決方案！無論您是自動產生報告還是為各種文件動態建立表格，Aspose.PDF 都提供了豐富的 API 來處理表格元素。本指南將引導您逐步了解如何建立表格、設定表格樣式，甚至確保其符合 PDF/UA 合規性標準。聽起來很令人興奮，對吧？讓我們深入探討吧！

## 先決條件

在我們開始之前，您需要做好一些準備：
1.  Aspose.PDF for .NET：從以下位置下載最新版本[Aspose.PDF for .NET 下載](https://releases.aspose.com/pdf/net/).
2. 開發環境：任何支援.NET 的IDE（例如Visual Studio）。
3. C# 基礎知識：建議熟悉 C# 程式設計。

最後，不要忘記您的 Aspose.PDF 許可證。如果您沒有，您可以使用[免費試用](https://releases.aspose.com/)或請求[臨時執照](https://purchase.aspose.com/temporary-license/)測試一切。

## 導入包

首先，讓我們導入必要的套件。這將使我們能夠使用所有相關類別在 PDF 文件中建立表格。

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

在本節中，我們將把建立表格的過程分解為多個步驟。每個步驟都專注於表格創建和定製過程的不同部分。

## 第 1 步：建立新的 PDF 文檔

我們需要做的第一件事是建立一個新的 PDF 文件。這將作為我們桌子的容器。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//建立新的 PDF 文檔
Document document = new Document();
```

在這裡，我們正在初始化一個新實例`Document`類，這將是我們的空白 PDF 文件。不要忘記定義您的檔案路徑！

## 第 2 步：設定標記內容

接下來，我們需要啟用標記內容，以確保表格的可存取性。需要加標籤的 PDF 才能符合 PDF/UA（通用輔助功能）。

```csharp
//啟用標記內容
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Table");
taggedContent.SetLanguage("en-US");
```

此步驟設定文件標題和語言，確保表格符合輔助功能標準。擁有可存取的文件對於某些行業的使用者體驗和法律要求至關重要。

## 第 3 步：建立表格元素

現在到了有趣的部分——創建表格本身！

```csharp
//取得根結構元素
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

在這裡，我們使用的是`RootElement`標記的內容附加到我們的表格中。這本質上是將表作為子節點添加到文件的結構中。

## 第 4 步：自訂表格邊框和標題

您不希望您的桌子看起來平淡無奇，對嗎？讓我們添加一些樣式！

```csharp
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

我們正在定義邊框並在表格中新增頁首、正文和頁尾。注意使用`BorderInfo`將表格邊框設定為深藍色。

## 第 5 步：將行和單元格新增至表中

現在，讓我們用行和儲存格填滿表格。過程的這一部分是我們定義表格佈局的地方。

### 步驟 5.1：建立標題行

```csharp
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
headTrElement.BackgroundColor = Color.LightGray;

for (int colIndex = 0; colIndex < 4; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
    thElement.BackgroundColor = Color.GreenYellow;
    thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
    thElement.Alignment = HorizontalAlignment.Right;
}
```

我們正在建立一個包含 4 列的標題行，每個標題單元格的背景顏色為`GreenYellow`。我們還為標題設定了邊框和對齊方式。

### 步驟5.2：新增正文行

```csharp
for (int rowIndex = 0; rowIndex < 50; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = $"Row {rowIndex}";

    for (int colIndex = 0; colIndex < 4; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
        tdElement.BackgroundColor = Color.Yellow;
        tdElement.Alignment = HorizontalAlignment.Center;
    }
}
```

在這裡，我們動態建立 50 行和 4 列，用文字填滿它們並設定儲存格樣式。背景顏色設定為黃色，文字置中。

### 步驟 5.3：新增頁尾行

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
footTrElement.BackgroundColor = Color.LightSeaGreen;

for (int colIndex = 0; colIndex < 4; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText($"Foot {colIndex}");
    tdElement.Alignment = HorizontalAlignment.Center;
}
```

為了完成表格，我們添加一個帶有居中文字的頁腳和一個`LightSeaGreen`背景。

## 第 6 步：驗證 PDF/UA 合規性

建立表格後，確保 PDF 符合 PDF/UA 要求至關重要。

```csharp
document.Save(dataDir + "CreateTableElement.pdf");

//驗證 PDF/UA 合規性
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

此程式碼片段保存 PDF 檔案並檢查它是否符合 PDF/UA 合規性標準。如果文件符合要求，殘障使用者就可以存取它。

## 結論

恭喜！您已使用 Aspose.PDF for .NET 在 PDF 中成功建立了完全自訂的表格。從設計表格樣式到確保 PDF/UA 合規性，您現在擁有在 PDF 文件中產生動態表格的堅實基礎。不要忘記探索 Aspose.PDF 的廣泛功能以進一步增強您的文件！

## 常見問題解答

### 我可以自訂表格的字體和文字樣式嗎？
是的，Aspose.PDF 允許您使用以下命令完全自訂字體、文字樣式和對齊方式：`TextState`班級。

### 如何動態新增更多列或行？
您可以透過修改以下內容來調整列數或行數`rowIndex`和`colIndex`在循環中。

### 是否可以合併表格中的儲存格？
是的，您可以使用`ColSpan`和`RowSpan`跨列或行合併儲存格的屬性。

### 什麼是 PDF/UA 合規性？
PDF/UA 合規性確保殘障使用者可以存取該文檔，並遵守國際無障礙標準。

### 如何在 Aspose.PDF 中測試 PDF/UA 合規性？
您可以使用`Validate`檢查文件是否符合 PDF/UA 標準的方法。