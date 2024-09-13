---
title: 在 PDF 檔案中套用數字樣式
linktitle: 在 PDF 檔案中套用數字樣式
second_title: Aspose.PDF for .NET API 參考
description: 透過此逐步指南，了解如何使用 Aspose.PDF for .NET 將不同的數字樣式（羅馬數字、字母順序）套用至 PDF 中的標題。
type: docs
weight: 10
url: /zh-hant/net/programming-with-headings/apply-number-style/
---
## 介紹

您是否曾經發現自己需要在 PDF 文件中添加精美的編號清單？無論您是要格式化法律文件、報告還是演示文稿，正確的編號樣式對於組織資訊至關重要。使用 Aspose.PDF for .NET，您可以將各種編號樣式套用至 PDF 檔案的標題，從而建立結構良好的專業文件。 

## 先決條件

在深入編碼之前，讓我們先回顧一下您需要什麼：

1. Aspose.PDF for .NET：從以下位置下載最新版本的 Aspose.PDF[這裡](https://releases.aspose.com/pdf/net/).
2. 開發環境：確保您有 Visual Studio 或任何其他 .NET 相容的 IDE。
3. .NET Framework：確保您已安裝 .NET Framework 4.0 或更高版本。
4. 許可證：您可以使用臨時許可證[這裡](https://purchase.aspose.com/temporary-license/)或探索[免費試用](https://releases.aspose.com/)選項。

## 導入包

首先，請確保您的專案中匯入了以下命名空間：

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 第 1 步：設定文檔

讓我們先建立一個新的 PDF 文件並配置其頁面設定。我們將設定頁面大小和邊距來控制內容的佈局。

說明： 在此步驟中，我們將設定 PDF 的基本結構，其中包括定義頁面大小、高度和邊距以保持格式一致。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();

//設定頁面尺寸和邊距
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

透過執行此操作，您的文件將具有標準頁面尺寸，相當於 8.5 x 11 英吋的頁面，並且所有邊的邊距為 72 磅（或 1 英吋）。

## 步驟 2：將頁面新增至 PDF

接下來，我們將在 PDF 文件中新增一個新頁面，稍後我們將在其中套用編號樣式。

說明：每個 PDF 都需要頁面！此步驟將空白頁面新增至 PDF 並設定其邊距以符合文件層級設定。

```csharp
//為 PDF 文件新增頁面
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
```

## 第三步：創建一個浮動框

FloatingBox 可讓您將內容（如文字或標題）放置在一個獨立於頁面流的行為的方塊中。當您想要完全控制內容的佈局時，這非常有用。

說明：在這裡，我們設定一個 FloatingBox 來包含將套用數字樣式的標題。

```csharp
//為結構化內容創建 FloatingBox
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
```

## 步驟 4：新增帶有羅馬數字的第一個標題

現在到了令人興奮的部分！讓我們加入小寫羅馬數字編號的第一個標題。

說明：我們將 NumberingStyle.NumeralsRomanLowercase 樣式套用至標題，該樣式將以羅馬數字（i、ii、iii 等）顯示編號。

```csharp
//使用羅馬數字創建第一個標題
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading.IsInList = true;
heading.StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);
```

## 步驟 5：新增第二個羅馬數字標題

出於演示目的，我們添加第二個羅馬數字標題，但這次我們將從 13 開始。

說明： StartNumber 屬性可讓您從自訂數字開始編號 - 在本例中，我們從 13 開始。

```csharp
//創建從羅馬數字 13 開始的第二個標題
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "List 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);
```

## 第 6 步：新增按字母順序編號的標題

為了多樣化，我們添加第三個標題，但這次我們將使用小寫字母順序編號（a、b、c 等）。

說明：將 NumberingStyle 更改為 LettersLowercase 允許我們將字母編號應用於標題。

```csharp
//建立帶有字母編號的標題
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "the value, as of the effective date of the plan, of property to be distributed under the plan on account of each allowed";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
```

## 第 7 步：儲存 PDF

最後，套用所有標題和數字樣式後，將 PDF 檔案儲存到您想要的目錄。

說明：此步驟儲存包含所有已套用編號樣式的格式化標題的 PDF 檔案。

```csharp
//儲存 PDF 文件
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumber style applied successfully in headings.\nFile saved at " + dataDir);
```

## 結論

現在你就得到它了！您已使用 Aspose.PDF for .NET 成功將編號樣式（羅馬數字和信件）套用到 PDF 檔案中的標題。 Aspose.PDF 為控制頁面佈局、編號樣式和內容定位提供了靈活性，為您提供了創建組織良好的專業 PDF 文件的強大工具集。

## 常見問題解答

### 我可以對同一個 PDF 文件套用不同的數位樣式嗎？  
是的，Aspose.PDF for .NET 可讓您在相同文件中混合不同的編號樣式，例如羅馬數字、阿拉伯數字和字母編號。

### 如何自訂標題的起始編號？  
您可以使用以下指令設定任何標題的起始編號`StartNumber`財產。

### 有沒有辦法重新設定編號順序？  
是的，您可以透過調整`StartNumber`每個標題的屬性。

### 除了編號之外，我還可以對標題套用粗體或斜體樣式嗎？  
絕對地！您可以使用以下命令修改字體、大小、粗體和斜體等屬性來自訂標題樣式`TextState`目的。

### 如何取得 Aspose.PDF 的臨時授權？  
您可以從以下地址取得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/)無限制地測試 Aspose.PDF。