---
title: 提取 PDF 文件中突出顯示的文本
linktitle: 提取 PDF 文件中突出顯示的文本
second_title: Aspose.PDF for .NET API 參考
description: 透過本教學課程，了解如何使用 Aspose.PDF for .NET 從 PDF 檔案中高效提取突出顯示的文字。非常適合數據分析和內容審查。
type: docs
weight: 60
url: /zh-hant/net/annotations/extracthighlightedtext/
---
## 介紹

在處理 PDF 檔案時，提取突出顯示的文字可能是一項至關重要的任務，無論是用於資料分析、內容審查還是只是組織筆記。如果您使用 Aspose.PDF for .NET，此過程非常簡單且有效率。在本教學中，我們將引導您了解如何使用 Aspose.PDF for .NET 從 PDF 文件中提取突出顯示的文字。我們將涵蓋從先決條件到逐步指導的所有內容，確保您最終有全面的了解。

## 先決條件

在深入研究程式碼之前，您需要做好以下幾件事：

-  Aspose.PDF for .NET 函式庫：請確定您已安裝 Aspose.PDF 函式庫。如果沒有，您可以從以下位置下載[發布頁面](https://releases.aspose.com/pdf/net/).
- 開發環境：您應該設定一個有效的開發環境，例如 Visual Studio。
- C# 基礎知識：熟悉 C# 程式語言和物件導向程式設計至關重要。
- 有效的 Aspose 許可證：雖然您可以從免費試用開始，但請考慮獲取[臨時執照](https://purchase.aspose.com/temporary-license/)或從以下網站購買一個[這裡](https://purchase.aspose.com/buy)不受限制地使用。

## 導入包

首先，您需要在 C# 專案中匯入必要的命名空間。這對於存取 Aspose.PDF for .NET 提供的類別和方法至關重要。

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

現在，讓我們分解一下使用 Aspose.PDF for .NET 從 PDF 文件中提取突出顯示文字的過程。每個步驟都進行了詳細解釋，以幫助您理解底層概念和實現。

## 第 1 步：設定您的專案目錄

首先，您需要設定 PDF 檔案所在的專案目錄。這就是奇蹟發生的地方。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`與 PDF 檔案所在目錄的實際路徑。該目錄是應用程式獲取 PDF 進行處理的位置。

## 第 2 步：載入 PDF 文檔

接下來，您需要載入要從中提取突出顯示文字的 PDF 文件。這是使用以下方法完成的`Document`由 Aspose.PDF 提供的類別。

```csharp
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

這`Document`類別使用 PDF 檔案的路徑進行實例化。這裡，`"ExtractHighlightedText.pdf"`是包含突出顯示文字的 PDF 檔案的名稱。確保指定目錄中存在該檔案。

## 第 3 步：存取註釋集合

載入 PDF 文件後，下一步是存取文件第一頁上的註釋。 PDF 中使用註釋來新增附加訊息，例如突出顯示、註釋等。

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
```

這`Annotations`的財產`Page`物件提供對 PDF 特定頁面上所有註釋的存取。在這裡，我們循環遍歷第一頁上的每個註釋。

## 第 4 步：過濾突出顯示的文字註釋

現在我們可以存取所有註釋，我們需要僅過濾掉突出顯示的文字註釋。這是透過檢查每個註釋的類型來實現的。

```csharp
if (annotation is TextMarkupAnnotation)
{
    TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
```

這`TextMarkupAnnotation`類別用於表示文字標記註釋，包括突出顯示。這`is`關鍵字檢查註釋是否屬於類型`TextMarkupAnnotation`，如果是，它將註釋轉換為`TextMarkupAnnotation`.

## 第 5 步：提取突出顯示的文本

識別出突出顯示的註釋後，下一步是提取與突出顯示相關的文字。

```csharp
TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
foreach (TextFragment tf in collection)
{
    Console.WriteLine(tf.Text);
}
```

這`GetMarkedTextFragments()`方法傳回一個集合`TextFragment`對象，每個對象代表突出顯示文字的一部分。我們循環遍歷這個集合並將每個片段的文字列印到控制台。

## 結論

使用 Aspose.PDF for .NET 從 PDF 中提取突出顯示的文字是一項強大的功能，可以簡化您的工作流程，特別是在處理大型文件時。透過遵循本教程中概述的步驟，您可以在自己的專案中輕鬆實現此功能。無論您是組織筆記、準備報告還是進行資料分析，此方法都為提取和利用突出顯示的文字提供了無縫的解決方案。

## 常見問題解答

### 我可以使用此方法提取其他類型的註釋嗎？  
是的，您可以透過修改來提取其他類型的註釋`if`檢查不同註釋類型的條件，例如`TextAnnotation`, `StampAnnotation`， ETC。

### 是否可以從 PDF 的所有頁面中提取突出顯示的文字？  
絕對地！您可以循環瀏覽 PDF 文件的每個頁面，並應用相同的提取邏輯來收集每個頁面中突出顯示的文字。

### 我需要許可證才能使用 Aspose.PDF for .NET 嗎？  
雖然您可以從免費試用開始，但建議您獲取[臨時執照](https://purchase.aspose.com/temporary-license/)或購買完整許可證以不受限制地存取所有功能。

### 我可以將提取的文字儲存到文件中而不是將其列印到控制台嗎？  
是的，您可以輕鬆修改程式碼以將提取的文字儲存到文字檔案或任何其他所需的格式。

### 除了.NET 之外，Aspose.PDF 是否支援其他平台？  
是的，Aspose.PDF 也支援 Java 和其他平台，在不同環境中提供類似的功能。