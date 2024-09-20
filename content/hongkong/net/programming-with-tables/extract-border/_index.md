---
title: 提取 PDF 檔案中的邊框
linktitle: 提取 PDF 檔案中的邊框
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 從 PDF 檔案中提取邊框並將其儲存為映像。包含程式碼範例和成功提示的逐步指南。
type: docs
weight: 80
url: /zh-hant/net/programming-with-tables/extract-border/
---
## 介紹

在處理 PDF 時，提取特定元素（例如邊框或圖形路徑）可能看起來是一項艱鉅的任務。但使用 Aspose.PDF for .NET，您可以輕鬆地從 PDF 文件中提取邊框或形狀並將其儲存為映像。在本教程中，我們將深入研究從 PDF 中提取邊框並將其另存為 PNG 圖像的過程。準備好控制 PDF 的圖形內容！

## 先決條件

在我們深入研究程式碼之前，請確保您已完成所有設定：

1.  Aspose.PDF for .NET：如果您尚未安裝 Aspose.PDF 庫，您可以[在這裡下載](https://releases.aspose.com/pdf/net/)。您還需要透過免費試用或購買許可證來套用許可證。
2. IDE 設定：在 Visual Studio 或任何其他 .NET IDE 中設定 C# 專案。確保您已新增對 Aspose.PDF 庫的必要引用。
3. 輸入 PDF 文件：準備好一個 PDF 文件，您可以從中提取邊框。本教學將引用一個名為`input.pdf`.

## 導入所需的套件

讓我們開始導入所需的命名空間。這些套件提供了操作 PDF 內容所需的工具。

```csharp
using System.IO;
using System;
using System.Drawing.Drawing2D;
using System.Drawing.Imaging;
using System.Collections;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

現在我們已經了解了基礎知識，讓我們轉到逐步指南，我們將分解程式碼的每個部分以詳細解釋它。


## 第 1 步：載入 PDF 文檔

第一步是載入包含要提取邊框的 PDF 文件。可以將其想像為在開始閱讀之前打開一本書 - 您需要訪問內容！

我們將首先指定儲存 PDF 檔案的目錄，並使用以下命令載入文件：`Aspose.Pdf.Document`班級。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
```

此程式碼載入`input.pdf`來自您指定目錄的檔案。確保檔案路徑正確，否則您可能會收到檔案未找到錯誤。

## 第 2 步：設定圖形和點陣圖

在開始提取之前，我們需要創建一個畫布來繪製。在 .NET 世界中，這意味著設定 Bitmap 和 Graphics 物件。 Bitmap 表示影像，Graphics 物件可讓我們繪製從 PDF 中提取的形狀，例如邊框。

```csharp
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);
```

這是一個細分：
- 我們建立 PDF 第一頁大小的點陣圖影像。
- GraphicsPath 用於定義形狀（在本例中為邊框）。
- 矩陣定義了圖形如何變換；我們需要一個反轉矩陣，因為 PDF 和 .NET 有不同的座標系。

## 步驟3：處理PDF內容


PDF檔案是一系列繪圖命令，我們需要處理每個命令來識別和提取邊框資訊。

```csharp
foreach (Operator op in doc.Pages[1].Contents)
{
    //處理命令，例如儲存/恢復狀態、繪製線條、填滿形狀等。
}
```

此程式碼循環遍歷 PDF 內容流中的每個繪圖運算符。每個運算符可能代表一條線、矩形或其他圖形指令。

## 步驟 4：處理 PDF 運算符

PDF 檔案中的每個運算子控制一個操作。為了提取邊框，我們需要識別諸如“移動到”、“線到”和“繪製矩形”等命令。以下運算子處理這些操作：

- MoveTo：將遊標移到起點。
- LineTo：從目前點到新點繪製一條線。
- 回覆：繪製一個矩形（這可能是邊框的一部分）。

```csharp
Aspose.Pdf.Operators.MoveTo opMoveTo = op as Aspose.Pdf.Operators.MoveTo;
Aspose.Pdf.Operators.LineTo opLineTo = op as Aspose.Pdf.Operators.LineTo;
Aspose.Pdf.Operators.Re opRe = op as Aspose.Pdf.Operators.Re;

if (opMoveTo != null)
{
    lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
    System.Drawing.PointF linePoint = new System.Drawing.PointF((float)opLineTo.X, (float)opLineTo.Y);
    graphicsPath.AddLine(lastPoint, linePoint);
    lastPoint = linePoint;
}
else if (opRe != null)
{
    System.Drawing.RectangleF re = new System.Drawing.RectangleF((float)opRe.X, (float)opRe.Y, (float)opRe.Width, (float)opRe.Height);
    graphicsPath.AddRectangle(re);
}
```

在這一步中：
- 我們捕捉繪製的每條線或形狀的點。
- 對於矩形（`opRe` ），我們直接將它們添加到`graphicsPath`，稍後我們將使用它來繪製邊框。

## 步驟5：繪製邊框

一旦我們確定了形成邊框的線條和矩形，我們就需要將它們實際繪製到 Bitmap 物件上。這就是 Graphics 物件的用武之地。

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
    gr.SmoothingMode = SmoothingMode.HighQuality;
    gr.DrawPath(new System.Drawing.Pen(strokeColor), graphicsPath);
}
```

- 我們基於點陣圖建立一個 Graphics 物件。
- SmoothingMode.HighQuality 確保我們獲得漂亮平滑的圖像。
- 最後，我們使用DrawPath來繪製邊框。

## 步驟6：儲存提取的邊框

現在我們已經提取了邊框，是時候將其儲存為圖像檔案了。這會將邊框另存為 PNG。

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

- 點陣圖儲存為 PNG 影像。
- 現在您可以打開此圖像以查看提取的邊框。

## 結論

使用 Aspose.PDF for .NET 從 PDF 文件中提取邊框一開始可能看起來很棘手，但一旦將其分解，它就會變得簡單。透過了解 PDF 中的繪圖運算子並利用強大的 .NET 程式庫，您可以有效地操作和提取圖形內容。本指南為您開始 PDF 操作奠定了堅實的基礎！

## 常見問題解答

### 如何處理 PDF 中的多個頁面？  
您可以透過迭代來循環瀏覽文件中的每個頁面`doc.Pages`而不是硬編碼`doc.Pages[1]`.

### 我可以使用相同的方法提取其他元素（例如文字）嗎？  
是的，Aspose.PDF 提供了豐富的 API 來從 PDF 檔案中提取文字、圖像和其他內容。

### 如何申請許可證以避免限制？  
你可以[申請許可證](https://purchase.aspose.com/temporary-license/)透過加載它`License`Aspose 提供的類別。

### 如果我的 PDF 沒有邊框怎麼辦？  
如果您的 PDF 不包含可見邊框，圖形擷取過程可能不會產生任何結果。確保 PDF 內容包含可繪製邊框。

### 我可以將輸出儲存為 PNG 以外的格式嗎？  
是的，只需更改`ImageFormat.Png`轉換為另一種受支援的格式，例如`ImageFormat.Jpeg`.