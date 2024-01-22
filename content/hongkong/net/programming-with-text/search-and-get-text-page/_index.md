---
title: 搜尋並取得 PDF 文件中的文字頁面
linktitle: 搜尋並取得 PDF 文件中的文字頁面
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 從 PDF 檔案中的特定頁面搜尋和取得文字。
type: docs
weight: 430
url: /zh-hant/net/programming-with-text/search-and-get-text-page/
---
本教學課程介紹如何使用 Aspose.PDF for .NET 從 PDF 檔案中的特定頁面搜尋和取得文字。提供的 C# 原始程式碼逐步演示了該過程。

## 先決條件

在繼續學習本教學之前，請確保您具備以下條件：

- C# 程式語言的基礎知識。
- 安裝了 Aspose.PDF for .NET 函式庫。您可以從 Aspose 網站取得它或使用 NuGet 將其安裝到您的專案中。

## 第 1 步：設定項目

首先在您首選的整合開發環境 (IDE) 中建立一個新的 C# 項目，並新增對 Aspose.PDF for .NET 程式庫的參考。

## 步驟2：導入必要的命名空間

在 C# 檔案的開頭新增以下 using 指令以匯入所需的命名空間：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 第 3 步：載入 PDF 文檔

設定 PDF 文檔目錄的路徑並使用以下命令載入文檔`Document`班級：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

確保更換`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

## 步驟 4：從頁面中搜尋並提取文本

創建一個`TextFragmentAbsorber`物件尋找特定頁面上輸入搜尋短語的所有實例：

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

代替`"Figure"`與您要搜尋的實際文字。

## 步驟5：在特定頁面上搜尋

接受文件特定頁面的吸收器：

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## 步驟6：取得擷取的文字片段

使用以下命令獲取提取的文字片段`TextFragments`的財產`TextFragmentAbsorber`目的：

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## 第 7 步：循環遍歷文字片段和片段

循環遍歷 getd 文字片段及其段，並存取它們的屬性：

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text: {0} ", textSegment.Text);
		Console.WriteLine("Position: {0} ", textSegment.Position);
		Console.WriteLine("XIndent: {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent: {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name: {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible: {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded: {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset: {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size: {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color: {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

您可以修改循環內的程式碼以對每個文字段執行進一步的操作。

### 使用 Aspose.PDF for .NET 搜尋並取得文字頁面的範例原始程式碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開啟文件
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
//建立 TextAbsorber 物件以尋找輸入搜尋短語的所有實例
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
//接受所有頁面的吸收器
pdfDocument.Pages.Accept(textFragmentAbsorber);
//取得擷取的文字片段
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
//循環遍歷片段
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

## 結論

恭喜！您已成功學習如何使用 Aspose.PDF for .NET 從 PDF 文件的特定頁面搜尋和取得文字。本教學課程提供了從載入文件到存取提取的文字段的逐步指南。您現在可以合併

### 常見問題解答

#### Q：「搜尋並取得文字頁面」教學的目的為何？

答：「搜尋並取得文字頁面」教學課程旨在說明如何使用 .NET 的 Aspose.PDF 庫從 PDF 檔案中的特定頁面搜尋和檢索文字。本教程提供了詳細說明和範例 C# 程式碼來演示該過程。

#### Q：本教學如何幫助從 PDF 文件的特定頁面中提取文字？

答：本教學將引導您完成使用 Aspose.PDF 庫從 PDF 文件的特定頁面提取文字的過程。它概述了必要的步驟並提供 C# 程式碼來搜尋所選頁面上的指定文字短語並檢索關聯的文字片段。

#### Q：學習本教程的先決條件是什麼？

答：在開始本教學之前，您應該對 C# 程式語言有基本的了解。此外，您需要安裝 Aspose.PDF for .NET 程式庫。您可以從 Aspose 網站取得它或使用 NuGet 將其整合到您的專案中。

#### Q：如何設定我的專案來遵循本教學？

答：首先，在您首選的整合開發環境 (IDE) 中建立一個新的 C# 項目，並新增對 Aspose.PDF for .NET 程式庫的參考。這將使您能夠在專案中利用該庫的功能。

#### Q：我可以搜尋 PDF 文件特定頁面上的文字嗎？

答：是的，本教學示範如何在 PDF 文件的特定頁面上搜尋文字。它涉及使用`TextFragmentAbsorber`類別來尋找所選頁面上特定文字短語的實例。

#### Q：如何存取從特定頁面提取的文字片段？

 A：在指定頁面搜尋到文字後，您可以透過以下方式存取擷取的文字片段：`TextSegments`的財產`TextFragment`目的。此屬性提供對集合的訪問`TextSegment`包含提取的文字和相關資訊的物件。

#### Q：我可以從擷取的文字片段中檢索哪些資訊？

答：您可以從提取的文字片段中檢索各種詳細信息，包括文字內容、位置（X 和 Y 座標）、字體資訊（名稱、大小、顏色等）等。本教學的範例程式碼示範如何存取和列印每個文字段的這些詳細資訊。

#### Q：我可以對提取的文字段執行自訂操作嗎？

答：當然可以。提取文字段後，您可以自訂循環中的程式碼以對每個段執行其他操作。這可能包括保存提取的文字、分析文字模式或應用格式變更。