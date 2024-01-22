---
title: 建立填滿矩形
linktitle: 建立填滿矩形
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 建立填滿矩形。自訂填滿顏色的分步指南。
type: docs
weight: 50
url: /zh-hant/net/programming-with-graphs/create-filled-rectangle/
---
在本教學中，我們將引導您逐步完成以下 C# 原始程式碼，以使用 Aspose.PDF for .NET 建立填滿矩形。

在開始之前，請確保您已經安裝了 Aspose.PDF 庫並設定了開發環境。也具備 C# 程式設計的基礎知識。

## 第 1 步：文檔目錄設置

在提供的原始程式碼中，您需要指定要儲存產生的 PDF 檔案的目錄。將“dataDir”變數變更為所需的目錄。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步驟2：建立文檔實例並新增頁面

我們建立 Document 類別的一個實例並為該文件新增一個頁面。

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## 第 3 步：建立圖形物件並將其新增至頁面

我們建立一個具有指定尺寸的 Graph 物件並將其新增至頁面的段落集合中。

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## 第四步：建立矩形物件並新增到圖表中

我們建立一個具有指定尺寸的 Rectangle 對象，並將其新增至圖表的形狀集合中。

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
graph.Shapes.Add(rect);
```

## 第五步：設定填滿顏色

我們可以使用 GraphInfo 物件的 FillColor 屬性來指定矩形的填滿顏色。

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## 第 6 步：儲存生成的 PDF 文件

最後，我們將產生的 PDF 檔案以名稱「CreateFilledRectangle_out.pdf」儲存在指定目錄中。

```csharp
doc.Save(dataDir + "CreateFilledRectangle_out.pdf");
```

### 使用 Aspose.PDF for .NET 建立填滿矩形的範例原始碼 

```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//建立文件實例
Document doc = new Document();
//將頁面新增至 PDF 檔案的頁面集合
Page page = doc.Pages.Add();
//建立圖實例
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
//將圖形物件加入到頁面實例的段落集合中
page.Paragraphs.Add(graph);
//建立矩形實例
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
//指定 Graph 物件的填滿顏色
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
//將矩形物件新增至圖形物件的形狀集合中
graph.Shapes.Add(rect);
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
//儲存 PDF 文件
doc.Save(dataDir);
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);            

```

## 結論

在本教學中，我們說明如何使用 Aspose.PDF for .NET 建立填滿矩形。現在，您可以利用這些知識在 PDF 檔案中建立具有自訂填滿色彩的幾何形狀。

## 常見問題解答

#### Q：本教學的目的是什麼？

答：本教學的目的是引導您完成使用 Aspose.PDF for .NET 建立填滿矩形的過程，使您能夠在 PDF 檔案中新增具有填滿顏色的自訂幾何形狀。

#### Q：開始之前需要什麼先決條件？

答：開始之前，請確保您已安裝 Aspose.PDF 庫並設定開發環境。此外，建議對 C# 程式設計有基本的了解。

#### Q：如何指定PDF檔案的保存目錄？

答：在提供的原始程式碼中，您可以修改「dataDir」變數以指示要儲存產生的 PDF 檔案的目錄。

#### Q：Graph 物件的用途是什麼？

答：Graph 物件充當繪圖元素的容器。它是使用指定的尺寸創建的，並添加到頁面的段落集合中。

#### Q：如何在 PDF 文件中新增填充矩形？

答：若要新增填滿矩形，請建立具有指定尺寸和填滿顏色的 Rectangle 類別的實例，並將其新增至圖形的形狀集合中。

#### Q：我可以自訂矩形的尺寸和填滿顏色嗎？

 A：是的，您可以透過修改傳入的參數來自訂矩形的尺寸和填滿顏色`Aspose.Pdf.Drawing.Rectangle`建構函數並設定 FillColor 屬性。

#### Q：建立填滿矩形後如何儲存產生的 PDF 檔案？

答：建立填滿矩形後，您可以使用以下命令儲存產生的 PDF 檔案：`doc.Save(dataDir + "CreateFilledRectangle_out.pdf");`提供的源代碼中的行。