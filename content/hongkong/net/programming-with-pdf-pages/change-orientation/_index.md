---
title: 改變方向
linktitle: 改變方向
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 變更 PDF 頁面方向的逐步指南。易於在您的專案中遵循和實施。
type: docs
weight: 10
url: /zh-hant/net/programming-with-pdf-pages/change-orientation/
---
## 介紹

您是否曾經發現自己在處理頁面方向不正確的 PDF 文件時遇到困難？也許您正在處理掃描或創建不正確的文檔，並且頁面需要旋轉才能有意義。對我們來說幸運的是，Aspose.PDF for .NET 提供了一種簡單、強大的方法來以任何可以想像的方式操作 PDF 文件，包括更改頁面的方向。無論您想從縱向切換到橫向，還是反之亦然，本指南都會逐步引導您完成整個過程。

因此，如果您準備好深入研究並輕鬆旋轉這些 PDF 頁面，那麼讓我們開始吧！

## 先決條件

在詳細介紹如何更改 PDF 中的頁面方向之前，我們先快速介紹一下您需要具備的條件：

-  Aspose.PDF for .NET：請確定您已經安裝了 Aspose.PDF for .NET 程式庫。如果你還沒有，你可以[在這裡下載](https://releases.aspose.com/pdf/net/).
- .NET 開發環境：您可以使用 Visual Studio、JetBrains Rider 或任何首選 IDE 來處理 .NET。
- C# 基礎知識：雖然本指南很簡單，但對 C# 的一些基本了解將使它更容易遵循。
- PDF 檔案：下面的範例假設您有一個包含多個頁面的 PDF 檔案。如果您手邊沒有 PDF，請建立或下載一個範例 PDF 來使用。

另外，如果您剛開始，您可以嘗試使用 Aspose.PDF[免費臨時許可證](https://purchase.aspose.com/temporary-license/)在決定之前[購買完整版](https://purchase.aspose.com/buy).

## 導入命名空間

在操作 PDF 中的頁面方向之前，您需要在 C# 專案中匯入必要的命名空間。確保您具備以下條件：

```csharp
using System.IO;
using Aspose.Pdf;
```

導入後，讓我們進入教程的主要部分。

## 第 1 步：載入 PDF 文檔

我們需要做的第一件事是載入您要修改的 PDF 檔案。您可以使用`Document`Aspose.PDF 命名空間中的類別來開啟 PDF。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
```

此行從您指定的目錄載入 PDF。確保更換`"YOUR DOCUMENT DIRECTORY"`與文件的實際路徑。這`"input.pdf"`是您要更改方向的 PDF。

## 第 2 步：循環瀏覽每一頁

現在我們已經加載了文檔，讓我們循環瀏覽 PDF 中的每個頁面。我們將使用一個`foreach`循環遍歷每個頁面，使我們能夠將方向變更應用於所有頁面。

```csharp
foreach (Page page in doc.Pages)
{
    //操縱每個頁面
}
```

此循環將遍歷文檔中的所有頁面。

## 第三步：獲取頁面的MediaBox

 PDF 中的每個頁面都有一個`MediaBox`定義頁面的邊界。我們需要訪問它來確定當前方向並修改它。

```csharp
Aspose.Pdf.Rectangle r = page.MediaBox;
```

這`MediaBox`為我們提供頁面的尺寸，例如寬度、高度和位置。

## 第四步：交換寬度和高度

要將頁面方向從縱向變更為橫向或將橫向變更為縱向，我們只需交換寬度和高度值即可。此步驟將調整頁面的尺寸。

```csharp
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
```

此程式碼交換高度和寬度並重新定位左下角（`LLY`）以便旋轉後內容能夠整齊地貼合。

## 第 5 步：更新 MediaBox 和 CropBox

現在我們有了新的高度和寬度，讓我們將變更應用到頁面的`MediaBox`和`CropBox` 。這`CropBox`如果原始文件只有一套，則這一點至關重要，以確保整個頁面正確顯示。

```csharp
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
```

此步驟根據我們剛剛計算的新尺寸調整頁面大小。

## 第 6 步：旋轉頁面

最後我們設定頁面的旋轉角度。 Aspose.PDF 讓這變得超級簡單。我們可以將頁面旋轉 90 度，從縱向變成橫向，或反之亦然。

```csharp
page.Rotate = Rotation.on90;
```

此程式碼將頁面旋轉 90 度，將其翻轉到所需的方向。

## 第 7 步：儲存輸出 PDF

將方向變更套用到所有頁面後，我們將修改後的文件儲存到新文件中。 

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);
```

確保提供新的檔案名稱（在本例中，`ChangeOrientation_out.pdf`) 保存輸出。這樣，您就不會覆蓋原始文件。

### 結論

現在你就得到它了！使用 Aspose.PDF for .NET 變更 PDF 檔案的頁面方向非常簡單，只需載入文件、循環瀏覽頁面、調整 MediaBox 並儲存更新的檔案。無論您是在處理掃描品質不佳的文檔，還是需要旋轉頁面以滿足您的格式設定需求，本逐步指南都可以滿足您的需求。

## 常見問題解答

### 我可以旋轉 PDF 中的特定頁面而不是所有頁面嗎？  
是的，您可以修改循環以使用索引定位特定頁面，而不是循環遍歷所有頁面。

### 什麼是`MediaBox`?  
這`MediaBox`定義 PDF 檔案中頁面的大小和形狀。這是放置頁面內容的地方。

### Aspose.PDF for .NET 是否可以與其他文件格式一起使用？  
是的，Aspose.PDF 可以處理多種檔案格式，如 HTML、XML、XPS 等。

### 有沒有適用於 .NET 的 Aspose.PDF 免費版本？  
是的，您可以開始使用[免費試用](https://releases.aspose.com/)或請求[臨時執照](https://purchase.aspose.com/temporary-license/).

### 儲存後我可以撤銷更改嗎？  
儲存文件後，所做的變更將是永久性的。請務必處理原始文件的副本或保留原始文件的備份。