---
title: 搜尋並獲取全部文本
linktitle: 搜尋並獲取全部文本
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 從 PDF 文件的所有頁面搜尋和取得文字。
type: docs
weight: 420
url: /zh-hant/net/programming-with-text/search-and-get-text-all/
---
## 介紹

您是否曾經需要從 PDF 中提取特定文本但發現它很棘手？ PDF 有時感覺像是上鎖的容器，導致您很難獲得所需的資訊。但好消息是：使用 Aspose.PDF for .NET，您可以輕鬆地從任何 PDF 中搜尋和檢索文字。這個功能強大的程式庫提供了您在 .NET 應用程式中處理 PDF 所需的一切，使文字擷取變得輕而易舉。在本教學中，我們將引導您完成使用 Aspose.PDF for .NET 從 PDF 檔案中搜尋和提取文字的過程。無論您是要建立文字分析工具還是只需要從 PDF 報告中自動提取數據，您都來對地方了！

## 先決條件

在我們進入程式碼之前，讓我們確保您已完成所有設定：

1. Aspose.PDF for .NET：您需要下載並安裝 Aspose.PDF for .NET。您可以從下載頁面取得它[這裡](https://releases.aspose.com/pdf/net/).
2. .NET 環境：確保您的開發電腦上設定了 .NET Framework 或 .NET Core。
3. 基本 C## 知識：建議熟悉 C# 並使用 .NET 專案。
4.  PDF 文件：我們將從中提取文本的範例 PDF 文件。在此範例中，我們將使用`SearchAndGetTextFromAll.pdf`.

## 導入包

在編寫任何程式碼之前，您需要將必要的命名空間匯入到專案中才能使用 Aspose.PDF。

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

這些命名空間提供對 PDF 文件物件模型的訪問，並允許我們操作文件中的文字。

讓我們將這個過程分解為簡單的步驟，以便您可以輕鬆遵循。

## 步驟1：設定文檔目錄

首先，您需要指定 PDF 所在目錄的路徑。這有助於應用程式找到您要從中提取文字的檔案。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

- 這`dataDir`變數應該指向你的目錄`SearchAndGetTextFromAll.pdf`文件已儲存。
- 代替`"YOUR DOCUMENT DIRECTORY"`與您機器上的實際路徑。

## 第 2 步：開啟 PDF 文檔

接下來，我們將使用 Aspose.PDF 開啟 PDF 文檔`Document`目的。

```csharp
//開啟文件
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

- 我們建立一個新的實例`Document`類別透過傳遞 PDF 的完整文件路徑。
- 這會將 PDF 載入到記憶體中，準備好進行處理。

## 第 3 步：建立文字吸收器

這`TextFragmentAbsorber`物件用於搜尋 PDF 中的特定文字。在本例中，我們將尋找單字「text」。

```csharp
//建立 TextAbsorber 物件以尋找輸入搜尋短語的所有實例
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

- 這`TextFragmentAbsorber`用字串初始化`"text"`。這意味著它將在 PDF 文件中查找任何出現的“文本”一詞。

## 第 4 步：接受所有頁面的吸收器

現在，我們將指示 PDF 文件接受吸收器並在其所有頁面上搜尋文字。

```csharp
//接受所有頁面的吸收器
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

- 這`Accept`方法應用於文檔的頁面。這將在所有頁面中搜尋指定文字。

## 步驟5：提取文字片段

一旦吸收器掃描了文檔，我們就可以檢索提取的文字片段。

```csharp
//取得擷取的文字片段
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- 這`TextFragments`的財產`TextFragmentAbsorber`傳回與搜尋字詞相符的所有文字片段的集合。

## 第 6 步：循環文字片段

現在我們已經收集了文字片段，我們將循環它們並提取詳細資訊。

```csharp
//循環遍歷片段
foreach (TextFragment textFragment in textFragmentCollection)
{
    Console.WriteLine("Text : {0} ", textFragment.Text);
    Console.WriteLine("Position : {0} ", textFragment.Position);
    Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
    Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
    Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
    Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
    Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
    Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
    Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
    Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

- 這`foreach`循環遍歷每個`TextFragment`在集合中。
- 我們列印每個片段的各種屬性，例如實際文字、其在頁面上的位置、字體詳細資訊和字體大小。
- 這`XIndent`和`YIndent`屬性給出了 PDF 中文本片段的精確座標。

## 結論

現在你就擁有了！只需幾行程式碼，我們就可以使用 Aspose.PDF for .NET 成功地從 PDF 中搜尋並提取文字。 Aspose.PDF 的靈活性可讓您以多種方式操作 PDF，這使其成為在 .NET 環境中需要強大 PDF 解決方案的開發人員的絕佳選擇。您可以輕鬆擴展此範例以搜尋其他單字、提取更多詳細信息，甚至根據您的需求操作 PDF 內容。希望本指南為您提供了一種清晰、直接的 PDF 處理方法。繼續嘗試使用您自己的 PDF！

## 常見問題解答

### 我可以一次搜尋多個單字嗎？  
是的，您可以修改`TextFragmentAbsorber`透過相應調整搜尋字串來搜尋多個短語。

### 如果文字跨越多行怎麼辦？  
即使文字跨越多行，Aspose.PDF 仍將識別並擷取文字。您可以單獨處理這些片段。

### 如何將提取的文字儲存到文件中？  
您可以使用標準 C# 文件 I/O 操作將提取的文字寫入文件，例如`StreamWriter`.

### Aspose.PDF是否支援從掃描的PDF中提取文字？  
Aspose.PDF 不支援 OCR。對於掃描的 PDF，您需要 OCR 工具來識別文字。

### 如何處理加密的 PDF？  
如果您的 PDF 受密碼保護，您可以透過在載入文件時提供密碼來使用 Aspose.PDF 將其解鎖。