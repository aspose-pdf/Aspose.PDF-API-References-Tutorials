---
title: 搜尋並取得 PDF 文件中的文字頁面
linktitle: 搜尋並取得 PDF 文件中的文字頁面
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 從 PDF 檔案中的特定頁面搜尋和取得文字。
type: docs
weight: 430
url: /zh-hant/net/programming-with-text/search-and-get-text-page/
---
## 介紹

您是否曾經發現自己需要在 PDF 文件中搜尋特定文字並將其提取以供進一步使用？也許您正在建立一個處理文件並需要精確資料提取的應用程序，或者您可能只需要有效地解析 PDF。無論您的情況如何，您都來對地方了！在本教學中，我們將深入研究如何使用 Aspose.PDF for .NET 從 PDF 檔案的頁面中搜尋和取得文字。無論您是初學者還是經驗豐富的開發人員，本指南都將以對話式且引人入勝的方式引導您完成每個步驟。準備好了嗎？讓我們開始吧！

## 先決條件

在我們開始編碼之前，讓我們確保您擁有所需的一切：

1.  Aspose.PDF for .NET Library：您可以從以下位置下載：[這裡](https://releases.aspose.com/pdf/net/)或從同一連結取得免費試用版。如欲購買，請前往[阿斯普斯商店](https://purchase.aspose.com/buy).
2. .NET Framework：您需要一個有效的 .NET 開發環境，例如 Visual Studio。
3. PDF 文件：您需要一個範例 PDF 文件，我們可以在其中搜尋和提取文字。對於本教程，我們假設該檔案名為`SearchAndGetTextPage.pdf`.

## 導入包

首先，我們需要匯入必要的命名空間以使用 Aspose.PDF for .NET。確保這些包含在程式碼的頂部。

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System
```

現在我們已經介紹了先決條件，讓我們逐步分解程式碼。每個步驟都已清晰概述，以便於遵循。

## 第 1 步：設定文檔目錄的路徑

在與 PDF 互動之前，您需要定義 PDF 文件的儲存路徑。這確保了程式可以存取該文件。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  dataDir：這是儲存 PDF 檔案的資料夾的路徑。代替`"YOUR DOCUMENT DIRECTORY"`與 PDF 所在的實際路徑。

## 第 2 步：載入 PDF 文檔

下一步是將 PDF 文件載入到記憶體中，以便您可以使用它。方法如下：

```csharp
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

- Document：這是載入 PDF 檔案的 Aspose.PDF 類別。
- pdfDocument：PDF 文件載入後儲存位置的變數。

## 第 3 步：建立文字吸收器對象

這`TextFragmentAbsorber`類別允許您在 PDF 中搜尋特定文字。讓我們建立此類的一個實例來尋找給定搜尋字詞的所有實例。

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

- TextFragmentAbsorber：此類負責從 PDF 中尋找和提取文字。
- 「圖」：將其替換為您要在 PDF 中搜尋的任何文字。

## 步驟 4：將文字吸收器應用到整個 PDF

設定文字吸收器後，您需要告訴程式搜尋 PDF 的所有頁面。

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

- Accept()：此方法將文字吸收器套用至 PDF，掃描每個頁面以尋找您指定的文字。

## 第 5 步：檢索並迭代提取的文本

現在我們已經掃描了 PDF，是時候檢索結果並顯示它們了。我們將循環遍歷提取的文字片段。

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- TextFragmentCollection：此集合保存文字吸收器找到的文字片段的所有實例。

## 第 6 步：循環每個片段並提取數據

我們現在將循環遍歷`textFragmentCollection`並提取每個文字段的各種屬性，例如其位置、字體細節和顏色。

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

- TextFragment：每個片段都包含找到的文字的一部分。
- TextSegment：每個片段可以有多個片段，代表文字的不同部分。
- TextState：提供有關文字字體、大小和顏色的詳細資訊。

在此循環中，我們列印出實際文字、其位置（X 和 Y 座標）、字體、字體是否嵌入在 PDF 中以及文字的前景色等詳細資訊。

## 結論

現在你就擁有了！您現在已經使用 Aspose.PDF for .NET 成功搜尋並提取了 PDF 文件中的文字。這個庫的靈活性令人難以置信。無論您需要在大型文件中搜尋特定文字、提取文字或分析其屬性，Aspose.PDF 都能讓您輕鬆完成。另外，透過我們介紹的程式碼，您可以根據自己的需求進行調整。 

## 常見問題解答

### 我可以一次搜尋多個短語嗎？  
是的，您可以修改程式碼以透過建立多個來搜尋多個短語`TextFragmentAbsorber`對象。

### 如何從特定頁面中提取文字？  
您可以透過應用程式來定位特定頁面`TextFragmentAbsorber`到單一頁面而不是整個文件。例如：`pdfDocument.Pages[1].Accept(textFragmentAbsorber);`.

### Aspose.PDF for .NET 是免費的嗎？  
 Aspose.PDF 是一個商業產品，但您可以將它與[免費試用](https://releases.aspose.com/).

### 我可以使用 Aspose.PDF 從 PDF 中提取圖像嗎？  
是的，Aspose.PDF 允許您提取文字以外的圖像。檢查[文件](https://reference.aspose.com/pdf/net/)了解更多詳情。

### 如果我需要更多幫助或支持怎麼辦？  
您隨時可以從以下方面獲得協助[Aspose 支援論壇](https://forum.aspose.com/c/pdf/10).