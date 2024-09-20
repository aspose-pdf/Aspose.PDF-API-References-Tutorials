---
title: 在 PDF 檔案中將文字放置在圖像周圍
linktitle: 在 PDF 檔案中將文字放置在圖像周圍
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 中的圖像周圍放置文字。按照我們的逐步指南建立圖像和文字並排的專業 PDF。
type: docs
weight: 260
url: /zh-hant/net/programming-with-text/placing-text-around-image/
---
## 介紹

您是否曾經嘗試過在 PDF 文件中的圖像周圍放置文本，但發現這很困難？如果是這樣，那麼您來對地方了！ Aspose.PDF for .NET 讓這個過程變得簡單，只需幾行程式碼即可將文字與圖像一起放置。無論您是建立報告、文件還是簡報，此功能都是增強內容佈局並使其更具視覺吸引力的絕佳方式。今天，我們將介紹如何使用 Aspose.PDF for .NET 在 PDF 文件中的圖像周圍放置文字。

## 先決條件

在我們開始編寫程式碼之前，讓我們確保我們已經完成了所有設定。這是您需要的：

-  Aspose.PDF for .NET：您可以從以下位置下載：[這裡](https://releases.aspose.com/pdf/net/).
- Visual Studio：確保安裝了最新版本以便順利進行。
- .NET Framework：此範例使用 .NET，因此請確保您的環境已設定為 .NET 開發。
- 臨時許可證：您可以申請臨時許可證[這裡](https://purchase.aspose.com/temporary-license/)如果您正在評估產品。

如果您尚未設定 Aspose.PDF for .NET，請依照下列安裝說明進行操作[文件](https://reference.aspose.com/pdf/net/).

## 導入命名空間

在開始編碼之前，我們需要導入必要的名稱空間。這是執行此操作的程式碼片段：

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

這些命名空間至關重要，因為它們提供對此類的訪問`Document`, `Page`, `Image`， 和`HtmlFragment`，我們將使用它來建立和操作 PDF。

現在我們已經做好準備，讓我們詳細介紹如何使用 Aspose.PDF for .NET 在 PDF 文件中的圖像周圍放置文字。我們將逐步引導您完成此過程。

## 第 1 步：實例化文檔對象

首先，您需要建立一個 PDF 文件。在 Aspose.PDF 中，這是透過實例化一個`Document`目的。該物件將作為我們將要添加的所有內容的基礎。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

在這裡，我們建立了一個空的 PDF 文件。它還沒有任何頁面，但不用擔心，我們將在下一步中添加一個。

## 步驟 2：新增頁面

現在我們已經有了文檔，是時候新增頁面了。將此視為創建一張白紙，您可以在其中添加內容。

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

此程式碼會為文件新增一個新頁面。預設情況下，該頁面是空白的，但我們即將更改它。

## 第 3 步：建立表格來組織內容

為了保持圖像和文字正確對齊，我們將使用表格。 PDF 中的表格可以幫助建立您的佈局，就像 Word 文件或 HTML 中的表格一樣。

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

此程式碼片段建立一個表並將其新增至頁面。將表格視為對齊圖像和文字的框架。

## 步驟 4：設定表格的列寬

現在我們已經新增了一個表，我們需要定義列的寬度。這可確保圖像和文字在頁面上的大小適當。

```csharp
table1.ColumnWidths = "120 270";
```

該行設定兩列的寬度－一列用於圖像，一列用於文字。如果您的圖像或文字需要更多或更少的空間，請調整這些值。

## 第 5 步：定義邊距和填充

為了確保一切看起來整潔，讓我們在表格中添加一些邊距和填充。

```csharp
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
table1.DefaultCellPadding = margin;
```

這些設定可確保您的表格具有一致的間距，使內容具有視覺吸引力。

## 第 6 步：將圖像插入表中

現在，讓我們開始有趣的部分——添加圖像。在本例中，我們將添加 Aspose 徽標，但您可以隨意使用您喜歡的任何圖像。

```csharp
Aspose.Pdf.Row row1 = table1.Rows.Add();
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

這是發生的事情：
- 我們從您指定的目錄載入圖片。
- 我們設定圖像的高度和寬度。
- 最後，我們將圖像添加到表中的第一個單元格中。

## 第 7 步：在圖像旁邊新增文本

現在圖像已就位，讓我們在其旁邊添加一些文字。對於本範例，我們將使用 HTML 格式的文字來設定內容的樣式。

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF document reporting component that enables .NET applications to <b>create PDF documents from scratch</b> without utilizing Adobe Acrobat.</font>";

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

此區塊在圖像旁邊的儲存格中新增樣式標題和描述。您可以使用 HTML 標籤設定文字格式以進行更多自訂。

## 第 8 步：調整垂直對齊方式

預設情況下，表格儲存格中的內容可能不會按照您想要的方式對齊。在本例中，我們要確保文字與儲存格頂部對齊。

```csharp
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
```

這可以確保文字位於單元格的頂部，保持佈局乾淨和專業。

## 第 9 步：在圖像和描述下方添加更多文本

您可能希望在圖像和文字下方包含更多內容。為此，我們在表中添加另一行。

```csharp
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
SecondRow.Cells[0].ColSpan = 2;
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

在這裡，我們添加了另一行帶有附加文字的行，跨越兩列以保持佈局平衡。

## 第10步：儲存PDF文檔

最後，我們需要儲存文件以便您可以查看變更。

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

這將保存 PDF，其圖像和文字格式正如我們想要的那樣。

## 結論

在 PDF 中的圖像周圍放置文字似乎是一項艱鉅的任務，但 Aspose.PDF for .NET 簡化了這個過程。透過利用表格、圖像和樣式文本，您可以輕鬆建立具有專業外觀的 PDF。只需幾行程式碼，您就可以將內容準確地放置在您想要的位置，從而使您的文件具有精美且組織良好的外觀。

## 常見問題解答

### 我可以使用此方法將多個圖像與文字一起放置嗎？
是的，只需在表格中新增更多行和儲存格即可包含其他圖像和文字。

### 我可以更改圖像的對齊方式嗎？
絕對地！您可以透過調整儲存格的對齊屬性來修改影像對齊方式。

### 如何進一步設定文字樣式？
您可以在`HtmlFragment`物件套用各種樣式，如粗體、斜體或不同的字體。

### 我可以控製文字和圖像之間的間距嗎？
是的，使用`MarginInfo`物件可讓您控制元素之間的填充和邊距。

### 是否可以在文字中加入連結？
確實！您可以使用以下命令在 HTML 格式的文字中嵌入超鏈接`<a>`標籤。