---
title: 搜尋並取得 PDF 文件中的圖像
linktitle: 搜尋並取得 PDF 文件中的圖像
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 輕鬆從 PDF 檔案中擷取影像。請按照此逐步指南來增強您的 PDF 處理技能。
type: docs
weight: 260
url: /zh-hant/net/programming-with-images/search-and-get-images/
---
## 介紹

您是否正在尋找使用 Aspose.PDF for .NET 從 PDF 文件中提取圖像的簡單方法？您來對地方了！在本文中，我們將深入探討如何有效搜尋和檢索 PDF 文件中嵌入的圖像的細節。無論您是經驗豐富的開發人員還是剛剛涉足 PDF 操作領域，本指南都將引導您逐步完成整個過程。

## 先決條件

在我們深入了解程式碼的細節之前，您需要檢查一下清單中的一些先決條件。 

### .NET框架

確保您的電腦上安裝了 .NET Framework。 Aspose.PDF for .NET 與各種版本相容，但最好使用最新的穩定版本以享受所有最新功能和改進。

### Aspose.PDF庫

您需要存取 Aspose.PDF 庫。如果還沒有，您可以透過以下連結下載：[下載 .NET 版 Aspose.PDF](https://releases.aspose.com/pdf/net/) 。此外，您還可以探索他們的[一個月免費試用](https://releases.aspose.com/)無需任何成本即可啟動您的專案。

### 開發環境

應設定合適的開發環境（例如 Visual Studio 或您喜歡的任何 IDE）來無縫編寫和執行程式碼。

## 導入包

若要使用 Aspose.PDF for .NET，您首先需要將適當的命名空間匯入到您的專案中。您需要執行以下操作：

```csharp
using System.IO;
using Aspose.Pdf;
using System;
```

在操作 PDF 文件時，每個套件都有特定的用途。這`Aspose.Pdf`命名空間是操作的基石，而其他兩個有助於處理 PDF 中的圖像和文字。

## 第 1 步：設定文檔路徑

首先，您需要定義 PDF 檔案所在的路徑。這段程式碼對此進行了設定：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

將「您的文件目錄」替換為包含 PDF 檔案的目錄的實際路徑，例如，`C:\Documents\`.

## 第 2 步：開啟 PDF 文檔

接下來，您需要將 PDF 文件載入到您的應用程式中。這是透過創建一個新的`Document`具有您剛剛指定的檔案路徑的實例：

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SearchAndGetImages.pdf");
```

## 第 3 步：建立 ImagePlacementAbsorber

要在 PDF 中搜尋圖像，您需要`ImagePlacementAbsorber`目的。此類有助於在提取過程中從 PDF 中吸收圖像：

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
```

## 第 4 步：接受所有頁面的吸收器

這一步至關重要，因為它告訴`Document`將圖像吸收器套用到所有頁面。它確保放置在文件中任何位置的任何圖像都將被識別：

```csharp
doc.Pages.Accept(abs);
```

## 第 5 步：循環遍歷影像位置

現在您已經吸收了這些圖像，是時候深入研究它們了。您將循環瀏覽從 PDF 中提取的每個圖像位置：

```csharp
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
    //取得影像屬性的進一步步驟
}
```

## 第 6 步：提取圖像屬性

在循環內，您可以開始檢索每個影像的有價值的屬性。使用`imagePlacement`對象，您可以存取尺寸和解析度：

```csharp
XImage image = imagePlacement.Image; //取得影像

Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
```

## 結論

現在你就擁有了！透過執行這些步驟，您可以使用 Aspose.PDF for .NET 有效率地搜尋和檢索 PDF 檔案中的影像。只需幾行程式碼，您就可以提取有價值的圖像及其屬性，為應用程式中的許多可能性打開大門。

## 常見問題解答

### Aspose.PDF 庫可以免費使用嗎？  
Aspose.PDF for .NET 是一個付費函式庫，但您可以下載一個月的免費試用版。

### 我可以從受密碼保護的 PDF 檔案中提取圖像嗎？  
可以，但開啟文件時需要提供密碼。

### 可以從 PDF 中提取哪些類型的圖像？  
可以提取所有嵌入的圖像，無論其格式如何（JPEG、PNG 等）。

### 我可以提取的圖像數量有限制嗎？  
沒有硬性限制；這取決於 PDF 文件本身。

### 我可以將提取的映像儲存到磁碟嗎？  
是的，您可以使用以下命令將映像儲存到磁碟`XImage`程式碼中的物件。