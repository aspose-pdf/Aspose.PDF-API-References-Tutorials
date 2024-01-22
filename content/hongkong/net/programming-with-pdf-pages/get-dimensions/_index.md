---
title: 取得 PDF 頁面尺寸
linktitle: 取得 PDF 頁面尺寸
second_title: Aspose.PDF for .NET API 參考
description: 在本教學中，我們將說明如何使用 Aspose.PDF for .NET 取得 PDF 頁面尺寸並執行操作。提供了詳細的步驟來引導您完成整個過程。
type: docs
weight: 60
url: /zh-hant/net/programming-with-pdf-pages/get-dimensions/
---
在本教學中，我們將引導您逐步完成使用 Aspose.PDF for .NET 取得 PDF 檔案中的頁面尺寸的過程。我們將解釋捆綁的 C# 原始程式碼，並為您提供全面的指南，幫助您理解並在自己的專案中實現此功能。在本教學結束時，您將了解如何使用 Aspose.PDF for .NET 取得 PDF 檔案中頁面的尺寸。

## 先決條件
在開始之前，請確保您具備以下條件：

- C# 程式語言的基礎知識
- 在您的開發環境中安裝 Aspose.PDF for .NET

## 步驟1：定義文檔目錄
首先，您需要設定文檔目錄的路徑。這是您的 PDF 文件所在的位置。將“您的文件目錄”替換為適當的路徑。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步驟 2：開啟 PDF 文檔
然後您可以使用以下命令開啟 PDF 文件`Document`Aspose.PDF 類別。請務必指定 PDF 檔案的正確路徑。

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## 步驟 3：新增空白頁（如果需要）
如果PDF文件已經包含頁面，您可以使用索引跳到現有頁面`1`（第一頁的索引為 1）。否則，您可以向文件新增頁面。

```csharp
Page page = pdfDocument.Pages.Count > 0? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

## 第 4 步：取得頁面尺寸
現在您可以使用以下方法來取得頁面尺寸`GetPageRect()`的方法`Page`目的。該方法傳回一個`Rectangle`包含頁面尺寸的物件。您可以使用以下命令存取寬度和高度`Width`和`Height`特性。

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

## 第 5 步：旋轉頁面
如果你想旋轉頁面，你可以使用`Rotate`的財產`Page`目的。在此範例中，頁面旋轉 90 度。

```csharp
page. Rotate = Rotate. on90;
```

## 步驟6：再次取得頁面尺寸
頁面旋轉後，您可以使用以下命令再次取得頁面尺寸`GetPageRect()`方法。

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

### 使用 Aspose.PDF for .NET 取得尺寸的範例原始碼 

```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開啟文件
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
//在 pdf 文件中新增空白頁
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
//取得頁面高度和寬度信息
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
//將頁面旋轉 90 度角
page.Rotate = Rotation.on90;
//取得頁面高度和寬度信息
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);

```

## 結論
在本教學中，我們學習如何使用 Aspose.PDF for .NET 來取得 PDF 檔案中頁面的尺寸。透過按照提供的步驟操作，您可以輕鬆提取頁面尺寸並執行其他 PDF 操作操作。 Aspose.PDF for .NET 為處理 PDF 文件提供了極大的靈活性，並允許您開發強大的客製化解決方案。

請隨意進一步探索 Aspose.PDF 的文檔，以發現該庫提供的所有功能。

### 取得 PDF 頁面尺寸的常見問題解答

#### Q：如何取得 PDF 檔案中特定頁面的尺寸？

答：要取得 PDF 檔案中特定頁面的尺寸，您可以使用`GetPageRect()`的方法`Page`Aspose.PDF for .NET 中的物件。該方法傳回一個`Rectangle`包含頁面尺寸（寬度和高度）的物件。

####  Q：什麼是`GetPageRect(true)` method do in the provided C# source code?

答： 的`GetPageRect(true)`提供的 C# 原始程式碼中的方法會傳回套用任何旋轉後頁面的尺寸。如果頁面旋轉，方法將返迴旋轉頁面的尺寸，該尺寸可能與原始尺寸不同。

#### Q：我可以使用 Aspose.PDF for .NET 來取得 PDF 文件中所有頁面的尺寸嗎？

 A：是的，您可以透過迭代來取得PDF文件中所有頁面的尺寸`Pages`的集合`Document`物件並使用`GetPageRect(true)`每個頁面的方法。

#### Q：如何根據頁面的尺寸來決定頁面的方向（縱向或橫向）？

答：若要根據頁面的尺寸來決定頁面的方向，您可以比較頁面的寬度和高度。如果寬度大於高度，則頁面為橫向，如果高度大於寬度，則頁面為縱向。

#### Q：我可以使用 Aspose.PDF for .NET 修改頁面尺寸嗎？

答：是的，您可以在 Aspose.PDF for .NET 中修改頁面的尺寸。得到後`Rectangle`代表頁面尺寸的對象，您可以根據您的要求調整寬度和高度，然後將變更套用到頁面。