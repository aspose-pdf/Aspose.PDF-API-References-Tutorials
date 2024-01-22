---
title: 新增圖層到 PDF 文件
linktitle: 新增圖層到 PDF 文件
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 將圖層新增至 PDF 檔案。包含用於建立和保存分層 PDF 的程式碼教學的逐步指南。
type: docs
weight: 20
url: /zh-hant/net/programming-with-document/addlayers/
---
為了在 PDF 檔案中新增圖層，我們將使用 Aspose.PDF for .NET。該程式庫使我們能夠在 .NET 應用程式中有效地處理 PDF 文件。請依照下面的逐步說明使用 Aspose.PDF for .NET 新增圖層。

## 第 1 步：建立新的 PDF 文檔

首先建立一個新實例`Document`Aspose.PDF for .NET 提供的類別。這將作為 PDF 文檔，我們將在其中添加圖層。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

## 步驟 2：新增頁面

接下來，使用以下命令為文件新增頁面`Add`的方法`Pages`集合於`Document`班級。

```csharp
Page page = doc.Pages.Add();
```

## 第 3 步：建立圖層並將其新增至頁面

建立實例`Layer`要新增到 PDF 檔案的每個圖層的類別。為每個圖層指定唯一識別碼和名稱。

```csharp
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new List<Layer>();
page.Layers.Add(layer);

layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);

layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
```

在本教程中，我們為頁面添加了三個具有不同顏色和名稱的圖層。

## 步驟 4：儲存 PDF 文件

使用以下命令儲存修改後的 PDF 文件`Save`的方法`Document`班級。

```csharp
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);
```

此程式碼將修改後的PDF檔案儲存到指定目錄。

### 使用 Aspose.PDF for .NET 新增圖層到 PDF 頁面的範例原始碼

```csharp            
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new  List<Layer>();
page.Layers.Add(layer);
layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);

```

## 結論

在本文中，我們提供了使用 Aspose.PDF for .NET 為 PDF 檔案新增圖層的逐步指南。透過遵循說明並利用提供的程式碼教學，您可以輕鬆地將圖層合併到 PDF 文件中。圖層可讓您組織和控制內容的可見性，為使用者提供更具互動性和可自訂的體驗。


### 在 PDF 檔案中新增圖層的常見問題解答

#### Q：什麼是 Aspose.PDF for .NET？

答：Aspose.PDF for .NET 是一個功能強大的程式庫，可讓開發人員在 .NET 應用程式中有效地處理 PDF 檔案。它提供了用於建立、修改和操作 PDF 文件的廣泛功能。

#### Q：什麼是 PDF 圖層？

答：PDF 圖層，也稱為可選內容群組 (OCG)，可讓您控制 PDF 文件中特定內容的可見性和外觀。它們對於組織內容和建立互動式文件非常有用。

#### Q：我可以使用 Aspose.PDF for .NET 將多個圖層新增到 PDF 檔案嗎？

答：是的，您可以使用 Aspose.PDF for .NET 將多個圖層加入 PDF 檔案中。每個圖層都可以有自己的唯一識別碼和名稱，如教程中所示。

#### Q：如何自訂圖層的外觀？

答：您可以透過指定不同的屬性（例如顏色、不透明度和可見性）來自訂圖層的外觀。 Aspose.PDF for .NET 提供了各種選項來實現此目的。

#### Q：Aspose.PDF for .NET 適合專業專案嗎？

答：是的，Aspose.PDF for .NET 是一個可靠且廣泛使用的函式庫，用於專業專案中的 PDF 操作。它為在 .NET 應用程式中處理 PDF 文件提供了廣泛的功能和出色的性能。