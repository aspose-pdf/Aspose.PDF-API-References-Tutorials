---
title: 建立多層 PDF 檔案第二種方法
linktitle: 建立多層 PDF 檔案第二種方法
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 建立多層 PDF 檔案。包含原始程式碼的逐步指南，用於建立包含文字和圖像的動態 PDF。
type: docs
weight: 80
url: /zh-hant/net/programming-with-document/createmultilayerpdfsecondapproach/
---
在本教學中，我們將探索如何使用 Aspose.PDF for .NET 中的第二種方法建立多層 PDF 檔案。我們將提供帶有詳細說明的逐步指南，並包含完整的原始程式碼。透過學習本教學課程，您將能夠在 .NET 應用程式中使用 Aspose.PDF 庫產生多層 PDF 文件。

現在，讓我們開始使用逐步指南。

## 第 1 步：設定環境

首先，開啟 Visual Studio 並建立一個新的 C# 專案。請確定您在專案中引用了 Aspose.PDF 庫。設定環境後，您就可以繼續下一步了。

## 第 2 步：初始化變數

在此步驟中，我們將初始化必要的變數。我們需要設定文件目錄的路徑並定義 PDF 圖層的顏色變數。這是程式碼片段：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

int alpha = 10;
int green = 0;
int red = 100;
int blue = 0;
Color alphaColor = Color.FromArgb(alpha, red, green, blue);
```

## 第 3 步：建立 PDF 文檔

接下來，我們將建立 Aspose.Pdf.Document 類別的新實例，它代表一個 PDF 文件。這是程式碼片段：

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## 步驟 4：新增頁面

在此步驟中，我們將向 PDF 文件新增頁面。這是程式碼片段：

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## 第 5 步：為頁面新增文本

現在，我們將向頁面添加一個文字片段。文字將顯示為紅色的第 3 段段。這是程式碼片段：

```csharp
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
t1.TextState.ForegroundColor = Color.Red;
t1.IsInLineParagraph = true;
t1.TextState.FontSize = 12;

Aspose.Pdf.FloatingBox TextFloatingBox1 = new Aspose.Pdf.FloatingBox(117, 21);
TextFloatingBox1.ZIndex = 1;
TextFloatingBox1.Left = -4;
TextFloatingBox1.Top = -4;
page.Paragraphs.Add(TextFloatingBox1);
TextFloatingBox1.Paragraphs.Add(t1);
```

## 第 6 步：將圖像新增至頁面

在此步驟中，我們將向頁面新增圖像。影像將定位為具有特定尺寸的浮動框。這是程式碼片段：

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";

Aspose.Pdf.FloatingBox ImageFloatingBox = new Aspose.Pdf.FloatingBox(117, 21);
page.Paragraphs.Add(ImageFloatingBox);
ImageFloatingBox.Left = -4;
ImageFloatingBox.Top = -4;
ImageFloatingBox.ZIndex = 2;
ImageFloatingBox.Paragraphs.Add(image1);
```

## 第 7 步：儲存 PDF

在此步驟中，我們將 PDF 儲存到文件中。

```
doc.Save(dataDir + @"Multilayer-2ndApproach_out.pdf");
```

### 使用 Aspose.PDF for .NET 建立多層 PDF 第二種方法的範例原始程式碼。

```csharp   
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

int alpha = 10;
int green = 0;
int red = 100;
int blue = 0;
Color alphaColor = Color.FromArgb(alpha, red, green, blue);
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

Aspose.Pdf.Page page = doc.Pages.Add();
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
t1.TextState.ForegroundColor = Color.Red;
t1.IsInLineParagraph = true;
t1.TextState.FontSize = 12;
Aspose.Pdf.FloatingBox TextFloatingBox1 = new Aspose.Pdf.FloatingBox(117, 21);
TextFloatingBox1.ZIndex = 1;
TextFloatingBox1.Left = -4;
TextFloatingBox1.Top = -4;
page.Paragraphs.Add(TextFloatingBox1);
TextFloatingBox1.Paragraphs.Add(t1);
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";
Aspose.Pdf.FloatingBox ImageFloatingBox = new Aspose.Pdf.FloatingBox(117, 21);
page.Paragraphs.Add(ImageFloatingBox);

ImageFloatingBox.Left = -4;
ImageFloatingBox.Top = -4;
ImageFloatingBox.ZIndex = 2;
ImageFloatingBox.Paragraphs.Add(image1);

doc.Save(dataDir + @"Multilayer-2ndApproach_out.pdf");
```

## 結論

在本文中，我們學習如何使用 Aspose.PDF for .NET 的第二種方法建立多層 PDF。我們為您提供了建立多層 PDF 所需的逐步說明和完整原始程式碼。

### 常見問題解答

#### Q：使用 Aspose.PDF for .NET 建立多層 PDF 的第二種方法是什麼？

答：使用 Aspose.PDF for .NET 建立多層 PDF 的第二種方法涉及使用浮動框來定位內容元素（例如文字和圖像）並將其新增至 PDF 文件中的不同圖層。

#### Q：我可以使用第二種方法為 PDF 文件添加兩層以上的圖層嗎？

答：是的，您可以使用第二種方法為 PDF 文件添加多個圖層，即添加更多浮動框並相應地定位它們。每個浮動框代表一個單獨的圖層，您可以為每個框添加內容元素以建立多個圖層。

#### Q：使用第二種方法建立多層 PDF 有什麼好處？

答：第二種方法可以精確控制 PDF 文件中內容元素的位置和可見性。它在管理層和內容安排方面提供了更大的靈活性，使創建複雜的互動式文件變得更加容易。

#### Q：Aspose.PDF for .NET 適合建立複雜的互動式 PDF 文件嗎？

答：是的，Aspose.PDF for .NET 是一個功能強大的函式庫，為建立複雜的互動式 PDF 文件提供了廣泛的功能。它提供了廣泛的功能，例如添加文字、圖像、表格、超連結和表單字段，以及支援高級 PDF 操作。

#### Q：第二種方式可以自訂浮動框的外觀和屬性嗎？

答：是的，您可以自訂浮動框的外觀和屬性，例如浮動框的大小、位置、背景顏色和不透明度。 Aspose.PDF for .NET 提供了各種設定浮動框樣式和定位的選項。