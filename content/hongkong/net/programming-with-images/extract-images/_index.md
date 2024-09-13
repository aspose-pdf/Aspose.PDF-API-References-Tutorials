---
title: 從 PDF 檔案中提取圖像
linktitle: 從 PDF 檔案中提取圖像
second_title: Aspose.PDF for .NET API 參考
description: 透過此逐步指南，了解如何使用 Aspose.PDF for .NET 從 PDF 檔案中擷取影像。從易於遵循的說明開始。
type: docs
weight: 120
url: /zh-hant/net/programming-with-images/extract-images/
---
## 介紹

您是否曾經想過如何從 PDF 文件中提取圖像？這聽起來可能很棘手，但使用 Aspose.PDF for .NET，從 PDF 中提取圖像變得輕而易舉！無論您是為了商業、研究還是個人用途而處理文檔，學習提取圖像都可以節省您大量的時間。在本文中，我們將以簡單的對話方式逐步分解它。讓我們深入了解如何使用 Aspose.PDF for .NET 輕鬆從 PDF 檔案中擷取影像。

## 先決條件

在我們深入討論細節之前，讓我們確保您擁有開始使用所需的一切。這是您需要的：

1.  .NET 的 Aspose.PDF Library：確保您已經擁有[Aspose.PDF for .NET](https://releases.aspose.com/pdf/net/)庫已安裝。您可以從連結下載它，也可以透過 Visual Studio 中的 NuGet 安裝它。
2. IDE（整合開發環境）：建議使用 Visual Studio，但任何相容於 .NET 的 IDE 都可以使用。
3. C# 的基本了解：C# 的基本知識很有幫助，但如果您是初學者，請不要擔心 — 我們將指導您完成程式碼！
4. 包含影像的 PDF 文件：包含要擷取的影像的範例 PDF 檔案。
5. 許可證：您可以使用[臨時執照](https://購買.aspose.com/temporary-license/)或者[purchase](https://purchase.aspose.com/buy)如果您沒有免費試用，則需要完整許可證。

## 導入包

首先，您需要從 Aspose.PDF for .NET 程式庫匯入必要的命名空間。這使您能夠處理 PDF 並提取圖像。

```csharp
using System.IO;
using Aspose.Pdf;
using System.Drawing.Imaging;
using System;
```

這些命名空間對於使用 Aspose.PDF for .NET 在 C# 中處理 PDF 和管理映像至關重要。

讓我們將這個過程分解為清晰、易於遵循的步驟。每個步驟旨在引導您完成從 PDF 文件中提取圖像的過程。

## 步驟1：設定文檔目錄路徑

在提取影像之前，您需要指定 PDF 檔案的位置。您還將定義要保存提取的圖像的位置。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

在此行中，替換`"YOUR DOCUMENT DIRECTORY"`以及 PDF 檔案的儲存路徑。這設定輸入和輸出檔案的位置。

## 第 2 步：開啟 PDF 文檔

接下來，您需要載入要從中提取圖像的 PDF 文件。

```csharp
Document pdfDocument = new Document(dataDir + "ExtractImages.pdf");
```

在這裡，您告訴 Aspose.PDF 開啟文件`"ExtractImages.pdf"`從上一個步驟中指定的目錄。確保檔案名稱完全匹配。

## 步驟 3：訪問第一頁的第一張圖片

現在 PDF 文件已加載，下一步是訪問文件第一頁上的第一張圖像。

```csharp
XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
```

此程式碼抓取第一頁上的第一張圖像。如果您的 PDF 有多個頁面或影像，您可以相應地調整數字。這`Pages[1]`指的是第一頁，並且`Images[1]`指該頁面上的第一張圖片。

## 步驟 4：為輸出影像建立檔案流

訪問圖像後，您需要建立一個文件流來保存它。這將指定影像在電腦上的儲存位置和方式。

```csharp
FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
```

在這裡，您將提取的圖像另存為`"output.jpg"`與 PDF 檔案位於同一目錄中。如果您想將其保存在其他地方或更改格式，請隨意修改路徑和檔案名稱。

## 第5步：保存提取的影像

載入圖像並準備好檔案流後，就可以儲存圖像了。

```csharp
xImage.Save(outputImage, ImageFormat.Jpeg);
```

這行程式碼將影像儲存為 JPEG 檔案。您也可以透過變更將其儲存為其他格式，例如 PNG 或 BMP`ImageFormat`範圍。

## 步驟 6：關閉文件流

儲存影像後，必須關閉檔案流以確保沒有資源處於開啟狀態。

```csharp
outputImage.Close();
```

關閉檔案流有助於避免記憶體洩漏並確保檔案正確保存。

## 第 7 步：儲存更新的 PDF 檔案（可選）

儘管此步驟是可選的，但如果您對 PDF 進行了任何變更（例如刪除影像），則可以儲存更新的檔案。這可以使您的 PDF 保持井井有條並保持最新狀態。

```csharp
dataDir = dataDir + "ExtractImages_out.pdf";
pdfDocument.Save(dataDir);
```

此程式碼將更新的 PDF 儲存為`"ExtractImages_out.pdf"`。如果未對 PDF 進行任何更改，您可以跳過此步驟。

## 結論

就是這樣！一旦分解，使用 Aspose.PDF for .NET 從 PDF 檔案中提取影像是一個簡單的過程。無論您處理的是一張或多張影像，這些步驟都將幫助您快速且有效率地完成工作。 Aspose.PDF for .NET 是一個功能強大的工具，讓 PDF 操作變得輕而易舉，本教學只是冰山一角。 

## 常見問題解答

### 我可以一次從不同頁面提取多張圖像嗎？
是的，您可以循環瀏覽頁面和每個頁面中的圖像以一次提取多個圖像。

### 是否可以以 JPEG 以外的格式儲存影像？
絕對地！您可以透過調整將影像儲存為不同的格式，如 PNG、BMP 或 TIFF`ImageFormat`範圍。

### 如果我的 PDF 檔案沒有任何圖像怎麼辦？
如果 PDF 中沒有圖像，Aspose.PDF for .NET 不會拋出錯誤，但不會提取任何內容。您可以新增錯誤處理來管理此類情況。

### 我可以從加密或受密碼保護的 PDF 中提取圖像嗎？
是的，只要您提供正確的密碼，Aspose.PDF for .NET 就可以開啟加密的 PDF 並擷取影像。

### 如何安裝 Aspose.PDF for .NET？
您可以從[Aspose.PDF for .NET 頁面](https://releases.aspose.com/pdf/net/)或在 Visual Studio 中使用 NuGet 安裝它。