---
title: 畫線
linktitle: 畫線
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在頁面上繪製一條線。建立自訂線條的分步指南。
type: docs
weight: 80
url: /zh-hant/net/programming-with-graphs/drawing-line/
---
在本教學中，我們將引導您逐步完成以下 C# 原始程式碼，以使用 Aspose.PDF for .NET 繪製一條線。

在開始之前，請確保您已經安裝了 Aspose.PDF 庫並設定了開發環境。也具備 C# 程式設計的基礎知識。

## 第 1 步：文檔目錄設置

在提供的原始程式碼中，您需要指定要儲存產生的 PDF 檔案的目錄。將“dataDir”變數變更為所需的目錄。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步驟2：建立文檔實例並新增頁面

我們建立 Document 類別的一個實例並為該文件新增一個頁面。

```csharp
Document pDoc = new Document();
Page pg = pDoc.Pages.Add();
```

## 步驟 3：設定頁邊距

我們將所有邊的頁邊距設定為 0。

```csharp
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

## 第 4 步：建立圖形物件和第一行

我們建立一個尺寸等於頁面尺寸的 Graph 對象，並繪製從頁面左下角到右上角的第一條線。

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width, (float)pg.PageInfo.Height);
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect. URY });
graph.Shapes.Add(line);
```

## 第五步：畫第二條線

我們繪製從頁面左上角到右下角的第二條線。

```csharp
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect. LLX });
graph.Shapes.Add(line2);
```

## 第 6 步：將圖形物件新增至頁面

我們將 Graph 物件加入到頁面的段落集合中。

```csharp
pg.Paragraphs.Add(graph);
```

## 第 7 步：儲存生成的 PDF 文件

最後，我們將產生的 PDF 檔案以名稱「DrawingLine_out.pdf」保存在指定目錄中。

```csharp
pDoc.Save(dataDir + "DrawingLine_out.pdf");
```

### 使用 Aspose.PDF for .NET 繪製線條的範例原始程式碼 

```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//建立文件實例
Document pDoc = new Document();
//將頁面新增至 PDF 文件的頁面集合
Page pg = pDoc.Pages.Add();
//將所有邊的頁邊距設定為0
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
//建立寬度和高度等於頁面尺寸的圖形對象
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width , (float)pg.PageInfo.Height);
//建立從頁面左下角到右上角的第一行對象
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });
//將線條加入 Graph 物件的形狀集合中
graph.Shapes.Add(line);
//從頁面左上角到頁面右下角繪製一條線
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });
//將線條加入 Graph 物件的形狀集合中
graph.Shapes.Add(line2);
//將 Graph 物件加入到頁面的段落集合中
pg.Paragraphs.Add(graph);
dataDir = dataDir + "DrawingLine_out.pdf";
//儲存 PDF 文件
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);            

```

## 結論

在本教學中，我們說明如何使用 Aspose.PDF for .NET 繪製一條線。現在，您可以利用這些知識在 PDF 文件中建立帶有自訂線條的幾何形狀。

### 常見問題解答

#### Q：本教學的目的是什麼？

答：本教學的目的是引導您完成使用 Aspose.PDF for .NET 繪製線條的過程。您將學習如何在 PDF 頁面上建立線條並自訂其外觀。

#### Q：開始之前需要什麼先決條件？

答：開始之前，請確保您已經安裝了 Aspose.PDF 庫並設定了開發環境。也建議具備 C# 程式設計基礎。

#### Q：如何指定PDF檔案的保存目錄？

答：修改提供的原始程式碼中的“dataDir”變數以指示要儲存產生的 PDF 檔案的目錄。

#### Q：如何在 PDF 頁面上建立線條？

答：本教學示範了使用頁面尺寸建立一個 Graph 對象，然後在其中加入 Line 物件。修改 Line 物件的座標和屬性以建立所需的線。

#### Q：我可以自訂線條的外觀嗎？

答：是的，您可以透過修改 Line 物件的屬性來自訂線條的外觀。這包括更改它們的座標、顏色、厚度和其他圖形屬性。

#### Q：畫線後如何儲存PDF文件？

答：將帶有 Line 物件的 Graph 物件新增至頁面後，您可以使用下列命令儲存產生的 PDF 文件：`pDoc.Save(dataDir + "DrawingLine_out.pdf");`提供的源代碼中的行。

#### Q：我可以畫不同角度和方向的線嗎？

答：是的，您可以透過調整圖表中線條物件的座標和屬性來繪製不同角度和方向的線條。