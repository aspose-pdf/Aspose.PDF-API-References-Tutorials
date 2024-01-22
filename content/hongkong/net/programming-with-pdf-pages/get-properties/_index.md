---
title: 取得 PDF 屬性
linktitle: 取得 PDF 屬性
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 取得 PDF 屬性（例如框尺寸和旋轉）的逐步指南。
type: docs
weight: 100
url: /zh-hant/net/programming-with-pdf-pages/get-properties/
---
在本教學中，我們將引導您逐步完成使用 Aspose.PDF for .NET 取得 PDF 屬性的過程。我們將解釋捆綁的 C# 原始程式碼，並為您提供全面的指南，幫助您理解並在自己的專案中實現此功能。在本教學結束時，您將了解如何使用 Aspose.PDF for .NET 存取 PDF 頁面的不同屬性，例如藝術框、裁切框、裁切框等。

## 先決條件
在開始之前，請確保您具備以下條件：

- C# 程式語言的基礎知識
- 在您的開發環境中安裝 Aspose.PDF for .NET

## 步驟1：設定文檔目錄
首先，您需要設定文檔目錄的路徑。這是您要取得其屬性的 PDF 檔案的位置。將“您的文件目錄”替換為適當的路徑。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步驟 2：開啟 PDF 文檔
接下來，您需要使用以下命令開啟 PDF 文檔`Document`Aspose.PDF 類別。請務必指定 PDF 檔案的正確路徑。

```csharp
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

## 第 3 步：訪問頁面集合
現在您可以使用以下命令存取文件的頁面集合`Pages`的財產`pdfDocument`目的。

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## 第四步：進入指定頁面
然後，您可以使用集合中頁面的索引跳到特定頁面。在下面的範例中，我們造訪第二頁（索引 1）。

```csharp
Page pdfPage = pageCollection[1];
```

## 第5步：取得頁面屬性
現在您可以透過使用PDF頁面的相應屬性來取得PDF頁面的不同屬性，例如藝術框，裁剪框，裁剪框等`pdfPage`目的。

```csharp
Console.WriteLine("ArtBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
Console.WriteLine("BleedBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.BleedBox.Height, pdf

Page.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
Console.WriteLine("CropBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
Console.WriteLine("MediaBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
Console.WriteLine("TrimBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
Console.WriteLine("Rect: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
Console.WriteLine("Page number: {0}", pdfPage.Number);
Console.WriteLine("Rotate: {0}", pdfPage.Rotate);
```

### 使用 Aspose.PDF for .NET 取得屬性的範例原始碼 

```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開啟文件
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
//取得頁面集合
PageCollection pageCollection = pdfDocument.Pages;
//取得特定頁面
Page pdfPage = pageCollection[1];
//取得頁面屬性
System.Console.WriteLine("ArtBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
System.Console.WriteLine("BleedBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.BleedBox.Height, pdfPage.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
System.Console.WriteLine("CropBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
System.Console.WriteLine("MediaBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
System.Console.WriteLine("TrimBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
System.Console.WriteLine("Rect : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
System.Console.WriteLine("Page Number : {0}", pdfPage.Number);
System.Console.WriteLine("Rotate : {0}", pdfPage.Rotate);

```

## 結論
恭喜！您已使用 Aspose.PDF for .NET 成功取得 PDF 的屬性。您學習如何開啟 PDF 文件、導覽至特定頁面以及取得各種頁面屬性，例如尺寸方塊和旋轉。現在，您可以使用此資訊根據 PDF 文件的屬性自訂 PDF 文件的處理方式。

請務必查看官方 Aspose.PDF for .NET 文檔，以取得更多有關高級功能和自訂可能性的資訊。

### 常見問題解答

#### Q：如何使用 Aspose.PDF for .NET 取得 PDF 的屬性？

答：要使用 Aspose.PDF for .NET 取得 PDF 的屬性，您可以依照下列步驟操作：

1. 透過指定要檢索其屬性的 PDF 檔案的路徑來設定文件目錄。
2. 使用以下命令開啟 PDF 文檔`Document` Aspose.PDF 類，提供 PDF 檔案的正確路徑。
3. 使用以下命令存取文件的頁面集合`Pages`的財產`pdfDocument`目的。
4. 使用集合中頁面的索引跳到特定頁面（索引從1開始）。
5. 透過使用 PDF 頁面的相應屬性來取得 PDF 頁面的不同屬性，例如 ArtBox、BleedBox、CropBox、MediaBox、TrimBox、Rect、Page Number 和 Rotation`pdfPage`目的。

#### Q：使用 Aspose.PDF for .NET 可以擷取的 PDF 頁面有哪些不同屬性？

答：您可以使用 Aspose.PDF for .NET 來擷取 PDF 頁面的各種屬性，例如：

- ArtBox：表示頁面藝術品的尺寸。
- BleedBox：表示頁面出血的尺寸。
- CropBox：表示裁切後頁面可見內容的尺寸。
- MediaBox：表示頁面實體媒體的尺寸。
- TrimBox：表示頁面修剪內容的尺寸。
- 矩形：表示頁面邊框的尺寸。
- 頁碼：表示文件中的頁碼。
- Rotate：表示頁面的旋轉角度。

#### Q：如何存取 PDF 文件中的特定頁面以檢索其屬性？

答：要存取 PDF 文件中的特定頁面並檢索其屬性，您可以使用`Pages`的財產`pdfDocument`物件來存取文件的頁面集合。然後，您可以使用集合中頁面的索引來跳到所需的頁面。例如，要存取第二頁，您可以使用`pdfDocument.Pages[1]`（索引從1開始）。

#### Q：我可以對檢索到的屬性執行操作，例如修改頁框或調整頁框大小嗎？

答：是的，一旦您使用 Aspose.PDF for .NET 檢索 PDF 頁面的屬性，您就可以對它們執行各種操作。例如，您可以修改頁面框的尺寸、旋轉頁面或使用檢索到的信息對 PDF 文件進行自訂處理和操作。

#### Q：Aspose.PDF for .NET 支援從加密或受密碼保護的 PDF 檔案中提取屬性嗎？

答：是的，Aspose.PDF for .NET 支援從加密或受密碼保護的 PDF 檔案中提取屬性。只要您提供正確的密碼來開啟 PDF 文檔，您就可以使用教學中示範的相同方法存取和檢索其屬性。