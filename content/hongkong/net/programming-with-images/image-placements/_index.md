---
title: 圖片展示位置
linktitle: 圖片展示位置
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 擷取和操作 PDF 文件中的影像位置。包含範例和程式碼片段的逐步指南。
type: docs
weight: 170
url: /zh-hant/net/programming-with-images/image-placements/
---
## 介紹

處理 PDF 文件中的圖像可能很棘手，但使用 Aspose.PDF for .NET，您可以輕鬆操作和提取圖像屬性，而無需費力。無論您是想取得影像尺寸、擷取影像，還是檢索解析度等其他屬性，Aspose.PDF 都能提供您所需的工具。本教學將逐步指導您如何使用 Aspose.PDF for .NET 擷取 PDF 文件中的影像位置。我們將涵蓋從導入包到檢索影像屬性（如寬度、高度和解析度）的所有內容。

## 先決條件

在我們開始學習本教程之前，您需要先做好一些準備。這是一個快速清單：

1.  Aspose.PDF for .NET：請確定您已安裝 Aspose.PDF for .NET 程式庫。你可以下載它[這裡](https://releases.aspose.com/pdf/net/).
2. 開發環境：您需要在電腦上安裝 Visual Studio 或任何其他支援 .NET 的 IDE。
3. PDF 文件：準備好包含影像的範例 PDF 文件。對於本例，我們將使用一個名為`ImagePlacement.pdf`.
4. 基本 C# 知識：雖然本指南適合初學者，但 C# 基本知識將幫助您更好地理解程式碼片段。

## 導入包

在我們深入了解程式碼的實質之前，您需要做的第一件事是匯入必要的名稱空間。這些套件對於在 Aspose.PDF for .NET 中處理 PDF 文件和影像操作至關重要。

```csharp
using System.IO;
using Aspose.Pdf;
using System;
using System.Drawing;
```

這些包可讓您處理 PDF（`Aspose.Pdf`），操縱影像位置（`Aspose.Pdf.ImagePlacement`），並處理影像流和圖形（`System.Drawing`和`System.IO`）。

現在我們已經具備了先決條件和軟體包，讓我們以簡單易懂的指南來分解本教程的每個部分。

## 第 1 步：載入 PDF 文檔

第一步是將 PDF 文件載入到您的專案中。這將成為處理 PDF 文件內的圖像的基礎。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "ImagePlacement.pdf");
```

在此步驟中，我們使用以下命令定義 PDF 文件的檔案路徑`dataDir`然後建立一個新實例`Aspose.Pdf.Document`班級。這允許我們將 PDF 文件載入到我們的程式中。很簡單，對吧？就像打開一本書開始閱讀一樣，我們現在準備探索裡面的內容。

## 第 2 步：初始化影像放置吸收器

為了提取影像，我們需要一種稱為「影像放置吸收器」的東西。把它想像成一個吸收特定頁面上所有圖像資訊的工具。

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
```

在這裡，我們建立一個實例`ImagePlacementAbsorber`。該物件將收集並儲存有關特定 PDF 頁面上所有影像位置的資訊。想像一下，這就像用放大鏡掃描頁面並識別上面的所有圖像！

## 步驟 3： 接受第一頁的吸收器

接下來，我們要告訴吸收器要掃描 PDF 的哪一頁。對於此範例，我們將重點關注第一頁。

```csharp
doc.Pages[1].Accept(abs);
```

這`Accept`方法掃描 PDF 文件第一頁中的任何影像並將結果儲存在`ImagePlacementAbsorber`。這就像告訴放大鏡去哪裡尋找影像。

## 第 4 步：循環遍歷每個影像位置

現在我們已經掃描了頁面，我們需要循環瀏覽頁面上找到的每個圖像並檢索其屬性。

```csharp
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
    Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
    Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
    Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
    Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
    Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
    Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
}
```

該循環遍歷頁面上找到的每個圖像。我們列印出影像的寬度、高度、左下 x (LLX)、左下 y (LLY) 和解析度（水平和垂直）。這些詳細資訊可協助您了解 PDF 中每個影像的大小和位置。

## 步驟5：提取具有可見尺寸的影像

收集有關圖像的資訊後，您可能想要提取實際圖像及其尺寸。以下是您可以如何做到這一點。

```csharp
Bitmap scaledImage;
using (MemoryStream imageStream = new MemoryStream())
{
    imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
    Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);
    scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
}
```

此程式碼片段從 PDF 中檢索影像，並將其縮放至實際尺寸（如`ImagePlacement`目的。透過將圖像保存在記憶體流中並對其進行縮放，您可以確保提取的圖像保持其在 PDF 中顯示的精確大小。

## 結論

一旦您一步步分解，使用 Aspose.PDF for .NET 從 PDF 文件中提取影像位置就非常簡單了。我們涵蓋了從加載 PDF 到檢索圖像屬性以及提取圖像及其實際尺寸的所有內容。 Aspose.PDF 讓處理 PDF 和操作內容變得異常簡單，讓您能夠有效率地處理影像、文字等。

## 常見問題解答

### 我可以從 PDF 的特定頁面中提取圖像嗎？  
是的，透過在使用時指定頁碼`Accept`方法，您可以專注於任何特定頁面。

### 支援提取哪些圖像格式？  
Aspose.PDF支援多種格式，包括PNG、JPEG、BMP等。

### 是否可以操作提取的影像？  
絕對地！提取後，您可以使用`System.Drawing`命名空間來操作影像。

### 我可以從受密碼保護的 PDF 中提取圖像嗎？  
是的，您可以，但您需要在提取圖像之前使用適當的憑證解鎖 PDF。

### Aspose.PDF for .NET 是否適用於所有 .NET 框架？  
是的，它支援 .NET Framework、.NET Core 和 .NET 5 及更高版本。