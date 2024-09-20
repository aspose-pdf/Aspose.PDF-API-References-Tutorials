---
title: 在 PDF 檔案中搜尋正規表示式
linktitle: 在 PDF 檔案中搜尋正規表示式
second_title: Aspose.PDF for .NET API 參考
description: 在此逐步教學中，了解如何使用 Aspose.PDF for .NET 在 PDF 檔案中搜尋正規表示式。使用正規表示式提高您的工作效率。
type: docs
weight: 440
url: /zh-hant/net/programming-with-text/search-regular-expression/
---
## 介紹

在處理大型 PDF 文件時，您可能會發現自己正在搜尋特定的模式或格式，例如日期、電話號碼或其他結構化資料。手動瀏覽 PDF 可能很乏味，對嗎？這就是使用正規表示式 (regex) 派上用場的地方。在本教學中，我們將探討如何使用 Aspose.PDF for .NET 在 PDF 檔案中搜尋正規表示式模式。本指南將引導您完成每個步驟，以便您可以在 .NET 應用程式中輕鬆實現它。

## 先決條件

在我們深入了解逐步教學之前，讓我們先回顧一下您需要具備的條件：

-  Aspose.PDF for .NET：您需要安裝此程式庫。如果您還沒有安裝，您可以[在這裡下載](https://releases.aspose.com/pdf/net/).
- IDE：Visual Studio 或任何其他 C# 相容 IDE。
- .NET Framework：確保您的專案設定了適當版本的 .NET Framework。
- C# 的基本知識：雖然本指南很詳細，但對 C# 的基本了解將會有所幫助。

### 導入包

首先，您需要將必要的命名空間從 Aspose.PDF for .NET 匯入到您的專案中。這些套件對於處理 PDF 和使用正規表示式執行搜尋操作至關重要。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

讓我們將使用 Aspose.PDF 在 PDF 檔案中搜尋正規表示式的過程分解為多個步驟。

## 第 1 步：設定文檔目錄

每個 PDF 操作都從指定文件所在的位置開始。您需要定義 PDF 文件的路徑，該文件儲存在`dataDir`多變的。

### 步驟 1.1：定義文檔路徑

```csharp
//定義 PDF 文件的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`與 PDF 檔案的實際路徑。此步驟至關重要，因為它將您的程式碼指向您要使用的檔案。

### 步驟1.2：開啟PDF文檔

接下來，您需要使用以下命令開啟 PDF 文檔`Document`來自 Aspose.PDF 的類別。

```csharp
//開啟文件
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

這裡，`"SearchRegularExpressionAll.pdf"`是我們將在其中執行正規表示式搜尋的範例 PDF 檔案。

## 步驟2：設定TextFragmentAbsorber

這就是魔法發生的地方！這`TextFragmentAbsorber`類別有助於捕獲與特定模式或正規表示式相符的文字片段。

讓我們設定吸收器以使用正規表示式查找模式。在本例中，我們正在搜尋諸如「1999-2000」之類的年份模式。

```csharp
//建立 TextAbsorber 物件以尋找與正規表示式相符的所有短語
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); //如1999-2000年
```

正規表示式`\\d{4}-\\d{4}`找出四位數字後面跟著連字符和另外四位數字的模式，這是年份範圍的典型模式。

## 第 3 步：啟用正規表示式搜尋

為了確保搜尋操作將模式解釋為正規表示式，您需要使用以下命令配置搜尋選項`TextSearchOptions`班級。

```csharp
//設定文字搜尋選項以指定正規表示式的用法
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

設定`TextSearchOptions`到`true`確保吸收器使用基於正規表示式的搜尋而不是純文字。

## 第 4 步：接受文字吸收器

在此階段，您將文字吸收器套用到 PDF 文檔，以便它可以執行搜尋操作。這是透過呼叫來完成的`Accept`方法上的`Pages`PDF 文件的對象。

```csharp
//接受所有頁面的吸收器
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

此命令處理 PDF 的所有頁面，尋找與正規表示式相符的任何文字。

## 第 5 步：提取並顯示結果

搜尋完成後，您需要提取結果。這`TextFragmentAbsorber`將這些結果儲存在`TextFragmentCollection`。您可以循環訪問此集合以存取和顯示每個匹配的文字片段。

### 步驟5.1：檢索擷取的文字片段

```csharp
//取得擷取的文字片段
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

現在您已經收集了片段，是時候循環遍歷它們並顯示相關詳細信息，例如文字、位置、字體詳細資訊等。

### 步驟 5.2：循環片段

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

對於每個`TextFragment`，列印出字體大小、字體名稱和位置等詳細資訊。這不僅有助於查找文本，還可以為您提供準確的格式和位置。

## 結論

給你了！使用正規表示式在 PDF 檔案中搜尋模式非常強大，尤其是對於日期、電話號碼和類似模式等結構化文字。 Aspose.PDF for .NET 提供了一種無縫的方式來輕鬆執行此類操作。現在，您可以利用正規表示式的強大功能來自動執行 PDF 文字搜索，從而使您的工作流程更有效率。

## 常見問題解答

### 我可以在一份 PDF 中搜尋多個圖案嗎？
是的，您可以運行多個`TextFragmentAbsorber`同一 PDF 中的對象，每個對像都有不同的正規表示式模式。

### Aspose.PDF是否支援搜尋不區分大小寫的模式？
絕對地！您可以配置`TextSearchOptions`使搜尋不區分大小寫。

### 我可以搜尋的 PDF 大小有限制嗎？
沒有嚴格的限制，但效能可能會有所不同，具體取決於 PDF 的大小和正規表示式模式的複雜性。

### 我可以在 PDF 中突出顯示找到的文字嗎？
是的，Aspose.PDF 允許您在使用吸收器找到文字後突出顯示甚至替換文字。

### 如果未找到模式，如何處理錯誤？
如果沒有找到匹配項，則`TextFragmentCollection`將是空的。您可以在循環結果之前透過簡單的檢查來處理這種情況。