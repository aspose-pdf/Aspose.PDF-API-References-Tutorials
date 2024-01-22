---
title: 搜尋並獲取全部文本
linktitle: 搜尋並獲取全部文本
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 從 PDF 文件的所有頁面搜尋和取得文字。
type: docs
weight: 420
url: /zh-hant/net/programming-with-text/search-and-get-text-all/
---
本教學課程介紹如何使用 Aspose.PDF for .NET 從 PDF 文件的所有頁面搜尋和取得文字。提供的 C# 原始程式碼逐步演示了該過程。

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

確保更換`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

## 第 4 步：搜尋並提取文本

創建一個`TextFragmentAbsorber`物件尋找輸入搜尋短語的所有實例：

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

代替`"text"`與您要搜尋的實際文字。

## 步驟5：在所有頁面上搜尋

接受文件所有頁面的吸收器：

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## 步驟6：取得擷取的文字片段

使用以下命令獲取提取的文字片段`TextFragments`的財產`TextFragmentAbsorber`目的：

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## 第 7 步：循環文字片段

循環遍歷 getd 文字片段並存取它們的屬性：

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
    Console.WriteLine("Text: {0} ", textFragment.Text);
    Console.WriteLine("Position: {0} ", textFragment.Position);
    Console.WriteLine("XIndent: {0} ", textFragment.Position.XIndent);
    Console.WriteLine("YIndent: {0} ", textFragment.Position.YIndent);
    Console.WriteLine("Font - Name: {0}", textFragment.TextState.Font.FontName);
    Console.WriteLine("Font - IsAccessible: {0} ", textFragment.TextState.Font.IsAccessible);
    Console.WriteLine("Font - IsEmbedded: {0} ", textFragment.TextState.Font.IsEmbedded);
    Console.WriteLine("Font - IsSubset: {0} ", textFragment.TextState.Font.IsSubset);
    Console.WriteLine("Font Size: {0} ", textFragment.TextState.FontSize);
    Console.WriteLine("Foreground Color: {0} ", textFragment.TextState.ForegroundColor);
}
```

您可以修改循環內的程式碼以對每個文字片段執行進一步的操作。

### 使用 Aspose.PDF for .NET 搜尋並取得全部文字的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開啟文件
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
//建立 TextAbsorber 物件以尋找輸入搜尋短語的所有實例
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
//接受所有頁面的吸收器
pdfDocument.Pages.Accept(textFragmentAbsorber);
//取得擷取的文字片段
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
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

## 結論

恭喜！您已成功學習如何使用 Aspose.PDF for .NET 從 PDF 文件的所有頁面搜尋和取得文字。本教學課程提供了從載入文件到存取提取的文字片段的逐步指南。現在，您可以將此程式碼合併到您自己的 C# 專案中，以分析和處理 PDF 文件中的文字內容。

### 常見問題解答

#### Q：「搜尋並取得全部文字」教學的目的為何？

答：「搜尋並取得全部文字」教學課程示範如何利用 .NET 的 Aspose.PDF 庫從 PDF 文件的所有頁面中搜尋和擷取文字。本教程提供了用於執行文字搜尋和檢索的逐步說明以及範例 C# 程式碼。

#### Q：本教學如何幫助從 PDF 文件中提取文字？

答：本教學將引導您完成從 PDF 文件的所有頁面中提取文字的過程。它使用 Aspose.PDF 庫來定位特定文字短語並檢索相關信息，例如位置、字體屬性和顏色。

#### Q：學習本教程的先決條件是什麼？

答：在開始本教學之前，您應該對 C# 程式語言有基本的了解。此外，您需要安裝 Aspose.PDF for .NET 程式庫。您可以從 Aspose 網站取得它或使用 NuGet 將其整合到您的專案中。

#### Q：如何設定我的專案來遵循本教學？

答：首先，在您首選的整合開發環境 (IDE) 中建立一個新的 C# 項目，並新增對 Aspose.PDF for .NET 程式庫的參考。這將允許您在專案中存取該庫的功能。

#### Q：如何搜尋 PDF 文件中的特定文字？

答：您可以使用`TextFragmentAbsorber`類別來尋找 PDF 文件中特定搜尋短語的實例。透過建立此類別的實例並指定目標文本，您可以捕獲該文本的所有出現位置。

#### Q：我可以搜尋 PDF 文件所有頁面的文字嗎？

答：是的，本教學示範如何在 PDF 文件的所有頁面中搜尋文字。這`pdfDocument.Pages.Accept(textFragmentAbsorber)`方法用於接受所有頁面的吸收器，允許您在每個頁面上搜尋所需的文字。

#### Q：如何存取提取的文字片段？

答：搜尋文字後，您可以使用以下命令存取提取的文字片段：`TextFragments`的財產`TextFragmentAbsorber`目的。此屬性提供對集合的訪問`TextFragment`包含提取的文字和相關資訊的物件。

#### Q：我可以從擷取的文字片段中檢索哪些資訊？

答：您可以從提取的文字片段中檢索各種詳細信息，例如實際文字內容、位置（X 和 Y 座標）、字體資訊（名稱、大小、顏色等）等。本教學的範例程式碼示範如何存取和列印這些詳細資訊。

#### Q：我可以對提取的文字片段執行進一步的操作嗎？

答：當然。提取文字片段後，您可以修改循環中的程式碼以對每個片段執行自訂操作。這可能包括保存提取的文字、分析文字模式或應用格式變更。