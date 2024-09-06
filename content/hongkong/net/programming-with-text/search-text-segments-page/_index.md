---
title: 在 PDF 檔案中搜尋文字段頁面
linktitle: 在 PDF 檔案中搜尋文字段頁面
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 檔案頁面上搜尋文字段並檢索其屬性。
type: docs
weight: 470
url: /zh-hant/net/programming-with-text/search-text-segments-page/
---
本教學課程介紹如何使用 Aspose.PDF for .NET 搜尋 PDF 文件頁面上的特定文字段並檢索其屬性。提供的 C# 原始程式碼逐步演示了該過程。

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

## 第三步：設定文檔目錄路徑

使用以下命令設定文檔目錄的路徑`dataDir`多變的：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

## 第 4 步：載入 PDF 文檔

使用載入 PDF 文檔`Document`班級：

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

代替`"SearchTextSegmentsPage.pdf"`與您的 PDF 檔案的實際名稱。

## 步驟5：建立一個TextFragmentAbsorber

創建一個`TextFragmentAbsorber`物件尋找輸入搜尋短語的所有實例：

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

代替`"text"`與您想要的搜尋字詞。

## 第 6 步：接受特定頁面的吸收器

接受文件所需頁面的吸收器：

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

代替`2`與所需的頁碼（從 1 開始的索引）。

## 步驟 7：檢索擷取的文字片段

使用以下命令獲取提取的文字片段`TextFragments`的財產`TextFragmentAbsorber`目的：

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## 第 8 步：循環文本段

循環檢索到的文字段並存取它們的屬性：

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

如果需要，修改循環內的程式碼以對每個文字段執行進一步的操作。

### 使用 Aspose.PDF for .NET 搜尋文字段頁面的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開啟文件
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
//建立 TextAbsorber 物件以尋找輸入搜尋短語的所有實例
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
//接受所有頁面的吸收器
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
//取得擷取的文字片段
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
//循環遍歷片段
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ",
		textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ",
		textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}",
		textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ",
		textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ",
		textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ",
		textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ",
		textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ",
		textSegment.TextState.ForegroundColor);
	}
}
```

## 結論

恭喜！您已成功學習如何使用 Aspose.PDF for .NET 在 PDF 文件頁面上搜尋特定文字區段。本教學課程提供了從載入文件到存取提取的文字段的逐步指南。現在您可以將此程式碼合併到您自己的 C# 專案中，以在 PDF 文件中執行高級文字段搜尋。

### 常見問題解答

#### Q：「在 PDF 檔案中搜尋文字段頁面」教學的目的為何？

答：「在 PDF 檔案中搜尋文字段頁面」教學提供瞭如何利用 .NET 的 Aspose.PDF 庫在 PDF 文件的特定頁面上搜尋特定文字段的全面指南。它涵蓋了設定項目、載入 PDF 文件、搜尋文字段以及使用 C# 程式碼檢索其屬性的過程。

#### Q：本教學如何幫助搜尋 PDF 文件中的特定文字段？

答：本教學示範了在 PDF 文件的特定頁面上定位和提取特定文字段的過程。透過遵循提供的步驟和程式碼範例，使用者可以有效地搜尋所需的文字段並檢索有關其屬性的資訊。

#### Q：學習本教程需要滿足哪些先決條件？

答：在開始本教學之前，您應該對 C# 程式語言有基本的了解。此外，您需要安裝 Aspose.PDF for .NET 程式庫。您可以從 Aspose 網站取得它或使用 NuGet 將其安裝到您的專案中。

#### Q：如何設定我的專案來遵循本教學？

答：首先，在您首選的整合開發環境 (IDE) 中建立一個新的 C# 項目，並新增對 Aspose.PDF for .NET 程式庫的參考。這將使您能夠利用庫的功能來搜尋和處理 PDF 文件。

#### Q：我可以使用本教學搜尋 PDF 任何頁面上的特定文字段嗎？

答：是的，本教學提供如何在 PDF 文件的選定頁面上搜尋特定文字段的說明。它指導使用者設定項目、載入 PDF 以及使用 Aspose.PDF 庫來尋找和檢索所需文字段的屬性。

#### Q：如何在本教程中指定要搜尋的文字？

答：要指定要搜尋的文本，請建立一個`TextFragmentAbsorber`對象並使用以下命令設定其搜尋參數`Text`財產。替換預設值`"text"`在教程的程式碼中加入您所需的搜尋短語。

#### 問：如何檢索擷取的文字段的屬性？

接受後`TextFragmentAbsorber`對於 PDF 的特定頁面，您可以使用以下命令檢索提取的文字片段`TextFragments`吸收體對象的屬性。這提供了對文本片段集合的訪問，每個文本片段包含多個文本片段。

#### Q：我可以自訂程式碼以對每個文字段執行其他操作嗎？

答：當然。本教程的範例程式碼提供了一個循環來迭代檢索到的文字段。您可以自訂此循環中的程式碼，以便根據您的專案要求對每個文字段執行其他操作。

#### Q：提取文字段後如何儲存修改後的PDF文件？

答：本教學主要著重在搜尋文字段並檢索其屬性。如果您打算對 PDF 進行修改，您可以參考其他 Aspose.PDF 文檔，以了解如何根據您的特定需求操作和儲存文檔。