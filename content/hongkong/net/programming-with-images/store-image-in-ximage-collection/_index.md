---
title: 將影像儲存在 XImage 集合中
linktitle: 將影像儲存在 XImage 集合中
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 在 XImage 集合中儲存影像的逐步指南。
type: docs
weight: 290
url: /zh-hant/net/programming-with-images/store-image-in-ximage-collection/
---
在本教學中，我們將引導您了解如何使用 Aspose.PDF for .NET 在 XImage 集合中儲存影像。請按照以下步驟輕鬆執行此操作。

## 先決條件

在開始之前，請確保您具備以下條件：

- 安裝並設定 Visual Studio 或任何其他開發環境。
- C# 程式語言的基礎知識。
- 安裝了適用於.NET 的 Aspose.PDF 庫。您可以從Aspose官方網站下載。

## 步驟1：PDF文檔初始化

首先，使用以下程式碼初始化一個新的 PDF 文件：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//初始化文檔
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
```

## 步驟 2：將影像加入 XImage 集合中

接下來，我們將影像新增到 PDF 文件的 XImage 集合中。使用以下程式碼：

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
```

請務必提供影像來源檔案的正確路徑。

## 步驟 3：將圖像放置在頁面上

現在讓我們將圖像放置在 PDF 文件的頁面上。使用以下程式碼：

```csharp
page. Contents. Add(new GSave());

//設定座標
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});

//使用 ConcatenateMatrix 運算子：定義映像的放置方式
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page. Contents. Add(new GRestore());
```

這會將圖像放置在頁面上的指定座標處。

## 步驟 4：儲存 PDF 文檔

最後，我們將儲存更新後的 PDF 文件。使用以下程式碼：

```csharp
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

請務必提供最終 PDF 文件所需的路徑和檔案名稱。

### 使用 Aspose.PDF for .NET 在 XImage Collection 中儲存影像的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//初始化文檔
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new GSave());
//設定座標
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});
//使用ConcatenateMatrix（連接矩陣）運算子：定義影像的放置方式
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page.Contents.Add(new GRestore());
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

## 結論

恭喜！您已使用 Aspose.PDF for .NET 成功將影像儲存在 XImage 集合中。現在您可以將此方法應用到您自己的專案中，以操作和個性化 PDF 文件中的圖像。

### 常見問題解答

#### Q：使用 Aspose.PDF for .NET 在 XImage 集合中儲存影像的目的為何？

答：將影像儲存在 XImage 集合中可以讓您有效地管理和使用 PDF 文件中的影像。這種方法使您能夠在將圖像放置到特定頁面之前對其進行操作、自訂和個性化。

#### Q：在 XImage 集合中儲存影像與直接將影像放置在 PDF 頁面上有何不同？

答：將影像儲存在 XImage 集合中提供了一種更有組織性和可重複使用性的影像管理方式。您無需將圖像直接放置在頁面上，而是將其儲存在集合中，然後可以在需要時透過名稱引用它，從而更輕鬆地管理和修改。

#### Q：我可以在單一 PDF 文件中將多個影像新增到 XImage 集合中嗎？

答：是的，您可以將多個影像新增至同一 PDF 文件中的 XImage 集合中。每個圖像在集合中都被分配了一個唯一的名稱，可用於引用圖像並將圖像放置在不同的頁面上。

#### Q：將 XImage 集合中的影像放置到 PDF 頁面上時，如何指定影像的位置和大小？

A：要指定影像的位置和大小，需要定義一個矩形和一個矩陣變換。矩形定義影像的邊界，矩陣變換指定影像應如何放置在該矩形內。

####  Q：這樣做的目的是什麼`GSave()` and `GRestore()` operators in the code for placing the image?

答： 的`GSave()`和`GRestore()`運算符用於儲存和恢復PDF頁面的圖形狀態。這樣可以確保在頁面上執行的操作（例如放置圖像）不會影響圖像放置後頁面的狀態。

#### Q：我可以對 XImage 集合中儲存的圖像應用其他修改或轉換嗎？

答：是的，您可以對 XImage 集合中儲存的影像套用各種修改和轉換。您可以使用 Aspose.PDF for .NET 提供的適當操作和技術來旋轉、縮放、裁剪和執行其他轉換。

#### Q：如何將此方法整合到我自己的專案中，以在 PDF 文件的 XImage 集合中儲存和放置圖像？

答：要整合此方法，請按照概述的步驟操作並修改程式碼以滿足您的專案要求。您可以使用 XImage 集合來儲存和管理映像，然後使用指定的座標和轉換將它們放置在特定頁面上。

#### Q：在 Aspose.PDF for .NET 中使用 XImage 集合時是否有任何注意事項或限制？

答：雖然 XImage 集合提供了一種強大的方法來管理和操作影像，但考慮記憶體使用情況和對影像執行的操作的複雜性等因素也很重要。建議仔細管理收集並有效利用資源。

#### Q：我可以在多個 PDF 文件中重複使用 XImage 集合中儲存的圖像嗎？

答：XImage 集合特定於每個 PDF 文檔，並不是為跨文檔重複使用而設計的。如果您需要在多個文件中重複使用影像，則需要為每個文件單獨儲存和管理它們。