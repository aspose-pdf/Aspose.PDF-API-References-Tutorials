---
title: 讓頁面內容適合 PDF 文件
linktitle: 讓頁面內容適合 PDF 文件
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 調整 PDF 檔案中頁面內容的詳細逐步指南。易於實施和有益的結論。
type: docs
weight: 50
url: /zh-hant/net/programming-with-pdf-pages/fit-page-contents/
---
在本教學中，我們將引導您完成使用 Aspose.PDF for .NET 調整 PDF 檔案中的頁面內容的逐步流程。我們將解釋捆綁的 C# 原始程式碼，並為您提供全面的指南，幫助您理解並在自己的專案中實現此功能。在本教學結束時，您將了解如何使用 Aspose.PDF for .NET 調整 PDF 頁面的內容。

## 先決條件
在開始之前，請確保您具備以下條件：

- C# 程式語言的基礎知識
- 在您的開發環境中安裝 Aspose.PDF for .NET

## 步驟1：定義文檔目錄
首先，您需要設定文檔目錄的路徑。這是您輸入的 PDF 檔案所在的位置。將“您的文件目錄”替換為適當的路徑。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：載入 PDF 文檔
然後您可以使用以下命令載入 PDF 文檔`Document`Aspose.PDF 類別。請務必指定輸入 PDF 檔案的正確路徑。

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 第三步：調整頁面內容
現在您可以循環瀏覽文件的所有頁面，並根據媒體框的大小調整每個頁面的內容。在提供的範例中，我們調整頁面的寬度，使其以橫向模式（landscape）呈現，並保持相同的高度。新寬度是根據媒體框的長寬比計算的。

```csharp
foreach(Page page in doc.Pages)
{
     Rectangle r = page.MediaBox;
     double newHeight = r.Height;
     double newWidth = r.Height * r.Height / r.Width;
}
```

### 使用 Aspose.PDF for .NET 調整頁面內容的範例原始碼 

```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
foreach (Page page in doc.Pages)
{
	Rectangle r = page.MediaBox;
	//新高度一樣
	double newHeight = r.Height;
	//新寬度按比例擴展以形成方向橫向
	//（我們假設之前的方向是縱向）
	double newWidth = r.Height * r.Height / r.Width;
}          

```

## 結論
在本教學中，我們學習如何使用 Aspose.PDF for .NET 調整 PDF 頁面內容。透過執行上述步驟，您可以在自己的專案中輕鬆實現此功能。請隨意進一步探索 Aspose.PDF 文檔，以發現處理 PDF 文件的其他有用功能。

### PDF 檔案中適合頁面內容的常見問題解答

#### Q：PDF 頁面中的「媒體框」代表什麼？

答：在 PDF 頁面的上下文中，「媒體框」表示定義頁面內容的實體尺寸的邊界框。它定義 PDF 文件中頁面內容的寬度、高度和位置。

#### Q：提供的C#原始碼如何調整頁面內容？

答：提供的 C# 原始程式碼透過調整每個頁面的寬度大小來調整頁面內容，使其以橫向模式顯示，同時保持相同的高度。新的寬度是根據媒體框的長寬比計算的，確保內容保留其原始比例。

#### Q：我可以調整頁面內容以適應特定的尺寸或寬高比嗎？

答：是的，您可以透過修改提供的 C# 原始程式碼中的計算來調整頁面內容以適合特定的尺寸或寬高比。例如，如果您希望將頁面內容調整為固定尺寸（例如，8.5 x 11 英吋），則可以相應地計算新的寬度和高度。

#### Q：調整頁面大小後，頁面內容會發生什麼變化？

A：使用提供的C#原始碼調整頁面大小後，頁面上的內容將按比例調整大小。如果原始內容的寬高比與新的寬高比顯著不同，則內容可能會出現拉伸或壓縮。

#### Q：我可以調整PDF文件中特定頁面的內容而不是所有頁面嗎？

答：是的，您可以調整 PDF 文件中特定頁面的內容，而不是所有頁面的內容。在提供的 C# 原始程式碼中，「foreach」會循環遍歷文件中的所有頁面。若要調整特定頁面的內容，您可以在迴圈中使用條件語句來僅定位所需的頁面。