---
title: 在 PDF 檔案中套用數字樣式
linktitle: 在 PDF 檔案中套用數字樣式
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 將編號樣式套用至 PDF 檔案中的標題。一步步指導。
type: docs
weight: 10
url: /zh-hant/net/programming-with-headings/apply-number-style/
---
在本教學中，我們將引導您逐步完成以下 C# 原始程式碼，以使用 Aspose.PDF for .NET 在 PDF 檔案中套用編號樣式。

在開始之前，請確保您已經安裝了 Aspose.PDF 庫並設定了開發環境。也具備 C# 程式設計的基礎知識。

### 第 1 步：文檔目錄設置

在提供的原始程式碼中，您需要指定要儲存產生的PDF檔案的目錄。將“dataDir”變數變更為所需的目錄。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### 第 2 步：建立 PDF 文檔

我們建立一個具有指定尺寸和邊距的新 PDF 文件。

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

### 第三步：建立頁面和浮動容器

我們為文件新增一個頁面並建立一個浮動容器來組織內容。

```csharp
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
```

### 步驟 4：新增編號的標題

我們建立具有指定編號的標頭並將它們新增至浮動容器中。

```csharp
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading. IsInList = true;
heading. StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading. IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);

Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "Listing 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);

Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "The value, at the effective date of the plan, of the assets to be distributed under the plan

";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
```

### 第5步：儲存PDF文檔

我們將產生的PDF文件保存在指定目錄中。

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style successfully applied to headers.\nFile saved as: " + dataDir);
```

### 使用 Aspose.PDF for .NET 應用數字樣式的範例原始碼 
```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
TextFragment textFragment = new TextFragment();
TextSegment segment = new TextSegment();
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading.IsInList = true;
heading.StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "List 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "the value, as of the effective date of the plan, of property to be distributed under the plan onaccount of each allowed";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumber style applied successfully in headings.\nFile saved at " + dataDir);  
          
```

## 結論

在本教學中，我們說明如何使用 Aspose.PDF for .NET 將編號樣式套用至 PDF 文件中的標題。現在，您可以使用這些知識來建立具有自訂標題編號的 PDF 文件。

### 在 PDF 檔案中套用數位樣式的常見問題解答

#### Q：PDF 文件中的編號樣式是什麼？

答：編號樣式是指 PDF 文件中標題或章節的編號格式。它可以包括數字、字母或其他字元以提供分層結構。

#### Q：為什麼我需要對 PDF 文件中的標題套用編號樣式？

答：對標題套用編號樣式可以增強 PDF 文件的可讀性和組織性。它可以幫助讀者輕鬆導航和理解內容的層次結構。

#### Q：什麼是 Aspose.PDF for .NET？

答：Aspose.PDF for .NET 是一個函式庫，可讓開發人員在 .NET 應用程式中以程式設計方式處理 PDF 檔案。它提供了用於建立、編輯、轉換和操作 PDF 文件的廣泛功能。

#### Q：如何導入 C# 專案所需的庫？

答：要匯入 C# 專案所需的函式庫，請包含以下導入指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

這些指令使您能夠存取處理 PDF 文件和套用編號樣式所需的類別和方法。

#### Q：如何指定產生的PDF檔案的保存目錄？

答：在提供的原始程式碼中，修改「dataDir」變數以指定要儲存產生的PDF檔案的目錄。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

代替`"YOUR DOCUMENTS DIRECTORY"`與實際的目錄路徑。

#### Q：如何建立具有指定尺寸和邊距的 PDF 文件？

答：要建立具有指定尺寸和邊距的 PDF 文檔，請使用以下程式碼：

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

#### Q：如何在 PDF 文件中新增編號樣式的標題？

答：若要為 PDF 文件新增編號樣式的標題，請使用提供的程式碼範例建立標題並自訂其編號樣式。根據需要調整文字、編號樣式、起始編號和自動序列等屬性。

#### Q：產生的PDF文件如何保存？

答：若要儲存產生的 PDF 文檔，請使用`Save`的方法`pdfDoc`目的：

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style applied to headers.\nFile saved as: " + dataDir);
```

#### Q：如何確認編號樣式已套用？

答：開啟產生的 PDF 檔案以驗證指定的編號樣式是否已套用至標題。

#### Q：我可以進一步自訂編號樣式嗎？

 A：是的，您可以透過調整編號的屬性來進一步自訂編號樣式`Heading`對象，例如編號樣式類型、起始編號和自動序列。

#### Q：我可以對文件的不同部分套用不同的編號樣式嗎？

答：是的，您可以透過建立多個編號將不同的編號樣式套用至文件的不同部分`Heading`具有不同樣式和順序的物件。