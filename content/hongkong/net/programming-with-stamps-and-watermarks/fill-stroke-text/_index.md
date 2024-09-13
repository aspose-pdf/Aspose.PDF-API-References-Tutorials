---
title: 在 PDF 檔案中填入描邊文本
linktitle: 在 PDF 檔案中填入描邊文本
second_title: Aspose.PDF for .NET API 參考
description: 透過包含實際範例的逐步指南，了解如何使用 Aspose.PDF for .NET 輕鬆填入 PDF 檔案中的筆畫文字。
type: docs
weight: 90
url: /zh-hant/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
## 介紹

您是否曾經想要修改 PDF 文件以使其脫穎而出？也許您需要添加醒目的水印或粗體印章，使重要文件明確屬於您。使用 Aspose.PDF for .NET，您可以輕鬆地在 PDF 文件中填充描邊文本，添加引人注目的藝術風格。在今天的教學中，我們將演練使用 C# 在 PDF 中填入筆畫文字的過程。最後，您將牢牢掌握如何像專業人士一樣操作 PDF 文件。

## 先決條件

在我們深入編碼之前，您需要準備好一些東西才能使本教程變得輕而易舉：

1. Visual Studio：確保您的電腦上安裝了 Visual Studio，因為我們將編寫 C# 程式碼。
2.  Aspose.PDF 庫：請確定您已下載 Aspose.PDF for .NET 庫。你可以抓住它[這裡](https://releases.aspose.com/pdf/net/).
3. C# 基礎知識：熟悉 C# 程式設計將有助於您更輕鬆地理解本教學。
4. 範例 PDF 檔案：您需要一個範例 PDF 檔案（`input.pdf`）用於測試目的。您可以建立一個簡單的 PDF 或使用您擁有的任何現有 PDF。

現在我們已完成所有操作，讓我們深入了解在 PDF 文件中填充筆畫文字的具體細節。

## 導入包

首先，我們需要導入必要的套件。以下是我們專案的基本導入的簡要概述：

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

這些套件將使我們能夠使用 Aspose.PDF 庫的強大功能。

讓我們將主要任務分解為清晰的步驟。透過執行以下步驟，您可以輕鬆地將筆劃文字填入 PDF 檔案中。 

## 第 1 步：設定您的環境

首先，請確保在 Visual Studio 專案中正確設定所有內容。建立一個新項目或選擇現有項目。如果您需要協助，請按以下步驟操作：

1. 打開視覺工作室。
2. 建立一個新的 C# 專案（例如，控制台應用程式）。
3. 右鍵點選「解決方案資源管理器」中的項目，選擇「管理 NuGet 套件」。
4. 搜尋`Aspose.PDF`並安裝它。

## 第 2 步：定義您的文件目錄

每個旅程都需要一個起點，在我們的例子中，它是輸入和輸出檔案所在的文件目錄。 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`輸入 PDF 檔案所在的實際路徑。 

## 第 3 步：建立 TextState 對象

在此步驟中，您開始定義要新增的文字的屬性。 

```csharp
TextState ts = new TextState();
```

這`TextState`物件將保存筆畫文字的樣式選項。

## 第 4 步：設定描邊顏色

接下來，您需要定義文字筆畫的顏色。 

```csharp
ts.StrokingColor = Color.Gray;
```

在此程式碼中，我們對筆劃使用灰色。請隨意更改顏色以滿足您的需求！

## 步驟5：配置渲染模式

為了確保文字按預期顯示，請設定渲染模式：

```csharp
ts.RenderingMode = TextRenderingMode.StrokeText;
```

這指示 Aspose 庫我們正在處理筆畫文字。

## 第 6 步：載入輸入的 PDF 文檔

現在是時候載入您要修改的 PDF 檔案了。 

```csharp
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

確保您輸入的 PDF (`input.pdf`位於前面步驟中定義的文檔目錄中。

## 第7步：建立圖章對象

接下來，建立一個印章來保存您的筆劃文字。 

```csharp
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
```

此圖章將用於將您的文字覆蓋在 PDF 上。

## 第 8 步：定義要標記的文本

您需要指定要新增到 PDF 的文字：

```csharp
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));
```

在這裡，「PAID IN FULL」是我們新增的文字及其樣式屬性。根據您的要求自訂它！

## 第9步：綁定文字狀態

現在，綁定`TextState`您之前對圖章進行了定義。 

```csharp
stamp.BindTextState(ts);
```

此步驟將所有樣式（例如顏色和渲染模式）套用至文字。

## 第10步：設定圖章的位置

確定您的圖章將出現在 PDF 中的位置：

```csharp
stamp.SetOrigin(100, 100);
```

論據`(100, 100)`表示文本原點的 X 和 Y 座標（以磅為單位）。調整這些值以完美放置文字！

## 步驟 11：配置不透明度和旋轉

您可以在此處調整文字的外觀：

```csharp
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
```

在本例中，不透明度值和 45 度的旋轉角度為您的文字添加了獨特的風格。請隨意修改這些設定以獲得不同的效果。

## 第 12 步：將圖章新增至 PDF

這是關鍵的一步，我們最終將包含筆畫文本的圖章添加到 PDF 中：

```csharp
fileStamp.AddStamp(stamp);
```

就這樣，您的文字就可以發表聲明了！

## 步驟 13：儲存並關閉文檔

最後，儲存您的變更並確保所有內容都已正確清理。 

```csharp
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

您新修改的包含筆畫文字的 PDF 檔案將另存為`output_out.pdf`在您的文件目錄中。 

## 結論

現在你就得到它了！遵循這些簡單的步驟，您可以使用 Aspose.PDF for .NET 輕鬆填入 PDF 檔案中的描邊文字。無論是商業文件還是個人項目，此技術都可以讓您為 PDF 添加獨特的風格，使其在任何紙張中脫穎而出。

## 常見問題解答

### 什麼是 Aspose.PDF for .NET？
Aspose.PDF for .NET 是一個函式庫，可讓開發人員以程式設計方式建立、操作和轉換 PDF 檔案。

### 我可以免費使用 Aspose.PDF 嗎？
是的，Aspose 提供免費試用。你可以得到它[這裡](https://releases.aspose.com/).

### 我需要支付許可證費用嗎？
雖然該庫可以免費試用，但也可以在以下位置購買臨時許可證：[這個連結](https://purchase.aspose.com/temporary-license/).

### 我在哪裡可以找到文件？
您可以存取完整的文檔[這裡](https://reference.aspose.com/pdf/net/).

### 如果我遇到問題，可以獲得支援嗎？
絕對地！您可以在 Aspose 論壇上獲得支持[這裡](https://forum.aspose.com/c/pdf/10).