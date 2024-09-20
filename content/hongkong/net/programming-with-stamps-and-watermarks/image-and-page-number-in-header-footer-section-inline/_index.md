---
title: 頁眉頁腳部分內嵌的影像和頁碼
linktitle: 頁眉頁腳部分內嵌的影像和頁碼
second_title: Aspose.PDF for .NET API 參考
description: 透過此逐步指南，了解如何使用 Aspose.PDF for .NET 在 PDF 的頁首部分內嵌新增影像和頁碼。
type: docs
weight: 120
url: /zh-hant/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
## 介紹

Aspose.PDF for .NET 是一個功能強大的工具，提供了操作和產生 PDF 檔案的廣泛功能。無論您需要新增圖像、自訂頁首和頁尾或管理文本，Aspose.PDF 都能滿足您的需求。在本教學中，我們將探討如何在 PDF 文件的頁首或頁尾中新增內嵌圖像和頁碼。讓我們直接深入並逐步分解該過程。

## 先決條件

在我們開始編寫程式碼之前，讓我們確保您已準備好可以遵循的所有內容：

-  Aspose.PDF for .NET：從以下位置下載最新版本[Aspose PDF 下載頁面](https://releases.aspose.com/pdf/net/).
- 開發環境：您需要一個 C# IDE，例如 Visual Studio。
- 許可證：如果您還沒有許可證，您可以獲得[臨時許可證在這裡](https://purchase.aspose.com/temporary-license/)或從[阿斯普斯商店](https://purchase.aspose.com/buy).

現在您已準備好先決條件，讓我們開始吧。

## 導入包

在開始編碼之前，請確保導入必要的命名空間：

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

這些套件可讓您處理 PDF 文件和文字操作。

## 第 1 步：設定文檔目錄

我們需要做的第一件事是定義保存 PDF 檔案的目錄路徑。可以將此路徑自訂為專案的資料夾或電腦上的任何位置。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

此變數保存文檔的儲存位置。代替`"YOUR DOCUMENT DIRECTORY"`與實際路徑。

## 第 2 步：實例化 PDF 文檔

在此步驟中，我們建立一個新實例`Aspose.Pdf.Document`目的。該物件將作為 PDF 文件的主幹。

```csharp
//透過呼叫其空建構函數來實例化 Document 對象
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

在這裡，我們建立一個空白 PDF 文件，稍後可以填入內容。

## 第 3 步：向 PDF 新增頁面

您的 PDF 至少需要一頁，您可以在其中新增頁首、頁尾和內容。讓我們在文件中新增一個空白頁。

```csharp
//在 Pdf 物件中建立頁面
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

透過致電`pdf1.Pages.Add()`，一個新頁面將會新增到文件中，準備進行頁首和頁尾自訂。

## 第 4 步：建立並設定標題

現在是時候為文件建立標題了。我們將在此處添加文字、圖像和頁碼。

```csharp
//建立文件的標題部分
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
//設定 PDF 檔案的標題
page.Header = header;
```

我們創建一個`HeaderFooter`對象並將其分配給`Header`頁面的屬性，確保我們新增到標題的任何內容都會出現在頁面的頂部。

## 第 5 步：將內嵌文字新增至標題

添加文字就像創建一個文字一樣簡單`TextFragment`並指定其屬性。讓我們在標題中添加一些彩色文字。

```csharp
//建立文字對象
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");
//指定顏色
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;
```

在這一步中，我們創建一個`TextFragment`內容為“Aspose.Pdf is a Robust component by”並將其顏色設為藍色。這`IsInLineParagraph`屬性確保文字是內聯的，這意味著它將與其他元素（如圖像和附加文字）顯示在同一行。

## 第 6 步：在頁眉中插入內嵌影像

為了使標題具有視覺吸引力，您可以添加與文字內嵌的圖像。這可以是您的公司徽標或任何其他圖形。

```csharp
//在該部分中建立圖像對象
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
//設定圖片檔案路徑
image1.File = dataDir + "aspose-logo.jpg";
//設定圖像寬度資訊
image1.FixWidth = 50;
image1.FixHeight = 20;
//指示 seg1 的 InlineParagraph 是圖像。
image1.IsInLineParagraph = true;
```

在這裡，我們透過創建一個圖像將圖像添加到標題中`Image`對象，設定其路徑，並調整寬度和高度。這`IsInLineParagraph`確保圖像與文字對齊。

## 步驟 7：新增額外的內嵌文字以完成標題

讓我們添加更多文字來完成內聯標題。

```csharp
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

在這一部分，我們創建另一個`TextFragment`內容為“Pty Ltd.”並將其顏色設為栗色。文字片段和圖像都添加到標題中。

## 第 8 步：儲存 PDF

設定標題後，就可以儲存 PDF 了。

```csharp
//儲存 PDF
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

這`Save`方法將最終的 PDF 檔案寫入指定位置。

## 結論

恭喜！您已使用 Aspose.PDF for .NET 成功將影像和文字新增至 PDF 文件的頁首。本教學引導您完成基本步驟，包括建立文件、新增頁面、插入標題以及放置文字和圖像等內聯內容。 Aspose.PDF 為您提供了令人難以置信的靈活性來管理您的 PDF，無論是操作頁首、頁尾還是複雜的內容。 

## 常見問題解答

### 我可以在頁眉中加入頁碼嗎？
是的！您可以使用以下命令輕鬆新增頁碼`TextFragment`類別並根據需要對其進行格式化。只需將其作為內聯內容插入標題部分即可。

### 如何在標題中設定背景圖片？
您可以使用`BackgroundImage`的財產`HeaderFooter`類別來設定背景圖像。但是，這不是內聯內容，它將覆蓋整個標題區域。

### 除了 JPEG 之外，是否可以使用其他影像格式？
絕對地！ Aspose.PDF支援多種影像格式，例如PNG、BMP和GIF。

### 我可以自訂標題中文字的字體嗎？
是的，您可以使用`TextState`物件變更文字的字體、大小和樣式。

### 我需要許可證才能使用 Aspose.PDF for .NET 嗎？
是的，Aspose.PDF 需要生產使用許可證，但您可以從[在這裡免費試用](https://releases.aspose.com/).