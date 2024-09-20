---
title: 在 PDF 檔案中建立縮圖
linktitle: 在 PDF 檔案中建立縮圖
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 輕鬆產生 PDF 檔案中每個頁面的縮圖。增強您的文件預覽體驗。
type: docs
weight: 100
url: /zh-hant/net/programming-with-images/create-thumbnail-images/
---
## 介紹

對於希望在不開啟整個文件的情況下快速預覽文件的任何人來說，為 PDF 中的每個頁面建立縮圖非常有用。無論您是要建立文件管理系統還是只是想簡化 PDF 集合中的導航，此過程都可以節省您的時間並增強您的使用者體驗。今天，我們將介紹如何使用 Aspose.PDF for .NET 自動為 PDF 檔案中的每個頁面產生縮圖。這不僅涉及編碼；還涉及編碼。它旨在為您提供簡化工作流程並提高可訪問性的工具。

## 先決條件

在深入研究程式碼之前，您需要注意一些先決條件以確保順利設定：

1. C# 或 .NET 的基本知識：熟悉 C# 程式設計將有助於您在學習過程中更好地理解程式碼。
2. 已安裝 Visual Studio：您需要一個 IDE 來編寫和執行程式碼。 Visual Studio 是 .NET 開發的熱門選擇。
3. Aspose.PDF for .NET 函式庫：請確定您已安裝 Aspose.PDF 函式庫。您可以從[Aspose.PDF 文檔](https://reference.aspose.com/pdf/net/).
4. PDF 檔案：在指定的工作目錄中準備一些 PDF 檔案以進行測試。

想立即開始嗎？偉大的！我們首先導入必要的套件。

## 導入包

要利用 Aspose.PDF 功能，您需要在 C# 檔案的頂部包含相關的命名空間。操作方法如下：

```csharp
using Aspose.Pdf.Devices;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

包含這些命名空間可確保您能夠存取 Aspose 中我們將執行的操作所需的所有類別和方法。

## 第 1 步：設定您的文件目錄

我們流程的第一步是指定儲存所有 PDF 檔案的文檔目錄的路徑。您需要告訴程式在哪裡尋找這些 PDF。 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; //替換為你的實際目錄路徑
```

代替`"YOUR DOCUMENT DIRECTORY"`以及 PDF 檔案所在的路徑。此步驟至關重要，因為如果沒有正確的目錄，您的程式將找不到它需要處理的 PDF。

## 第 2 步：檢索 PDF 檔案名

接下來，您需要取得目錄中所有 PDF 檔案的名稱。此步驟有助於稍後迭代每個檔案。 

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
```

在這裡，我們使用`Directory.GetFiles`僅過濾和檢索 PDF 文件的方法。這`*.pdf`通配符確保我們抓取指定目錄中的每個 PDF。 

## 第 3 步：遍歷每個 PDF 文件

現在我們將循環遍歷剛剛檢索到的每個文件。對於每個 PDF，我們將開啟它並為其頁面建立縮圖。 

```csharp
for (int counter = 0; counter < fileEntries.Length; counter++)
{
    Document pdfDocument = new Document(fileEntries[counter]);
}
```

在這個循環中，`counter`追蹤我們正在處理的文件。這`Document`類別用於開啟每個 PDF 檔案。您將一次處理每個 PDF，以從其頁面建立縮圖。

## 步驟 4：為每個頁面建立縮圖

我們將為 PDF 中的每個頁面建立一個縮圖。讓我們一步步分解這部分。

### 步驟 4.1：為每個縮圖初始化 FileStream

在循環中，我們需要設定一個用於保存縮圖的流。

```csharp
using (FileStream imageStream = new FileStream(dataDir + "\\Thumbanils" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
{
```

在這裡，我們使用以下命令為每個縮圖建立一個新的 JPG 文件`FileStream`。檔案名稱包含計數器，因此每個縮圖都有一個唯一的名稱。

### 步驟 4.2：定義分辨率

接下來，我們需要定義縮圖的解析度。解析度越高，影像越清晰，但也會增加檔案大小。

```csharp
Resolution resolution = new Resolution(300);
```

300 DPI（每英吋點數）的解析度是高品質影像的標準。請根據您的需求隨意調整該值。

### 步驟 4.3：設定 JpegDevice

現在，我們將設定`JpegDevice`它將用於將 PDF 頁面轉換為圖像。

```csharp
JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
```

在這裡，我們指定縮圖的尺寸和品質。在本例中，我們將尺寸設為 45x59 像素，但可以根據應用程式的需要調整這些值。

### 步驟 4.4：處理每個頁面

一切就緒後，我們現在可以處理 PDF 的每一頁並將生成的縮圖保存到我們的流中。

```csharp
jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
```

該行從 PDF 中獲取特定頁面並將其處理為 JPEG 格式，然後將其直接提供給`imageStream`我們將在其中儲存縮圖。

### 步驟 4.5：關閉流

最後，處理完每個頁面後，我們需要關閉流以釋放資源。

```csharp
imageStream.Close();
```

關閉流對於防止記憶體洩漏並確保所有變更都正確寫入磁碟至關重要。

## 結論

為 PDF 文件建立縮圖可以顯著改善使用者與文件的互動方式。透過 Aspose.PDF for .NET，可以簡單且有效率地以程式方式產生這些縮圖，從而節省您的時間和精力。遵循本指南，您將能夠將 PDF 縮圖合併到您的專案中！

## 常見問題解答

### 什麼是Aspose.PDF？  
Aspose.PDF 是一個功能強大的庫，用於在 .NET 應用程式中處理 PDF 文檔，允許建立、編輯和轉換。

### Aspose.PDF 庫是免費的嗎？  
 Aspose.PDF 是一個商業產品，但您可以從他們的網站下載免費試用版[網站](https://releases.aspose.com/).

### 我可以自訂縮圖尺寸嗎？  
是的，您可以變更 JpegDevice 建構函式中的寬度和高度參數來調整縮圖大小。

### 轉換大型 PDF 時是否有任何效能考量？  
是的，較大的文件可能需要更長的時間來處理，這取決於解析度和頁數；優化這些參數有助於提高效能。

### 我可以在哪裡找到更多資源和支援？  
您可以在以下位置找到更多資源和社區支持[Aspose 論壇](https://forum.aspose.com/c/pdf/10).