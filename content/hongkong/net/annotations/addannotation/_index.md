---
title: 新增 PDF 註釋
linktitle: 新增註釋
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用此 C# 原始程式碼透過 Aspose.PDF for .NET 新增文字 PDF 註解。使用特定的細節和圖示自訂您的註釋。
type: docs
weight: 10
url: /zh-hant/net/annotations/addannotation/
---
在 PDF 文件中添加註釋是一項強大的功能，可增強協作和審閱流程。 Aspose.PDF for .NET 可以輕鬆地使用 C# 以程式設計方式為 PDF 文件新增註解。在本指南中，我們將逐步解釋如何使用 Aspose.PDF for .NET 在 PDF 文件中新增註解。

## 步驟 1：建立一個新專案並安裝 Aspose.PDF for .NET

在開始編寫新增註解的程式碼之前，我們需要建立一個新專案並安裝 Aspose.PDF for .NET。若要安裝 Aspose.PDF for .NET，請依照下列步驟操作：

1. 開啟 Visual Studio 並建立一個新的 C# 專案。
2. 在解決方案資源管理器中以滑鼠右鍵按一下該項目，然後選擇「管理 NuGet 套件」。
3. 搜尋“Aspose.PDF”並選擇“安裝”。

安裝完成後，我們就可以開始寫程式碼了。

## 第 2 步：開啟 PDF 文檔

新增註解的第一步是開啟 PDF 文件。我們可以使用下面的程式碼來開啟該文件：

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");
```

在此程式碼中，我們指定要開啟的 PDF 文件的路徑。確保將“您的資料目錄”替換為資料目錄的實際路徑。

## 第 3 步：建立註釋

要新增註釋，我們需要建立一個新的實例`TextAnnotation`班級。我們可以使用以下程式碼來建立新的文字註解：

```csharp
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;
```

在此程式碼中，我們在 PDF 文件的第二頁上建立一個新的文字註解。我們也設定註釋的標題、主題、狀態、內容、開啟和圖示屬性。

## 第 4 步：自訂註釋

我們可以使用以下命令自訂註解的外觀`Border`班級。我們可以使用下面的程式碼來自訂註解的邊框：

```csharp
Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);
```

在此程式碼中，我們建立一個新的`Border`物件並設定其寬度和虛線屬性。然後我們設定`Border`新註釋的屬性`Border`目的。最後，我們設定`Rect`註釋的屬性來指定其位置和大小。

## 第 5 步：將註釋新增至 PDF 文檔

建立並自訂註釋後，我們需要將其新增至 PDF 文件中。我們可以使用以下程式碼為PDF文檔新增註解：

```csharp
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

在此程式碼中，我們將註解新增到 PDF 文件第二頁的註解集合中。

## 第 6 步：儲存輸出文件

最後，我們需要儲存新增了註釋的 PDF 文件。我們可以使用以下程式碼來保存輸出檔：

```csharp
dataDir = dataDir + "AddAnnotation_out.pdf";
pdfDocument.Save(dataDir);
```
### 使用 Aspose.PDF for .NET 新增註解的範例原始程式碼


```csharp   
 //文檔目錄的路徑。
string dataDir = "YOUR DATA DIRECTORY";

//開啟文件
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");

//建立註釋
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;

Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);

//在頁面的註釋集合中加入註釋
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddAnnotation_out.pdf";
//儲存輸出檔案
pdfDocument.Save(dataDir);
```
此程式碼示範如何使用 Aspose.PDF for .NET 將具有特定標題、主題、狀態、內容和圖示的文字註解新增至 PDF 頁面。您可以根據您的要求修改此程式碼，以便在 PDF 文件中新增註解。只需記住將 YOUR DATA DIRECTORY 替換為 PDF 文件所在的實際目錄路徑以及要保存輸出文件的位置。

## 結論

使用 Aspose.PDF for .NET 為 PDF 文件新增註解為增強文件協作和審閱流程提供了寶貴的工具。透過遵循本文提供的逐步指南，開發人員可以將註釋功能無縫整合到他們的 C# 應用程式中。

### 常見問題解答

#### Q：使用 Aspose.PDF for .NET 可以新增哪些類型的註解？

答：Aspose.PDF for .NET 支援各種類型的註釋，包括文字註釋、圖章、連結、形狀等。開發人員可以自訂這些註釋的外觀和屬性以滿足他們的特定需求。

#### Q：我可以為多頁 PDF 文件中的特定頁面添加註解嗎？

答：是的，Aspose.PDF for .NET 允許您指定要新增註解的頁面。您可以根據需要選擇特定頁面或為多個頁面新增註釋。

#### Q：如何自訂註解的外觀？

答：可以使用邊框寬度、顏色、破折號樣式、文字樣式等屬性來自訂註解。 Aspose.PDF for .NET 提供了一組豐富的選項來自訂註解的外觀。

#### Q：是否可以使用 Aspose.PDF for .NET 新增超連結作為註解？

答：是的，您可以使用 Aspose.PDF for .NET 將超連結作為註解新增至 PDF 文件中。超連結註解可用於連結到外部 URL 或同一文件中的特定位置。

#### Q：可以在不改變原始內容的情況下為現有 PDF 文件添加註解嗎？

答：是的，Aspose.PDF for .NET 會新增註解作為附加元素，而不改變 PDF 文件的原始內容。原始 PDF 內容保持不變。