---
title: 使用 Alpha 顏色建立矩形
linktitle: 使用 Alpha 顏色建立矩形
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 建立具有透明顏色的矩形。自訂透明度的逐步指南。
type: docs
weight: 60
url: /zh-hant/net/programming-with-graphs/create-rectangle-with-alpha-color/
---
在本教學中，我們將引導您逐步完成以下 C# 原始程式碼，以使用 Aspose.PDF for .NET 建立具有 alpha 顏色的矩形。

在開始之前，請確保您已經安裝了 Aspose.PDF 庫並設定了開發環境。也具備 C# 程式設計的基礎知識。

## 第 1 步：文檔目錄設置

在提供的原始程式碼中，您需要指定要儲存產生的 PDF 檔案的目錄。將“dataDir”變數變更為所需的目錄。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：實例化文檔物件並新增頁面

我們建立 Document 類別的一個實例並為該文件新增一個頁面。

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## 第 3 步：建立圖形物件和矩形

我們建立一個具有指定尺寸的 Graph 物件和一個具有特定尺寸的矩形。

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
```

## 步驟 4：設定矩形的 Alpha 顏色

我們可以使用 System.Drawing.Color 類別的 FromArgb 方法為矩形指定 alpha 顏色。

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
```

## 第 5 步：將矩形新增至圖形對象

我們將矩形新增到 Graph 物件的形狀集合中。

```csharp
canvas.Shapes.Add(rect);
```

## 第 6 步：使用不同的 alpha 顏色建立第二個矩形

我們建立第二個具有特定尺寸和另一種 alpha 顏色的矩形。

```csharp
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
```

## 步驟7：將圖形物件加入頁面

我們將 Graph 物件加入到 Page 物件的 Paragraph 集合中。

```csharp
page.Paragraphs.Add(canvas);
```

## 第 8 步：儲存生成的 PDF 文件

最後，我們將產生的 PDF 檔案保存在指定目錄中，名稱為「CreateRectangleWithAlphaColor_out.pdf」。

```csharp
doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");
```

### 使用 Aspose.PDF for .NET 建立帶有 Alpha 顏色的矩形的範例原始程式碼 

```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//實例化文件實例
Document doc = new Document();
//將頁面新增至 PDF 檔案的頁面集合
Aspose.Pdf.Page page = doc.Pages.Add();
//建立圖實例
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
//建立具有特定尺寸的矩形對象
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
//從 32 位元 ARGB 值的 System.Drawing.Color 結構中設定圖形填滿顏色
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
//將矩形物件新增至 Graph 實例的形狀集合中
canvas.Shapes.Add(rect);
//建立第二個矩形對象
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
//將圖形實例加入到頁面物件的段落集合中
page.Paragraphs.Add(canvas);
dataDir = dataDir + "CreateRectangleWithAlphaColor_out.pdf";
//儲存 PDF 文件
doc.Save(dataDir);
Console.WriteLine("\nRectangle object created successfully with alpha color.\nFile saved at " + dataDir);            

```

## 結論

在本教學中，我們說明如何使用 Aspose.PDF for .NET 建立具有 alpha 顏色的矩形。現在，您可以使用這些知識在 PDF 檔案中建立具有透明顏色的幾何形狀。

## 常見問題解答

#### Q：本教學的目的是什麼？

答：本教學課程旨在引導您完成使用 Aspose.PDF for .NET 建立具有 alpha 顏色的矩形的過程。您將學習如何為 PDF 檔案添加具有透明顏色的幾何形狀。

#### Q：開始之前需要什麼先決條件？

答：開始之前，請確保您已安裝 Aspose.PDF 庫並設定開發環境。此外，建議對 C# 程式設計有基本的了解。

#### Q：如何指定PDF檔案的保存目錄？

答：在提供的原始程式碼中，您可以修改「dataDir」變數以指示要儲存產生的 PDF 檔案的目錄。

#### Q：Graph 物件和 Rectangle 的用途是什麼？

答：「圖形」物件充當繪圖元素的容器，而「矩形」則代表您將新增至 PDF 中的幾何形狀。

#### Q：如何為矩形設定 Alpha 顏色？

答：您可以使用以下指令為矩形指定 Alpha 顏色：`FillColor`的財產`GraphInfo`對象和`Color.FromRgb`具有 ARGB 值的方法。

#### Q：我可以建立多個具有不同 Alpha 顏色的矩形嗎？

答：是的，您可以按照教學中示範的類似步驟建立多個具有不同 alpha 顏色的矩形。

#### Q：使用 Alpha 顏色建立矩形後如何儲存生成的 PDF 檔案？

答：使用 alpha 顏色建立矩形後，您可以使用以下命令儲存生成的 PDF 檔案：`doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");`提供的源代碼中的行。