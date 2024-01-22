---
title: 在 PDF 檔案中新增線條對象
linktitle: 在 PDF 檔案中新增線條對象
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 檔案中新增自訂線條物件。
type: docs
weight: 30
url: /zh-hant/net/programming-with-graphs/add-line-object/
---
在本教學中，我們將引導您逐步完成以下 C# 原始程式碼，以使用 Aspose.PDF for .NET 新增線條物件。

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

## 第 4 步：建立線條物件並新增到圖表

我們使用指定的座標建立一個 Line 對象，並將其新增到圖表的形狀集合中。

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
graph.Shapes.Add(line);
```

## 第 5 步：線路設定

我們可以指定線條的屬性，例如虛線類型和虛線相位。

```csharp
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## 步驟 6：儲存 PDF 文件

最後，我們將產生的 PDF 檔案以名稱「AddLineObject_out.pdf」保存在指定目錄中。

```csharp
doc.Save(dataDir + "AddLineObject_out.pdf");
```

### 使用 Aspose.PDF for .NET 新增線條物件的範例原始程式碼 

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
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
//指定 Graph 物件的填滿顏色
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
//將矩形物件新增至圖形物件的形狀集合中
graph.Shapes.Add(line);
dataDir = dataDir + "AddLineObject_out.pdf";
//儲存 PDF 文件
doc.Save(dataDir);
Console.WriteLine("\nLine object added successfully to pdf.\nFile saved at " + dataDir);            

```

## 結論

在本教學中，我們逐步說明如何使用 Aspose.PDF for .NET 新增線條物件。現在您可以利用這些知識在應用程式中建立帶有自訂行的 PDF 文件。

### 在 PDF 檔案中新增線條物件的常見問題解答

#### Q：本教學的目的是什麼？

答：本教學課程旨在引導您完成使用 Aspose.PDF for .NET 新增線條物件以增強 PDF 文件的過程。

#### Q：開始之前需要什麼先決條件？

答：開始之前，請確保您已經安裝了 Aspose.PDF 庫並設定了開發環境。此外，建議對 C# 程式設計有基本的了解。

#### Q：如何指定PDF檔案的保存目錄？

答：在提供的原始程式碼中，您可以修改「dataDir」變數以指示要儲存產生的 PDF 檔案的目錄。

#### Q：Graph 物件的用途是什麼？

答：Graph 物件充當繪圖元素的容器。它是使用指定的尺寸創建的，並添加到頁面的段落集合中。

#### Q：如何在 PDF 文件中新增線條物件？

答：若要新增線條對象，請建立具有指定座標的 Line 類別的實例，並將其新增至圖形的形狀集合中。

#### Q：我可以自訂線路的外觀嗎？

答：是的，您可以透過使用 Line 物件的 GraphInfo 屬性來設定破折號類型和破折號相位等屬性來自訂線條的外觀。

#### Q：指定破折號數組和破折號相位的目的為何？

答：虛線陣列和虛線階段屬性可讓您建立具有特定圖案的虛線或點線。

#### Q：新增線條物件後如何儲存PDF檔案？

答：新增線條物件後，您可以使用以下命令儲存產生的 PDF 檔案：`doc.Save(dataDir + "AddLineObject_out.pdf");`提供的源代碼中的行。

#### Q：有可用的範例原始碼嗎？

答：是的，本教學包含範例原始程式碼，您可以參考它來實現所描述的步驟。