---
title: 使用標記圖像建立 PDF
linktitle: 使用標記圖像建立 PDF
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 建立標記影像的 PDF 的逐步指南。
type: docs
weight: 40
url: /zh-hant/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
在本教學中，我們將為您提供如何使用 Aspose.PDF for .NET 建立帶有標記影像的 PDF 文件的逐步指南。 Aspose.PDF 是一個功能強大的程式庫，可讓您以程式設計方式建立、操作和轉換 PDF 文件。使用Aspose.PDF的標記內容結構功能，您可以將標記影像新增至PDF文件中。

## 先決條件

在開始之前，請確保您具備以下先決條件：

1. 隨 .NET Framework 安裝的 Visual Studio。
2. 適用於 .NET 的 Aspose.PDF 庫。

## 第 1 步：項目設置

首先，在 Visual Studio 中建立一個新專案並新增對 Aspose.PDF for .NET 程式庫的參考。您可以從Aspose官方網站下載該程式庫並將其安裝到您的電腦上。

## 第 2 步：導入必要的命名空間

在您的 C# 程式碼檔案中，匯入存取 Aspose.PDF 提供的類別和方法所需的命名空間：

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## 步驟 3：建立帶有標記影像的 PDF 文檔

使用以下程式碼建立帶有標記影像的 PDF 文件：

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Creating a PDF with a tagged image");
taggedContent.SetLanguage("fr-FR");

IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Picture 1";
figure1.SetTag("Fig");
figure1.SetImage(dataDir + @"aspose-logo.jpg");
```

此程式碼建立一個空 PDF 文檔，並使用 Aspose.PDF 提供的方法新增標記影像。此圖像由替代文字、標題和標籤指定。

## 步驟 4：儲存 PDF 文檔

使用以下程式碼儲存PDF文件：

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

此程式碼將帶有標記影像的 PDF 文件儲存到指定文件中。

### 使用 Aspose.PDF for .NET 建立標記影像的 PDF 的範例原始碼 
```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("CreatePDFwithTaggedImage");
taggedContent.SetLanguage("en-US");
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Image 1";
figure1.SetTag("Fig");
//新增解析度為 300 DPI 的影像（預設）
figure1.SetImage(dataDir + @"aspose-logo.jpg");
//儲存 PDF 文件
document.Save(dataDir + "PDFwithTaggedImage.pdf");

```

## 結論

在本教學中，您學習如何使用 Aspose.PDF for .NET 建立帶有標記影像的 PDF 文件。帶有標籤的圖像會為您的 PDF 文件添加附加的結構化資訊。

### 常見問題解答

#### Q：使用 Aspose.PDF for .NET 建立標記影像的 PDF 文件的目的是什麼？

答：使用 Aspose.PDF for .NET 建立標記影像的 PDF 文件可讓您將標記影像新增至文件的內容。標記圖像提供結構化訊息，例如替代文字和標題，從而增強可訪問性和組織性。

#### Q：Aspose.PDF 庫如何協助建立標記影像的 PDF 文件？

答：Aspose.PDF for .NET 是一個強大的函式庫，提供以程式設計方式建立、操作和轉換 PDF 文件的功能。在本教學中，庫的標記內容結構功能用於將標記影像新增至 PDF 文件。

#### Q：使用 Aspose.PDF for .NET 建立帶有標記影像的 PDF 文件有哪些先決條件？

答：開始之前，請確保您已安裝了具有 .NET 框架的 Visual Studio，並在專案中引用了適用於 .NET 的 Aspose.PDF 程式庫。

#### Q：提供的 C# 程式碼如何建立帶有標記圖像的 PDF 文件？

答：程式碼示範如何建立 PDF 文件、定義標記影像元素並將其新增至文件內容。帶有標籤的圖像包括替代文字、標題和使用 Aspose.PDF 提供的方法的標籤。

#### Q：我可以為標記的圖像使用不同的圖像格式嗎？

答：是的，您可以為標記的圖像使用不同的圖像格式，例如 JPEG、PNG、GIF 等。首選格式。

#### Q：如何在標記圖像中使用替代文字（alt text）？

答：替代文字提供圖像的文字描述，由螢幕閱讀器為視障用戶大聲朗讀。在提供的程式碼中，替代文字是使用`AlternativeText`的財產`IllustrationElement`代表標記圖像。

#### 問：如何`SetTitle` method contribute to the PDF document's tagged image?

答： 的`SetTitle`方法設定 PDF 文件標記內容的標題，為標記影像提供附加上下文。此標題可以幫助識別標記內容的目的或主題。

#### Q：我可以自訂標記圖像的標籤和標題嗎？

答：是的，您可以使用以下命令自訂標記圖像的標籤和標題`SetTag`和`Title`的方法`IllustrationElement`。此程式碼範例示範如何將標籤設為「Fig」並將標題設為「Picture 1」。

#### Q：如何確保標記的圖像可存取並符合可訪問性標準？

答：透過使用 Aspose.PDF 的標記內容結構功能並提供替代文字和其他相關信息，您可以為標記圖像的可訪問性做出貢獻。確保符合輔助功能標準涉及遵循替代文字和文件結構的最佳實踐。

#### Q：是否可以使用類似的技術將多個標記影像新增到同一個 PDF 文件中？

答：是的，您可以使用類似的技術將多個標記影像新增到同一個 PDF 文件中。您將創建額外的`IllustrationElement`每個標記圖像的實例並根據需要自訂其屬性。