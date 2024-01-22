---
title: 建立多層 PDF 檔案優先方法
linktitle: 建立多層 PDF 第一種方法
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 的第一個方法建立多層 PDF 檔案。添加文字、圖像等以增強您的 PDF。
type: docs
weight: 70
url: /zh-hant/net/programming-with-document/createmultilayerpdffirstapproach/
---
在本教學中，我們將指導您使用第一種方法使用 Aspose.PDF for .NET 建立多層 PDF 檔案的過程。此方法可讓您為 PDF 檔案新增多個圖層。請按照以下逐步指南進行操作：

## 步驟一：初始化PDF文檔

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
```

## 步驟 2：為文件新增頁面

```csharp
Aspose.Pdf.Page sec1 = pdf.Pages.Add();
```

## 步驟 3：為頁面新增文字片段

```csharp
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
sec1.Paragraphs.Add(t1);
```

## 第四步：自訂文字片段

```csharp
t1.Text = "paragraph 3 segment 1";
t1.TextState.ForegroundColor = Color.Red;
t1.TextState.FontSize = 12;
```

## 第 5 步：為頁面新增圖像

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";
```

## 第六步：在頁面中新增浮動框

```csharp
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(117, 21);
sec1.Paragraphs.Add(box1);

box1.Left = -4;
box1.Top = -4;
box1.Paragraphs.Add(image1);
```

## 步驟7：儲存生成的PDF文檔

```csharp
pdf.Save(dataDir + "CreateMultiLayerPdf_out.pdf");
```

恭喜！您已使用第一種方法使用 Aspose.PDF for .NET 成功建立了多層 PDF 文件。

### 使用 Aspose.PDF for .NET 建立多層 PDF 第一種方法的範例原始碼：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
Aspose.Pdf.Page sec1 = pdf.Pages.Add();
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
sec1.Paragraphs.Add(t1);

t1.Text = "paragraph 3 segment 1";
t1.TextState.ForegroundColor = Color.Red;
t1.TextState.FontSize = 12;

Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";

Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(117, 21);
sec1.Paragraphs.Add(box1);

box1.Left = -4;
box1.Top = -4;
box1.Paragraphs.Add(image1);

pdf.Save(dataDir + "CreateMultiLayerPdf_out.pdf");
```

現在，您可以使用第一種方法使用 Aspose.PDF for .NET 建立多層 PDF 文件。

## 結論

在本教學中，我們示範如何使用第一種方法使用 Aspose.PDF for .NET 建立多層 PDF 文件。透過遵循逐步指南並利用提供的 C# 原始程式碼，您可以輕鬆地在 PDF 文件中新增多個圖層。 PDF 文件中的圖層提供了更高的靈活性和互動性，可讓您建立動態和自訂內容。 Aspose.PDF for .NET 為在 .NET 應用程式中處理 PDF 提供了可靠且高效的解決方案，使您能夠輕鬆建立複雜的互動式 PDF 文件。

### 建立多層 PDF 文件優先方法的常見問題解答

#### Q：什麼是多層 PDF 文件？

答：多層 PDF 文檔，也稱為分層 PDF，包含多層內容，可以單獨控制可見度和不透明度。 PDF 文件中的圖層允許使用者選擇性地顯示或隱藏特定的內容元素。

#### Q：如何使用 Aspose.PDF for .NET 將圖層新增至 PDF 文件？

答：您可以使用 Aspose.PDF for .NET 建立浮動框並在這些框中新增內容元素（例如文字和圖像），從而為 PDF 文件添加圖層。每個浮動框可以代表一個單獨的圖層，您可以控制它們在頁面上的可見性和位置。

#### Q：建立多層 PDF 有什麼好處？

答：建立多層 PDF 可以增強文件的靈活性和互動性。圖層可讓您有效地組織和管理內容元素，從而更輕鬆地控制其顯示並建立互動式文件。

#### Q：我可以在 PDF 文件的單一頁面上新增多個圖層嗎？

答：是的，您可以透過建立和定位多個浮動框，將多個圖層新增至 PDF 文件中的單一頁面。每個浮動框可以代表一個單獨的圖層，您可以相應地向每個框添加內容元素。

#### Q：Aspose.PDF for .NET 適合涉及多層 PDF 的專業專案嗎？

答：當然，Aspose.PDF for .NET 是一個強大且功能豐富的函式庫，廣泛用於專業專案中的 PDF 操作，包括建立多層 PDF。它提供了在 .NET 應用程式中處理 PDF 文件的全面功能。