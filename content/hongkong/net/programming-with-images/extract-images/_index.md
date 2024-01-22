---
title: 從 PDF 檔案中提取圖像
linktitle: 從 PDF 檔案中提取圖像
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 輕鬆從 PDF 檔案中擷取影像。
type: docs
weight: 120
url: /zh-hant/net/programming-with-images/extract-images/
---
本指南將逐步指導您如何使用 Aspose.PDF for .NET 從 PDF 文件中提取圖像。確保您已設定環境並按照以下步驟操作：

## 步驟1：定義文檔目錄

開始之前，請確保為文件設定正確的目錄。代替`"YOUR DOCUMENT DIRECTORY"`在程式碼中新增 PDF 文件所在目錄的路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步驟 2：開啟 PDF 文檔

在此步驟中，我們將使用以下命令開啟 PDF 文檔`Document` Aspose.PDF 類別。使用`Document`建構函數並傳遞 PDF 文件的路徑。

```csharp
Document pdfDocument = new Document(dataDir + "ExtractImages.pdf");
```

## 第三步：提取特定影像

在此步驟中，我們將從特定頁面中提取特定圖像。使用`Images`頁面集合`s `Resources` 物件來存取所需的映像。在下面的範例中，我們從第一頁中提取索引為 1 的圖像。

```csharp
XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
```

## 第四步：保存擷取的影像

使用以下命令將提取的圖像儲存到檔案中`Save`的方法`xImage`目的。指定輸出路徑和影像格式（在本例中我們使用 JPEG 格式）。

```csharp
FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
xImage.Save(outputImage, ImageFormat.Jpeg);
outputImage.Close();
```

## 第 5 步：儲存更新的 PDF 文件

使用以下命令儲存更新的 PDF 文件`Save`的方法`pdfDocument`目的。指定 PDF 檔案的輸出路徑。

```csharp
dataDir = dataDir + "ExtractImages_out.pdf";
pdfDocument.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 擷取影像的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開啟文件
Document pdfDocument = new Document(dataDir+ "ExtractImages.pdf");
//提取特定影像
XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
//儲存輸出影像
xImage.Save(outputImage, ImageFormat.Jpeg);
outputImage.Close();
dataDir = dataDir + "ExtractImages_out.pdf";
//儲存更新的 PDF 文件
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages extracted successfully.\nFile saved at " + dataDir); 
```

## 結論

恭喜！您已使用 Aspose.PDF for .NET 成功從 PDF 中擷取影像。提取的圖像將保存在指定目錄中，並且更新的 PDF 文件也會保存。現在您可以使用這些文件來滿足您的特定需求。

### 從 PDF 文件中提取圖像的常見問題解答

#### Q：為什麼我要使用 Aspose.PDF for .NET 從 PDF 檔案中擷取影像？

答：從 PDF 檔案中擷取影像可用於多種目的，例如存檔、在其他文件中重複使用影像、分析內容或執行影像處理任務。

#### Q：Aspose.PDF for .NET 如何促進從 PDF 文件中提取影像？

答：Aspose.PDF for .NET 提供了一個逐步過程來開啟 PDF 文件、存取特定影像並將其儲存為使用各種格式的影像檔案。

####  Q： 有何作用`Document` class in Aspose.PDF for .NET play in image extraction?

答： 的`Document`類別用於載入和操作 PDF 文件。在這種情況下，它有助於打開從中提取圖像的 PDF 文件。

#### Q：如何指定要從 PDF 頁面中提取的特定圖像？

答：您可以使用`Images`頁面的集合`Resources`物件透過其索引存取所需的圖像。例如，`pdfDocument.Pages[1].Resources.Images[1]`訪問第一頁上的第一張圖像。

#### Q：我可以從 PDF 文件的任意頁面提取圖像嗎？

答：是的，您可以透過指定所需的頁面索引和要提取的圖像的索引，從 PDF 文件的任何頁面中提取圖像。

#### Q：擷取的影像可以儲存為哪些影像格式？

答：您可以將擷取的影像儲存為各種支援的格式。`ImageFormat`枚舉，例如 JPEG、PNG、BMP 等。

#### Q：提取出來的圖片保存到文件後如何使用？

答：提取的圖像可以像任何其他圖像檔案一樣使用。您可以檢視、編輯、共用它們或將它們合併到其他文件或項目中。

#### Q：從 PDF 中提取影像是否會影響原始 PDF 文件的佈局或內容？

答：不會，從 PDF 中提取影像不會影響原始 PDF 文件的佈局或內容。僅提取的影像受到影響。

#### Q：我可以在一個進程中從不同頁面提取多個圖像嗎？

答：是的，您可以使用相同的過程透過迭代不同的頁面索引來從多個頁面中提取圖像。