---
title: 從 PDF 文件中的頁面區域提取文本
linktitle: 從 PDF 文件中的頁面區域提取文本
second_title: Aspose.PDF for .NET API 參考
description: 透過此逐步指南，了解如何使用 Aspose.PDF for .NET 從 PDF 中的特定區域提取文字。有效地收集和保存文件中的文字。
type: docs
weight: 190
url: /zh-hant/net/programming-with-text/extract-text-from-page-region/
---
## 介紹

使用 PDF 通常需要提取特定內容，無論是從表單、表格或文件的某些部分提取資料。在本教學中，我們將介紹如何使用 Aspose.PDF for .NET 從 PDF 的特定區域提取文字。我們無需篩選整個文檔，而是準確定位文字所在的位置並有效地提取它。

## 先決條件

在我們開始編寫程式碼之前，請確保您已準備好以下各項：

1.  Aspose.PDF for .NET：如果您尚未下載並安裝 Aspose.PDF for .NET 程式庫，請下載並安裝。[下載 .NET 版 Aspose.PDF](https://releases.aspose.com/pdf/net/).
2. IDE：任何 .NET 開發環境，例如 Visual Studio。
3. .NET Framework：確保您的專案使用適當的 .NET 框架進行設定。
4. PDF 文件：我們將從中提取文本的範例 PDF。

別忘了你可以[獲得免費試用](https://releases.aspose.com/)Aspose.PDF 或使用[臨時執照](https://purchase.aspose.com/temporary-license/)以獲得完整的功能。

## 導入必要的套件

要開始使用 Aspose.PDF for .NET，您需要將所需的命名空間匯入到您的專案中。這些套件提供了處理 PDF 文件所需的類別和方法。

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

## 第 1 步：設定文檔目錄並載入 PDF

第一步是指定 PDF 文件所在的位置並將其載入到您的專案中。您可以使用您想要使用的 PDF 檔案的本機目錄路徑。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//開啟 PDF 文檔
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

此步驟可確保 PDF 檔案正確載入並準備好進行處理。這`Document`Aspose.PDF 庫中的類別可讓您操作 PDF 檔案。

## 第 2 步：初始化文字吸收器以進行擷取

在這一步中，我們創建一個`TextAbsorber`對象，旨在從 PDF 文件中提取文字。這`TextAbsorber`非常靈活，可以自訂以專注於特定區域或頁面。

```csharp
//建立一個 TextAbsorber 物件來提取文本
TextAbsorber absorber = new TextAbsorber();
```

這`TextAbsorber`class 是一個強大的工具，可以擷取您指定範圍內的所有文字。

## 步驟 3：定義從中提取文字的區域

這就是奇蹟發生的地方。我們可以將提取限制在頁面的特定矩形區域，而不是從整個頁面提取文字。當您確切知道內容所在的位置時，這是完美的。

```csharp
//將文字擷取限製到特定區域
absorber.TextSearchOptions.LimitToPageBounds = true;
absorber.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
```

這`Rectangle`物件允許您定義從中提取文字的區域的座標（以點為單位）。這`TextSearchOptions.LimitToPageBounds`確保僅提取指定矩形內的文字。

## 第 4 步：在所需頁面上接受吸收器

設定區域後，下一步是接受`TextAbsorber`對於您要從中提取文字的特定頁面。在這裡，我們將重點放在 PDF 的第一頁。

```csharp
//接受第一頁的吸收體
pdfDocument.Pages[1].Accept(absorber);
```

透過致電`Accept`頁面上的方法，我們指示 Aspose.PDF 運行吸收器並從定義的區域收集文字。

## 第 5 步：檢索並儲存提取的文本

一旦吸收器完成其工作，就可以收集提取的文字並保存它。此步驟涉及檢索文字並將其寫入`.txt`文件。

```csharp
//獲取提取的文本
string extractedText = absorber.Text;

//建立一個 writer 來保存提取的文本
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");

//將文字寫入文件
tw.WriteLine(extractedText);

//關閉流
tw.Close();
```

在這裡，`TextWriter`類別用於將提取的文字寫入文字檔案。這可確保您提取的內容安全儲存以供以後使用。

## 結論

從 PDF 文件中的特定區域提取文字非常有用，尤其是在處理表單或表格等結構化內容時。使用Aspose.PDF for .NET，您只需幾行程式碼即可完成此任務。透過定義一個區域，初始化一個`TextAbsorber`，並保存提取的文本，您可以完全控制從 PDF 中提取的內容。

無論您是處理小型專案還是管理大型文檔，此方法都提供了一種從 PDF 中提取相關資料的有效方法，而無需梳理整個文檔。

## 常見問題解答

### 我可以同時從多個頁面中提取文字嗎？
是的，透過迭代`Pages`的集合`pdfDocument`，您可以應用`TextAbsorber`到多個頁面。

### 如果文字位於 PDF 的不同區域怎麼辦？
您可以輕鬆調整`Rectangle`座標以匹配文字所在的區域。

### 這適用於掃描的 PDF 嗎？
不可以，掃描的 PDF 需要 OCR（光學字元辨識）將影像轉換為文字。 Aspose.PDF 也提供 OCR 功能。

### 有沒有辦法根據特定關鍵字提取文字？
是的，您可以使用`TextFragmentAbsorber`用於基於關鍵字的文字提取。

### 如何從加密的 PDF 中提取文字？
您需要先透過提供正確的密碼來解密 PDF，然後繼續提取文字。