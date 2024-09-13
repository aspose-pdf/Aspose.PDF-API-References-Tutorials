---
title: 布拉德利演算法
linktitle: 布拉德利演算法
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 中的 Bradley 演算法將 PDF 轉換為 TIFF。無縫轉換的逐步指南、先決條件和常見問題。
type: docs
weight: 30
url: /zh-hant/net/programming-with-images/bradley-algorithm/
---
## 介紹

使用 PDF 文件有時需要的不僅僅是閱讀或編輯它們，您可能需要將它們轉換為圖像。將 PDF 轉換為 TIFF 影像的強大方法是透過 Aspose.PDF for .NET 函式庫使用 Bradley 演算法。此方法可確保高品質的二進位影像，非常適合文件歸檔和其他專業用例。

本教學將引導您完成使用 Bradley 二值化演算法將 PDF 頁面轉換為 TIFF 影像的詳細且易於遵循的過程。 Aspose.PDF for .NET 簡化了此任務，使您能夠自動化和簡化文件工作流程。

## 先決條件

在我們深入研究程式碼之前，讓我們確保您已掌握所需的一切：

-  Aspose.PDF for .NET：您將需要該程式庫。從以下位置下載[這裡](https://releases.aspose.com/pdf/net/).
- Visual Studio（或任何 C# IDE）。
- C# 基礎知識。
- 有效的許可證或[臨時執照](https://purchase.aspose.com/temporary-license/)來自阿斯珀斯。

## 導入包

首先，確保將必要的命名空間匯入到您的專案中。這些程式庫將為您提供操作 PDF 文件、將其轉換為 TIFF 格式以及應用 Bradley 二值化演算法的工具。

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

讓我們將這個過程分解為幾個簡單的步驟，以確保您可以順利地進行。在本指南結束時，您將使用 Bradley 演算法成功將 PDF 頁面轉換為二進位 TIFF 影像。

## 步驟1：設定文檔目錄

第一步是指定 PDF 文件所在目錄的路徑。您還將定義將產生的 TIFF 影像的輸出路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // PDF 檔案的路徑
```

您可以在此處儲存來源 PDF 和轉換後的 TIFF 檔案。確保目錄設定正確，以便程式碼可以無錯誤地讀寫檔案。

## 第 2 步：開啟 PDF 文檔

現在路徑已設置，是時候打開要轉換的 PDF 文件了。 Aspose.PDF for .NET 可以輕鬆載入文件以進行進一步處理。

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

這裡，`PageToTIFF.pdf`是範例文件。您可以將其替換為您選擇的任何 PDF 文件。文檔物件現在保存 PDF 以供進一步操作。

## 步驟 3：定義影像的輸出路徑

接下來，您將指定產生的 TIFF 檔案的輸出路徑，包括標準 TIFF 和二進位化版本。

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

透過分離這些路徑，您將獲得一個用於標準 TIFF 轉換的文件，以及另一個用於應用 Bradley 演算法後的二值化影像的文件。

## 第 4 步：建立解析對象

將 PDF 轉換為 TIFF 時，解析度在決定影像品質方面起著重要作用。出於我們的目的，我們將其設定為 300 DPI 以確保高品質的輸出。

```csharp
Resolution resolution = new Resolution(300);
```

更高的 DPI 意味著更好的影像清晰度，尤其是在處理要列印或存檔的文件時。

## 步驟 5：設定 TIFF 設定

接下來，您需要配置 TIFF 影像的設定。在這裡，我們將使用 LZW 壓縮並將顏色深度設為 1bpp（每像素 1 位元）來獲得二值影像。

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
```

透過將深度設為 1bpp，我們為二進位輸出準備影像。選擇 LZW 壓縮是因為它可以有效地減少檔案大小而不損失品質。

## 第 6 步：建立 TIFF 設備

現在，您需要建立一個處理轉換的 TIFF 裝置。本設備使用先前定義的解析度和 TIFF 設定。

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

TIFF設備是此操作的核心。它根據您的預定義設定獲取 PDF 文件並將每個頁面轉換為 TIFF 影像。

## 步驟 7：將 PDF 頁面轉換為 TIFF

現在是處理 PDF 並將第一頁轉換為 TIFF 影像的時候了。這`Process`方法允許您轉換特定頁面或整個文件。在此範例中，我們正在轉換第一頁。

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

此方法完成後，您將在先前定義的位置儲存一個 TIFF 影像。

## 步驟 8：應用 Bradley 二值化演算法

現在魔術來了——布拉德利演算法！此演算法將灰階 TIFF 影像轉換為二值影像，針對文件辨識系統進行最佳化。

```csharp
using (FileStream inStream = new FileStream(outputImageFile, FileMode.Open))
{
    using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
    {
        tiffDevice.BinarizeBradley(inStream, outStream, 0.1);
    }
}
```

 BinarizeBradley 方法採用兩個檔案流（輸入和輸出）以及一個閾值（此處，`0.1`）決定二值化等級。執行後，您將擁有一個可供使用的完美二值化影像。

## 第9步：確認轉換成功

最後，讓使用者知道流程已成功是一個很好的做法。您可以透過簡單的控制台輸出來完成此操作。

```csharp
System.Console.WriteLine("Conversion using Bradley algorithm performed successfully!");
```

一旦列印出來，您就知道您的 PDF 頁面已成功轉換為二進位 TIFF 影像！

## 結論

給你了！您剛剛學習如何使用 Aspose.PDF for .NET 將 PDF 頁面轉換為 TIFF 影像並套用 Bradley 二值化演算法。此流程對於文件歸檔、光學字元辨識 (OCR) 和其他專業應用至關重要。憑藉高品質的解析度和高效的壓縮，您可以確保文件影像清晰且尺寸易於管理。

## 常見問題解答

### 什麼是布拉德利演算法？
Bradley 演算法是一種二值化技術，透過根據周圍環境確定每個像素的自適應閾值，將灰階影像轉換為二值（黑白）影像。

### 我可以使用此方法將多個 PDF 頁面轉換為 TIFF 嗎？
是的，您可以修改`Process`方法透過循環遍歷文件中的頁面來轉換所有頁面。

### 將 PDF 轉換為 TIFF 的最佳解析度是多少？
對於高品質影像，通常建議使用 300 DPI。但是，您可以根據需要調整該值。

### 顏色深度中的 1bpp 意味著什麼？
1bpp（每像素 1 位元）意味著影像將是黑白的，每個像素要么全黑，要么全白。

### Bradley演算法適合OCR嗎？
是的，Bradley 演算法經常用於 OCR 預處理，因為它可以增強掃描文件中文字的對比度。