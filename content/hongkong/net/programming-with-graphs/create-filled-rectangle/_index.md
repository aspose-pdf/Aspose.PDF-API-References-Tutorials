---
title: 建立填滿矩形
linktitle: 建立填滿矩形
second_title: Aspose.PDF for .NET API 參考
description: 透過此逐步教學，了解如何使用 Aspose.PDF for .NET 在 PDF 中建立填滿矩形。非常適合各個層級的開發人員。
type: docs
weight: 50
url: /zh-hant/net/programming-with-graphs/create-filled-rectangle/
---
## 介紹

您是否曾經想過以程式設計方式建立具有視覺吸引力的 PDF？如果是這樣，那麼您來對地方了！在本教學中，我們將深入了解 Aspose.PDF for .NET 的世界，這是一個功能強大的程式庫，可讓您輕鬆操作 PDF 文件。今天，我們將重點放在在 PDF 文件中建立填充矩形。無論您是經驗豐富的開發人員還是新手，本指南都將以友好且引人入勝的方式引導您完成每個步驟。所以，拿起你的編碼帽子，讓我們開始吧！

## 先決條件

在我們開始編寫程式碼之前，您需要做好以下幾件事：

1. Visual Studio：確保您的電腦上安裝了 Visual Studio。它是用於 .NET 開發的出色 IDE。
2.  Aspose.PDF for .NET：您需要下載並安裝 Aspose.PDF 庫。你可以找到它[這裡](https://releases.aspose.com/pdf/net/).
3. C# 基礎知識：稍微熟悉一下 C# 程式設計將有助於您更好地理解程式碼片段。

## 導入包

首先，您需要在 C# 專案中匯入必要的套件。您可以這樣做：

### 建立一個新項目

開啟 Visual Studio 並建立一個新的 C# 專案。為了簡單起見，您可以選擇控制台應用程式。

### 新增 Aspose.PDF 參考

1. 在解決方案資源管理器中以滑鼠右鍵按一下您的專案。
2. 選擇“管理 NuGet 套件”。
3. 搜尋“Aspose.PDF”並安裝最新版本。

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

現在我們已經完成了所有設置，讓我們深入研究程式碼！

## 第 1 步：設定您的文件目錄

首先，您需要指定 PDF 的儲存路徑。這很重要，因為它告訴程式在哪裡建立文件。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`與您電腦上要儲存 PDF 的實際路徑。

## 步驟2：建立文檔實例

接下來，我們將建立一個實例`Document`班級。此類代表您將使用的 PDF 文件。

```csharp
//建立文件實例
Document doc = new Document();
```

此行初始化一個我們可以操作的新 PDF 文件。

## 步驟 3：新增頁面

現在，讓我們為文件新增一個頁面。每個 PDF 至少需要一頁，對吧？

```csharp
//將頁面新增至 PDF 檔案的頁面集合
Page page = doc.Pages.Add();
```

此程式碼會為文件新增一個頁面，允許我們在其上繪製形狀。

## 第 4 步：建立圖形實例

要繪製形狀，我們需要建立一個`Graph`實例。將圖表視為畫布，您可以在其中繪製各種形狀。

```csharp
//建立圖實例
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100.0, 400.0);
```

在這裡，我們建立一個寬度為 100、高度為 400 的圖表。

## 第 5 步：將圖表新增至頁面

現在我們有了圖表，讓我們將其添加到我們之前創建的頁面中。

```csharp
//將圖形物件加入到頁面實例的段落集合中
page.Paragraphs.Add(graph);
```

這條線將圖形附加到頁面上，準備好繪製。

## 第6步：建立一個矩形實例

接下來，我們將建立一個要填滿顏色的矩形。

```csharp
//建立矩形實例
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
```

在此程式碼中，我們定義矩形的位置和大小。這些參數表示 x 和 y 座標、寬度和高度。

## 第7步：指定填滿顏色

現在，讓我們為矩形選擇一種顏色。在本例中，我們將其填充為紅色。

```csharp
//指定 Graph 物件的填滿顏色
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

該行將矩形的填滿顏色設定為紅色。你可以選擇任何你喜歡的顏色！

## 第 8 步：將矩形加入圖表中

矩形準備好後，就可以將其新增至圖表了。

```csharp
//將矩形物件新增至圖形物件的形狀集合中
graph.Shapes.Add(rect);
```

此程式碼將矩形新增到圖形中，使其成為我們繪圖的一部分。

## 第9步：儲存PDF文檔

最後，我們需要將文檔儲存到指定的目錄中。

```csharp
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
//儲存 PDF 文件
doc.Save(dataDir);
```

此程式碼保存 PDF 文件，名稱為`CreateFilledRectangle_out.pdf`在您之前指定的目錄中。

## 第10步：確認訊息

為了讓我們知道一切順利，我們可以列印一條確認訊息。

```csharp
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);
```

此行將在控制台中輸出一條訊息，確認填充矩形已成功建立。

## 結論

現在你就擁有了！您已使用 Aspose.PDF for .NET 在 PDF 文件中成功建立了填滿矩形。這個強大的函式庫為 PDF 操作開闢了一個可能性的世界，讓您以程式設計方式建立令人驚嘆的文件。無論您是產生報表、發票或任何其他類型的 PDF，Aspose.PDF 都能滿足您的需求。

## 常見問題解答

### 什麼是 Aspose.PDF for .NET？
Aspose.PDF for .NET 是一個函式庫，可讓開發人員以程式設計方式建立、操作和轉換 PDF 文件。

### 我可以免費使用 Aspose.PDF 嗎？
是的，Aspose 提供免費試用版，您可以使用它來探索該程式庫的功能。你可以下載它[這裡](https://releases.aspose.com/).

### 有沒有辦法獲得 Aspose.PDF 支援？
絕對地！您可以透過 Aspose 論壇獲得支持[這裡](https://forum.aspose.com/c/pdf/10).

### 如何購買 Aspose.PDF？
您可以造訪購買頁面購買Aspose.PDF[這裡](https://purchase.aspose.com/buy).

### 我可以使用 Aspose.PDF 建立哪些類型的形狀？
您可以使用 Aspose.PDF 庫建立各種形狀，包括矩形、圓形、直線等。