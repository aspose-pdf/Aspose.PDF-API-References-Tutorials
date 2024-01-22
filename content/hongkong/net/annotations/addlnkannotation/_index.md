---
title: 新增lnk註釋
linktitle: 新增lnk註釋
second_title: Aspose.PDF for .NET API 參考
description: 透過逐步指南和完整原始程式碼，了解如何使用 Aspose.PDF for .NET 在 C# 中為 PDF 文件新增墨跡註解功能。
type: docs
weight: 20
url: /zh-hant/net/annotations/addlnkannotation/
---
Aspose.PDF for .NET 是一個功能強大的程式庫，可讓開發人員執行各種 PDF 操作。其中一項操作就是在 PDF 文件中加入墨跡註解。在本文中，我們將提供逐步指南來解釋使用 Aspose.PDF for .NET 新增墨跡註解的 C# 原始程式碼。讓我們開始吧！

## 了解 Aspose.PDF for .NET 的墨跡註解功能

在深入研究 C# 原始程式碼之前，我們首先了解什麼是 Ink Annotation 及其用途。

墨跡註釋是一種在 PDF 文件上繪製自由格式墨跡註釋的方法。它允許您使用手寫筆或滑鼠建立註釋。當您需要繪製圖表、草圖或其他類型的註釋時，此功能非常有用。

## 第 1 步：建立新文檔

將墨跡註解新增至 PDF 文件的第一步是建立 Document 類別的新實例。這是使用以下程式碼片段實現的：

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
Page pdfPage = doc.Pages.Add();
```

在這裡，我們建立 Document 類別的新實例並向其新增頁面。

## 步驟 2： 建立墨跡註釋

下一步是建立 InkAnnotation 類別的實例。這是使用以下程式碼片段完成的：

```csharp
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(筆劃.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);
```

在這裡，我們首先使用 System.Drawing.Rectangle 類別建立一個矩形，並使用 FromRect 方法將其轉換為 Aspose.Pdf.Rectangle。然後，我們使用矩形、點列表以及新增註解的頁面來建立 InkAnnotation 類別的實例。

然後，我們設定 InkAnnotation 的各種屬性，例如標題、顏色、大頭樣式、邊框和不透明度。最後，我們使用 Annotations.Add 方法將註解新增至頁面。

## 第 3 步：儲存文檔

最後一步是儲存新增了墨跡註釋的 PDF 文件。這是使用以下程式碼片段實現的：

```csharp
dataDir = dataDir + "AddlnkAnnotation_out.pdf";
doc.Save(dataDir);
```

在這裡，我們將輸出檔案名稱連接到資料目錄，並使用 Save 方法儲存文件。

### 使用 Aspose.PDF for .NET 新增墨跡註解的範例原始碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DATA DIRECTORY";


Document doc = new Document();
Page pdfPage = doc.Pages.Add();
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(筆劃.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);

dataDir = dataDir + "AddlnkAnnotation_out.pdf";
//儲存輸出檔案
doc.Save(dataDir);
```

## 結論

在本教學中，我們探討如何使用 Aspose.PDF for .NET 將墨跡註解新增至 PDF 文件。透過遵循提供的逐步指南和 C# 原始程式碼，開發人員可以輕鬆在 PDF 處理應用程式中實現墨跡註釋功能。

### 常見問題解答

#### Q：什麼是 PDF 文件中的墨跡註釋？

答：PDF 文件中的墨跡註解允許使用者使用手寫筆或滑鼠繪製自由格式的墨跡註解。它通常用於向 PDF 添加手繪草圖、圖表或其他手繪註釋。

#### Q：我可以自訂墨跡註解的外觀嗎？

答：是的，Aspose.PDF for .NET 提供了各種屬性來自訂墨跡註解的外觀，例如顏色、不透明度、大頭樣式、邊框寬度等。開發人員可以調整這些屬性以滿足他們的特定要求。

#### Q：是否可以將多個墨跡註解新增至單一 PDF 頁面？

答：是的，您可以使用 Aspose.PDF for .NET 將多個墨跡註解新增至單一 PDF 頁面。每個墨跡註釋都可以有自己的一組點和自訂外觀。

#### Q：我可以在現有 PDF 文件中添加墨跡註釋嗎？

答：是的，Aspose.PDF for .NET 允許您將墨跡註解新增至新建立的 PDF 文件和現有 PDF 文件。您可以開啟現有 PDF、新增墨跡註釋並儲存更新的文件。

#### Q：PDF 文件中墨跡註解有哪些常見用例？

答：墨跡註釋適用於多種應用，包括在 PDF 表單中添加簽名或手寫註釋、註釋建築藍圖或工程圖以及標記文件以供協作審查。