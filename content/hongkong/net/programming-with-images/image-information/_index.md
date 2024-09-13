---
title: PDF 檔案中的影像訊息
linktitle: PDF 檔案中的影像訊息
second_title: Aspose.PDF for .NET API 參考
description: 透過我們全面的逐步指南，學習使用 Aspose.PDF for .NET 從 PDF 中提取影像資訊。
type: docs
weight: 160
url: /zh-hant/net/programming-with-images/image-information/
---
## 介紹

如今，PDF 文件無所不在，幾乎所有專業和個人文件都會在某個時候採用這種格式。無論是報告、手冊或電子書，了解如何以程式設計方式與這些文件進行互動都提供了無數的可能性。一個常見的需求是從 PDF 文件中提取圖像資訊。在本指南中，我們將深入探討如何使用 .NET 的 Aspose.PDF 庫來提取 PDF 文件中嵌入的圖像的關鍵細節。

## 先決條件

在我們開始討論編碼的細節之前，您需要滿足一些先決條件：

1. 開發環境：您需要設定一個.NET 開發環境。這可以是 Visual Studio 或任何其他 .NET 相容的 IDE。
2.  Aspose.PDF 庫：確保您有權存取 Aspose.PDF 庫。您可以從[阿斯普斯網站](https://releases.aspose.com/pdf/net/). 
3. 基本 C# 知識：熟悉 C# 和物件導向的程式設計概念將幫助您輕鬆學習本教學。
4. PDF 文件：準備一個範例 PDF 文檔，其中包含用於測試程式碼的圖像。 

## 導入包

要開始使用 Aspose.PDF 庫，您需要將必要的命名空間匯入 C# 檔案中。這是一個快速概述：

```csharp
using System.IO;
using Aspose.Pdf;
using System;
```

這些命名空間將使您能夠存取操作 PDF 文件和提取影像資料所需的類別和方法。

現在您已完成所有設置，是時候將其分解為可管理的步驟了。我們將編寫一個 C# 程式來載入 PDF 文檔，遍歷每個頁面，並提取文檔中每個圖像的尺寸和解析度。

## 步驟1：初始化文檔

在此步驟中，我們將使用 PDF 文件的路徑初始化 PDF 文件。你應該更換`"YOUR DOCUMENT DIRECTORY"`與您的 PDF 檔案所在的實際路徑。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//載入來源 PDF 文件
Document doc = new Document(dataDir + "ImageInformation.pdf");
```
我們創建一個`Document`從指定目錄載入 PDF 的物件。這將使我們能夠處理文件的內容。

## 步驟2：設定預設解析度並初始化資料結構

接下來，我們為圖像設定預設分辨率，這對於計算很有用。我們還將準備一個陣列來保存圖像名稱和一個堆疊來管理圖形狀態。

```csharp
//定義影像的預設分辨率
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
//定義將保存影像名稱的陣列清單對象
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```
這`defaultResolution`變數幫助我們正確計算影像的解析度。這`graphicsState`當我們遇到轉換運算子時，堆疊充當儲存文件當前圖形狀態的手段。

## 第三步：處理頁面上的每個算子

現在我們循環遍歷文檔第一頁上的所有運算符。這就是繁重的工作發生的地方。 

```csharp
foreach (Operator op in doc.Pages[1].Contents)
{
    //流程操作員...
}
```
PDF 檔案中的每個運算子都是一個命令，告訴渲染器如何管理圖形元素（包括圖像）。

## 步驟 4：處理 GSave/GRestore 運算子

在循環內，我們將處理圖形保存和恢復命令以追蹤對圖形狀態所做的更改。

```csharp
if (opSaveState != null) 
{
    //儲存之前的狀態
    graphicsState.Push(((Matrix)graphicsState.Peek()).Clone());
} 
else if (opRestoreState != null) 
{
    //恢復之前的狀態
    graphicsState.Pop();
}
```
`GSave`儲存目前圖形狀態，同時`GRestore`恢復上次儲存的狀態，讓我們在處理影像時恢復任何轉換。

## 第 5 步：管理轉換矩陣

接下來，我們在對影像應用變換時處理變換矩陣的串聯。

```csharp
else if (opCtm != null) 
{
    Matrix cm = new Matrix(
        (float)opCtm.Matrix.A,
        (float)opCtm.Matrix.B,
        (float)opCtm.Matrix.C,
        (float)opCtm.Matrix.D,
        (float)opCtm.Matrix.E,
        (float)opCtm.Matrix.F);
    
    ((Matrix)graphicsState.Peek()).Multiply(cm);
    continue;
}
```
當應用變換矩陣時，我們將其與儲存在圖形狀態中的當前矩陣相乘，以便我們可以追蹤應用於影像的任何縮放或平移。

## 第6步：提取影像訊息

最後，我們處理圖像的繪圖運算符並提取必要的信息，例如尺寸和解析度。

```csharp
else if (opDo != null) 
{
    //繪製物件的 Handle Do 運算符
    if (imageNames.Contains(opDo.Name)) 
    {
        Matrix lastCTM = (Matrix)graphicsState.Peek();
        XImage image = doc.Pages[1].Resources.Images[opDo.Name];
        double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
        double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
        double originalWidth = image.Width;
        double originalHeight = image.Height;
        
        double resHorizontal = originalWidth * defaultResolution / scaledWidth;
        double resVertical = originalHeight * defaultResolution / scaledHeight;
        
        //輸出訊息
        Console.Out.WriteLine(string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
                         opDo.Name, scaledWidth, scaledHeight, resHorizontal, resVertical));
    }
}
```
在這裡，我們檢查操作員是否負責繪製影像。如果是，我們取得相應的 XImage 對象，計算其縮放尺寸和分辨率，並列印必要的資訊。

## 結論

恭喜！您剛剛建立了一個如何使用 Aspose.PDF for .NET 從 PDF 文件中提取影像資訊的工作範例。對於需要分析或操作各種應用程式（例如報告、資料提取甚至自訂 PDF 檢視器）的 PDF 文件的開發人員來說，此功能非常有用。 


## 常見問題解答

### 什麼是 Aspose.PDF 函式庫？
Aspose.PDF 庫是一個強大的工具，用於在 .NET 應用程式中建立、操作和轉換 PDF 檔案。

### 我可以免費使用圖書館嗎？
是的，Aspose 提供免費試用。你可以下載它[這裡](https://releases.aspose.com/).

### 可以提取哪些類型的圖像格式？
該庫支援各種圖像格式，包括 JPEG、PNG 和 TIFF，只要它們嵌入在 PDF 中即可。

### Aspose 是否用於商業目的？
是的，您可以將 Aspose 產品用於商業用途。如需許可，請訪問[購買頁面](https://purchase.aspose.com/buy).

### 我如何獲得 Aspose 的支援？
您可以造訪支援論壇[這裡](https://forum.aspose.com/c/pdf/10).