---
title: 設定 PDF 檔案中的圖像大小
linktitle: 設定 PDF 檔案中的圖像大小
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 設定 PDF 檔案中影像大小的逐步指南。
type: docs
weight: 270
url: /zh-hant/net/programming-with-images/set-image-size/
---
在本教學中，我們將引導您了解如何使用 Aspose.PDF for .NET 設定 PDF 檔案中影像的大小。請按照以下步驟輕鬆執行此操作。

## 先決條件

在開始之前，請確保您具備以下條件：

- 安裝並設定 Visual Studio 或任何其他開發環境。
- C# 程式語言的基礎知識。
- 安裝了適用於.NET 的 Aspose.PDF 庫。您可以從Aspose官方網站下載。

## 第 1 步：建立 PDF 文檔

首先，使用以下程式碼建立一個新的 PDF 文件：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//實例化一個文檔對象
Document doc = new Document();

//將頁面新增到 PDF 檔案的頁面集合中
Aspose.Pdf.Page page = doc.Pages.Add();
```

## 第二步：新增圖片

接下來，我們將向 PDF 文件的頁面新增圖像。使用以下程式碼：

```csharp
//建立圖像實例
Aspose.Pdf.Image img = new Aspose.Pdf.Image();

//設定影像的寬度和高度（以磅為單位）
img. FixWidth = 100;
img. FixHeight = 100;

//將影像類型設為未知（Unknown）
img.FileType = Aspose.Pdf.ImageFileType.Unknown;

//影像來源檔案的路徑
img.File = dataDir + "aspose-logo.jpg";

//將圖像加入頁面的段落集合中
page.Paragraphs.Add(img);
```

請務必提供影像來源檔案的正確路徑。

## 步驟 3：設定頁面屬性

最後，我們將設定頁面的屬性，包括其寬度和高度。使用以下程式碼：

```csharp
//設定頁面屬性
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```

### 使用 Aspose.PDF for .NET 設定圖片大小的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//實例化文檔對象
Document doc = new Document();
//將頁面新增至 PDF 檔案的頁面集合
Aspose.Pdf.Page page = doc.Pages.Add();
//建立圖像實例
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
//設定影像寬度和高度（以磅為單位）
img.FixWidth = 100;
img.FixHeight = 100;
//將圖像類型設定為 SVG
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
//來源檔案路徑
img.File = dataDir + "aspose-logo.jpg";
page.Paragraphs.Add(img);
//設定頁面屬性
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
dataDir = dataDir + "SetImageSize_out.pdf";
//儲存生成的 PDF 文件
doc.Save(dataDir);
Console.WriteLine("\nImage size added successfully.\nFile saved at " + dataDir);
```

## 結論

恭喜！您已使用 Aspose.PDF for .NET 成功設定 PDF 文件中影像的大小。現在您可以將此方法套用到您自己的專案中，以調整 PDF 檔案中圖像的大小。

### 在 PDF 檔案中設定影像尺寸的常見問題解答

#### Q：使用 Aspose.PDF for .NET 設定 PDF 文件中影像的大小的目的是什麼？

答：設定PDF文件中影像尺寸的目的是為了控制影像加入PDF時的尺寸。這允許您調整 PDF 文件中圖像的外觀和佈局。

#### Q：在 PDF 文件中如何設定影像尺寸？

答：該過程涉及創建一個`Aspose.Pdf.Image`實例，使用指定其寬度和高度`FixWidth`和`FixHeight`屬性，然後將圖像新增至 PDF 文件。此外，您可以設定頁面本身的尺寸以容納圖像。

#### Q：我可以將圖像的大小設定為頁面尺寸的特定百分比嗎？

答：提供的程式碼設定影像的絕對寬度和高度（以磅為單位）。如果您想根據頁面尺寸的百分比設定圖像的尺寸，則需要相應地計算尺寸並相應地調整程式碼。

#### 問： 其意義何在？`FileType` property when adding an image to the PDF document?

答： 的`FileType`屬性指定新增至 PDF 文件中的影像的類型。在提供的程式碼中，值`Unknown`表示影像類型未知，Aspose.PDF 將嘗試根據檔案副檔名確定影像類型。

#### Q：我可以使用此方法將多個圖像新增至單一頁面嗎？

答：是的，您可以透過建立多個影像將多個影像新增至單一頁面`Aspose.Pdf.Image`實例並將它們新增至頁面的段落集合中。確保根據需要調整影像的位置和佈局。

#### Q：如何控制頁面上新增的影像的位置和對齊方式？

答：可以透過使用以下屬性調整影像的座標和佈局來控制新增的影像的放置和對齊：`img.Left`, `img.Top`和段落格式屬性。

####  Q：使用設定頁面屬性的目的是什麼？`page.PageInfo.Width` and `page.PageInfo.Height`?

答：設定頁面屬性可讓您定義頁面本身的尺寸。這可確保頁面尺寸適應添加的圖像以及頁面上可能有的任何其他內容。

#### Q：我可以為同一個 PDF 文件中的不同影像設定不同的尺寸嗎？

答：是的，您可以透過建立單獨的影像來為不同的影像設定不同的尺寸`Aspose.Pdf.Image`實例並調整`FixWidth`, `FixHeight`，以及每個影像的放置屬性。

#### Q：如何將此方法整合到我自己的專案中以設定 PDF 文件中的圖像尺寸？

答：要將此方法整合到您的專案中，請按照概述的步驟操作並根據需要修改程式碼。您可以使用此方法根據應用程式的要求將特定尺寸的圖像新增至 PDF 文件中。