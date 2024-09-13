---
title: 頁眉頁尾部分中的圖像和頁碼
linktitle: 頁眉頁尾部分中的圖像和頁碼
second_title: Aspose.PDF for .NET API 參考
description: 在此逐步教學中，了解如何使用 Aspose.PDF for .NET 將圖像和頁碼新增至 PDF 的頁首和頁尾。
type: docs
weight: 110
url: /zh-hant/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section/
---
## 介紹

在建立專業級 PDF 文件時，控制頁首和頁尾等次要細節至關重要。您希望您的文件看起來整潔且組織良好，對嗎？那麼，使用 Aspose.PDF for .NET，您可以將影像和頁碼無縫新增至文件的頁首和頁尾部分。在本教程中，我們將引導您完成每個步驟，使其易於遵循。

## 先決條件

在深入了解本教學的實質內容之前，請確保您已整理好以下內容：

1. .NET Framework：您需要在電腦上安裝任意版本的 .NET Framework。如果沒有，您可以輕鬆地從 Microsoft 網站下載。
2.  Aspose.PDF for .NET：由於我們將使用 Aspose.PDF，請確保您已將其安裝在專案中。您可以下載試用版[這裡](https://releases.aspose.com/pdf/net/).
3. C# 基礎知識：熟悉基本的 C# 程式設計肯定會幫助您輕鬆理解程式碼。
4. 圖像檔案：您需要將圖像放入 PDF 文件的頁眉中，例如徽標。將其保存在可存取的目錄中。 
5. IDE：使用您選擇的整合開發環境 (IDE)（例如 Visual Studio）來處理您的 .NET 專案。

準備好先決條件後，您就可以建立精美的 PDF 檔案了！

## 導入包

要開始使用 Aspose.PDF for .NET，您需要匯入必要的命名空間。在 C# 檔案的頂部，您可以新增：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Image;
```

這些命名空間將使您能夠存取操作 PDF 文件所需的類別。

現在讓我們開始真正的交易吧！請依照下列步驟建立 PDF 文檔，在頁首中合併影像，在頁尾中合併頁碼。

## 第 1 步：設定您的文件目錄

每個好的項目都始於組織。定義儲存檔案和影像的文件目錄。操作方法如下：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

記得更換`"YOUR DOCUMENT DIRECTORY"`以及您想要儲存 PDF 和影像的實際路徑。

## 第 2 步：建立新的 PDF 文檔

接下來，我們將建立一個新的 PDF 文檔，所有的魔法都會在其中發生：

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

至此，您已經建立了一個空的 PDF 文件。令人興奮，不是嗎？

## 步驟 3：新增頁面

PDF 就是關於頁面的。讓我們使用以下命令為文件新增頁面：

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

現在您已經有了可以開始設計的畫布！

## 第 4 步：建立標題部分

您的標題將包含您想要顯示的圖像（如徽標）。使用以下程式碼建立標頭部分：

```csharp
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
page.Header = header;
```

現在您有了可以自訂的標題！

## 第 5 步：將圖像新增至標題

現在我們進入有趣的部分了！您需要將圖像新增至標題。首先，建立一個影像物件：

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
```

設定影像的檔案路徑：

```csharp
image1.File = dataDir + "aspose-logo.jpg";
```

最後，將圖像新增至標題：

```csharp
header.Paragraphs.Add(image1);
```

恭喜！您剛剛將圖像新增至 PDF 標題。

## 第 6 步：建立頁尾部分

現在讓我們處理頁腳。與頁首流程類似，建立頁尾物件：

```csharp
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();
page.Footer = footer;
```

您將在此處放置頁碼。 

## 第 7 步：將文字新增至頁尾

建立一個包含頁碼的文字片段：

```csharp
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P ) ");
```

然後將此文字片段新增至頁尾：

```csharp
footer.Paragraphs.Add(txt);
```

看看那是多麼容易嗎？您已動態設定頁碼！

## 步驟 8：儲存 PDF 文檔

我們冒險的最後一步是儲存文件。使用此命令儲存新建立的 PDF：

```csharp
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");
```

就像這樣，您的 PDF 已準備就緒，並在頁腳中加載了頁眉圖像和頁碼！

## 結論

現在你就得到它了！您剛剛使用 Aspose.PDF for .NET 建立了一個 PDF，其中頁首中有圖像，頁腳中有動態頁碼。幾行程式碼就能產生如此精美的輸出，真是令人難以置信。無論是公司報告還是個人化文檔，添加這些元素都會改變 PDF 的基調和專業性。

## 常見問題解答

### 我可以在任何 .NET 平台上使用 Aspose.PDF 嗎？
是的，Aspose.PDF for .NET 支援多種 .NET 平台，包括 .NET Framework、.NET Core 等。

### Aspose.PDF 是否有免費試用版？
絕對地！您可以下載免費試用版[這裡](https://releases.aspose.com/).

### 標題支援哪些圖像格式？
Aspose.PDF 支援最常見的圖片格式，例如頁首和頁尾的 JPG、PNG 和 BMP。

### 我可以自訂頁碼格式嗎？
是的，您可以根據需要輕鬆自訂頁腳文字和格式。

### 是否提供技術支援？
是的，Aspose 透過他們的論壇提供專門的支援。您可以尋求協助[這裡](https://forum.aspose.com/c/pdf/10).