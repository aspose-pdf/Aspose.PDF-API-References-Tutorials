---
title: 添加帶有漸變填充的繪圖
linktitle: 添加帶有漸變填充的繪圖
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 新增具有漸層填滿的繪圖。逐步教學建立有吸引力的 PDF 文件。
type: docs
weight: 20
url: /zh-hant/net/programming-with-graphs/add-drawing-with-gradient-fill/
---
在本教學中，我們將引導您逐步完成以下 C# 原始程式碼，以使用 Aspose.PDF for .NET 進行圖形編程，並新增具有漸層填色的繪圖。

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
Page page = doc.Pages.Add();
```

## 第 3 步：建立圖形物件並將其新增至頁面

我們建立一個具有指定尺寸的 Graph 物件並將其新增至頁面的段落集合中。

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
```

## 第四步：建立矩形物件並新增到圖表中

我們建立一個具有指定尺寸的 Rectangle 對象，並將其新增至圖表的形狀集合中。

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
```

## 第5步：配置漸層填充

我們使用 GradientAxialShading 類別來配置矩形的漸層填色。

```csharp
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
{
Start = new Point(0, 0),
End = new Point(300, 300)
}
};
```

這將創建從紅色到藍色、從點 (0, 0) 到點 (300, 300) 的漸變填充。

## 步驟 6：儲存 PDF 文件

最後，我們將產生的 PDF 檔案保存在指定目錄中，名稱為「AddDrawingWithGradientFill_out.pdf」。

```csharp
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");
```

### 使用 Aspose.PDF for .NET 新增漸層填色圖的範例原始碼 

```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
	PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
	{
		Start = new Point(0, 0),
		End = new Point(300, 300)
	}
};
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");

```
## 結論

在本教學中，我們逐步說明如何使用 Aspose.PDF for .NET 將具有漸進式填滿的繪圖新增至圖形程式設計中。現在，您可以使用這些知識來建立具有自訂設計和漸變填充的有吸引力的 PDF 文件。

### 常見問題解答

#### Q：本教學的目的是什麼？

答：本教學課程旨在引導您完成使用 Aspose.PDF for .NET 進行圖形程式設計新增具有漸層填滿的繪圖的過程。

#### Q：開始之前需要什麼先決條件？

答：開始之前，請確保您已安裝 Aspose.PDF 庫並設定開發環境。此外，建議對 C# 程式設計有基本的了解。

#### Q：如何指定PDF檔案的保存目錄？

答：在提供的原始程式碼中，您可以變更「dataDir」變數的值以指示要儲存產生的 PDF 檔案的目錄。

#### Q：Graph 物件的用途是什麼？

答：Graph 物件充當繪圖元素的容器。它是使用指定的尺寸創建的，並添加到頁面的段落集合中。

#### Q：如何為形狀配置漸層填滿？

答：要設定漸層填充，您可以使用 GradientAxialShading 類別來設定形狀的 GraphInfo 的 FillColor 屬性。這允許您定義漸變的起點和終點以及要在之間過渡的顏色。

#### Q：我可以自訂漸層填滿的顏色和方向嗎？

答：是的，您可以透過調整 Color 物件並指定 GradientAxialShading 的起點和終點來自訂漸層填滿的顏色和方向。

#### Q：本教學的最後一步是什麼？

答：最後一步是將產生的 PDF 檔案以名稱「AddDrawingWithGradientFill_out.pdf」保存在指定目錄中。

#### Q：有可用的範例原始碼嗎？

答：是的，本教學提供了範例原始程式碼，您可以將其用作實作所描述步驟的參考。

#### Q：我可以將漸層填充應用於矩形之外的其他形狀嗎？

答：是的，您也可以將漸層填滿應用於其他形狀。此過程涉及使用 GradientAxialShading 類別配置形狀的 GraphInfo 的 FillColor 屬性。