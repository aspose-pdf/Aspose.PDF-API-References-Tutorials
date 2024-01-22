---
title: 在 PDF 檔案中搜尋正規表示式
linktitle: 在 PDF 檔案中搜尋正規表示式
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 檔案中使用正規表示式搜尋和檢索文字。
type: docs
weight: 440
url: /zh-hant/net/programming-with-text/search-regular-expression/
---
本教學課程介紹如何使用 Aspose.PDF for .NET 搜尋和檢索與 PDF 檔案中的正規表示式相符的文字。提供的 C# 原始程式碼逐步演示了該過程。

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
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

確保更換`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

## 第四步：使用正規表示式搜尋

創建一個`TextFragmentAbsorber`物件並設定正規表示式模式以查找與該模式相符的所有短語：

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); //如1999-2000年
```

代替`"\\d{4}-\\d{4}"`與您想要的正規表示式模式。

## 第 5 步：設定文字搜尋選項

創建一個`TextSearchOptions`對象並將其設定為`TextSearchOptions`的財產`TextFragmentAbsorber`啟用正規表示式使用的物件：

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

## 步驟6：在所有頁面上搜尋

接受文件所有頁面的吸收器：

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## 步驟 7：檢索擷取的文字片段

使用以下命令獲取提取的文字片段`TextFragments`的財產`TextFragmentAbsorber`目的：

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## 第 8 步：循環文字片段

循環檢索到的文字片段並存取它們的屬性：

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

### 使用 Aspose.PDF for .NET 搜尋正規表示式的範例原始程式碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開啟文件
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
//建立 TextAbsorber 物件以尋找與正規表示式相符的所有短語
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); //如1999-2000年
//設定文字搜尋選項以指定正規表示式的用法
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
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

恭喜！您已成功學習如何使用 Aspose.PDF for .NET 搜尋和擷取與 PDF 文件中的正規表示式相符的文字。本教學課程提供了從載入文件到存取提取的文字片段的逐步指南。現在，您可以將此程式碼合併到您自己的 C# 專案中，以在 PDF 文件中執行高級文字搜尋。

### 常見問題解答

#### Q：「在 PDF 檔案中搜尋正規表示式」教學的目的為何？

答：「在 PDF 檔案中搜尋正規表示式」教學課程旨在展示如何使用 .NET 的 Aspose.PDF 程式庫來搜尋並擷取與 PDF 檔案中指定正規表示式模式相符的文字。本教程提供了全面的指導和範例 C# 程式碼來演示該過程。

#### Q：本教學如何幫助您在 PDF 文件中使用正規表示式搜尋文字？

答：本教學提供了使用 Aspose.PDF 庫基於正規表示式模式在 PDF 文件中進行文字搜尋的逐步方法。它詳細介紹如何設定項目、載入 PDF 文件、定義正規表示式模式以及檢索符合的文字片段。

#### Q：學習本教程的先決條件是什麼？

答：在開始本教學之前，您應該對 C# 程式語言有基本的了解。此外，您需要安裝 Aspose.PDF for .NET 程式庫。您可以從 Aspose 網站取得它或使用 NuGet 將其整合到您的專案中。

#### Q：如何設定我的專案來遵循本教學？

答：首先，在您首選的整合開發環境 (IDE) 中建立一個新的 C# 項目，並新增對 Aspose.PDF for .NET 程式庫的參考。這將使您能夠在專案中利用該庫的功能。

#### Q：我可以使用正規表示式搜尋 PDF 文件中的文字嗎？

答：是的，本教學課程示範如何使用正規表示式從 PDF 文件中搜尋和擷取文字。它涉及利用`TextFragmentAbsorber`類別並指定正規表示式模式以尋找與提供的模式相符的短語。

#### Q：如何定義文字搜尋的正規表示式模式？

答：要定義文字搜尋的正規表示式模式，請建立一個`TextFragmentAbsorber`對象並使用設定其模式`Text`範圍。替換預設模式`"\\d{4}-\\d{4}"`在教學課程的程式碼中加入您所需的正規表示式模式。

#### Q：如何啟用正規表示式用於文字搜尋？

答：透過建立一個來啟用正規表示式的使用`TextSearchOptions`對象並將其值設為`true`。將此物件分配給`TextSearchOptions`的財產`TextFragmentAbsorber`實例。這可確保在文字搜尋期間套用正規表示式模式。

#### Q：我可以檢索與正規表示式模式相符的文字片段嗎？

答：當然。對 PDF 文件套用正規表示式搜尋後，您可以使用以下命令檢索擷取的文字片段：`TextFragments`的財產`TextFragmentAbsorber`目的。這些文字片段包含與指定正規表示式模式相符的文字段。

#### Q：我可以從檢索到的文字片段中存取什麼？

答：從檢索到的文字片段中，您可以存取各種屬性，例如相符的文字內容、位置（X 和 Y 座標）、字體資訊（名稱、大小、顏色）等。本教學循環中的範例程式碼示範如何存取和顯示這些屬性。

#### Q：如何對擷取的文字片段自訂操作？

答：提取文字片段後，您可以在循環中自訂程式碼以對每個文字片段執行其他操作。這可以包括保存提取的文字、分析模式或根據您的要求實施格式變更。