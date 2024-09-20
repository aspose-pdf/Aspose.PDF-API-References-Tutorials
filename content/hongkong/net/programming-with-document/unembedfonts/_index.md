---
title: 取消嵌入字體並優化 PDF 文件
linktitle: 取消嵌入字體並優化 PDF 文件
second_title: Aspose.PDF for .NET API 參考
description: 在此逐步教學中，了解如何使用 Aspose.PDF for .NET 取消嵌入字體並優化 PDF 檔案。
type: docs
weight: 370
url: /zh-hant/net/programming-with-document/unembedfonts/
---
## 介紹

在數位時代，PDF 無所不在。無論您是共用報告、簡報或電子書，便攜式文件格式 (PDF) 都是保持文件完整性的首選。然而，隨著我們創建和共享越來越多的 PDF，文件大小會不斷膨脹，導致發送或儲存變得很麻煩。這就是 Aspose.PDF for .NET 發揮作用的地方，它提供了強大的工具來優化 PDF 檔案。在本教學中，我們將深入探討如何使用 Aspose.PDF for .NET 取消嵌入字體並優化 PDF 檔案。

## 先決條件

在我們深入討論細節之前，讓我們確保您已具備開始使用所需的一切：

1. Visual Studio：確保您的電腦上安裝了 Visual Studio。我們將使用它來編寫和運行 .NET 程式碼。
2.  Aspose.PDF for .NET：您需要下載並安裝 Aspose.PDF 庫。您可以從[下載連結](https://releases.aspose.com/pdf/net/).
3. C# 基礎知識：熟悉 C# 程式設計將幫助您理解我們將使用的程式碼片段。
4.  PDF 檔案：準備好要優化的 PDF 檔案。您可以使用任何 PDF，但為了演示，我們將其稱為`OptimizeDocument.pdf`.

## 導入包

首先，您需要在 C# 專案中匯入必要的套件。您可以這樣做：

1. 在 Visual Studio 中開啟您的專案。
2. 新增對 Aspose.PDF 的參考：在解決方案資源管理器中右鍵單擊您的項目，選擇“管理 NuGet 套件”，然後搜尋`Aspose.PDF`。安裝軟體包。

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

現在我們已經完成了所有設置，讓我們將優化過程分解為可管理的步驟。

## 第 1 步：設定您的文件目錄

首先，您需要定義文檔目錄的路徑。這是您的 PDF 檔案的儲存位置。操作方法如下：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`與您的 PDF 檔案所在的實際路徑。這一點至關重要，因為程式需要知道在哪裡可以找到您想要優化的 PDF。

## 第 2 步：開啟 PDF 文檔

現在我們已經設定了目錄，是時候開啟我們想要優化的 PDF 文件了。這是執行此操作的程式碼：

```csharp
//開啟文件
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

這行程式碼創建了一個新的`Document`對象，代表您的 PDF 檔案。確保檔案名稱與目錄中的檔案名稱相符。

## 第 3 步：設定優化選項

接下來，我們需要指定最佳化選項。在這種情況下，我們想要取消嵌入字體。設定方法如下：

```csharp
//設定取消嵌入字體選項
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    UnembedFonts = true
};
```

透過設定`UnembedFonts`到`true`，我們指示 Aspose.PDF 透過取消嵌入字體來優化 PDF。這可以顯著減小檔案大小，尤其是當 PDF 包含許多嵌入字體時。

## 步驟 4：最佳化 PDF 文件

設定好選項後，就可以優化 PDF 文件了。這是執行此操作的程式碼：

```csharp
Console.WriteLine("Start");
//使用 OptimizationOptions 優化 PDF 文檔
pdfDocument.OptimizeResources(optimizeOptions);
```

此程式碼片段調用`OptimizeResources`方法上的`pdfDocument`對象，應用我們先前定義的最佳化選項。您將在控制台中看到一條訊息，指示優化過程已開始。

## 步驟5：儲存更新後的文檔

優化PDF後，我們需要儲存更新後的文件。操作方法如下：

```csharp
//儲存更新的文檔
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
```

此程式碼將優化後的 PDF 儲存為`OptimizeDocument_out.pdf`在同一目錄中。如果您願意，可以選擇不同的名稱，但保持相似性有助於識別原始版本和優化版本。

## 第 6 步：比較檔案大小

最後，檢查您節省了多少空間總是好的。以下是比較原始檔案大小和最佳化檔案大小的方法：

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

此程式碼會擷取原始 PDF 和優化 PDF 的檔案大小並將其列印到控制台。看到檔案大小減少了多少，這是一個令人滿足的時刻！

## 結論

現在你就擁有了！您已成功使用 Aspose.PDF for .NET 取消嵌入字體並優化 PDF 檔案。此過程不僅有助於減小檔案大小，還可以增強 PDF 文件的效能。無論您是透過電子郵件共用檔案還是將它們儲存在雲端中，較小的檔案大小都會帶來很大的不同。

## 常見問題解答

### 什麼是 Aspose.PDF for .NET？
Aspose.PDF for .NET 是一個功能強大的程式庫，可讓開發人員以程式設計方式建立、操作和最佳化 PDF 文件。

### 我可以免費使用 Aspose.PDF 嗎？
是的，Aspose 提供免費試用版。您可以從以下位置下載：[這裡](https://releases.aspose.com/).

### 如何獲得 Aspose.PDF 支援？
您可以透過以下方式獲得支持[Aspose論壇](https://forum.aspose.com/c/pdf/10).

### 我可以對 PDF 執行哪些類型的最佳化？
您可以取消嵌入字體、壓縮圖像、刪除未使用的物件等來優化 PDF 檔案。

### 哪裡可以購買 Aspose.PDF for .NET？
您可以從以下位置購買許可證[Aspose購買頁面](https://purchase.aspose.com/buy).