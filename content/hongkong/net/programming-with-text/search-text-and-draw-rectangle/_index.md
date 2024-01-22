---
title: 搜尋文字並繪製一個矩形
linktitle: 搜尋文字並繪製一個矩形
second_title: Aspose.PDF for .NET API 參考
description: 了解如何在 PDF 中搜尋文字、在找到的文字周圍繪製矩形以及使用 Aspose.PDF for .NET 儲存修改後的文件。
type: docs
weight: 460
url: /zh-hant/net/programming-with-text/search-text-and-draw-rectangle/
---
本教學課程介紹如何使用 Aspose.PDF for .NET 搜尋 PDF 文件中的特定文本，在找到的文本周圍繪製矩形，然後儲存修改後的文件。提供的 C# 原始程式碼逐步演示了該過程。

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
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
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

代替`"SearchAndGetTextFromAll.pdf"`與您的 PDF 檔案的實際名稱。

## 步驟5：建立一個TextFragmentAbsorber

創建一個`TextFragmentAbsorber`物件尋找輸入搜尋短語的所有實例：

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

代替`@"[\S]+"`與您想要的正規表示式模式。

## 第 6 步：啟用正規表示式搜尋

透過設定啟用正規表示式搜尋`TextSearchOptions`吸收體的特性：

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## 步驟7：在所有頁面上搜尋

接受文件所有頁面的吸收器：

```csharp
document.Pages.Accept(textAbsorber);
```

## 第 8 步：在找到的文字周圍畫一個矩形

創建一個`PdfContentEditor`物件並循環檢索到的文字片段，在每個文字片段周圍繪製一個矩形：

```csharp
var editor = new PdfContentEditor(document);
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

## 步驟9：儲存修改後的文檔

儲存修改後的文件：

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

確保更換`"SearchTextAndDrawRectangle_out.pdf"`與所需的輸出檔名。

### 使用 Aspose.PDF for .NET 搜尋文字和繪製矩形的範例原始程式碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開啟文件
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
//建立 TextAbsorber 物件以尋找與正規表示式相符的所有短語
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
document.Pages.Accept(textAbsorber); 
var editor = new PdfContentEditor(document); 
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
			DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
	}
}
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

## 結論

恭喜！您已經成功學習如何在 PDF 文件中搜尋特定文字、在找到的文字周圍繪製矩形以及使用 Aspose.PDF for .NET 儲存修改後的文件。本教程提供了從設定項目到執行所需操作的逐步指南。現在，您可以將此程式碼合併到您自己的 C# 專案中，以操作 PDF 文件中的文字和繪製矩形。

### 常見問題解答

#### Q：「搜尋文字並繪製矩形」教學的目的是什麼？

A: The "Search Text And Draw Rectangle" tutorial aims to guide users through the process of using the Aspose.PDF library for .NET to search for specific text within a PDF document, draw rectangles around the found text segments, and save the modified文件.本教程提供了詳細的說明和 C# 程式碼範例來說明該過程的每個步驟。

#### Q：本教學如何幫助您在 PDF 文件中的特定文字周圍繪製矩形？

答：本教學提供了有關如何在 PDF 文件中的特定文字段周圍定位和繪製矩形的全面指南。它演示了設定項目、載入 PDF 文件、啟用正規表示式搜尋、在找到的文本段周圍繪製矩形以及保存修改後的 PDF 的過程。

#### Q：學習本教程需要滿足哪些先決條件？

答：在開始本教學之前，您應該對 C# 程式語言有基本的了解。此外，您需要安裝 Aspose.PDF for .NET 程式庫。您可以從 Aspose 網站取得它或使用 NuGet 將其安裝到您的專案中。

#### Q：如何設定我的專案來遵循本教學？

答：首先在您首選的整合開發環境 (IDE) 中建立一個新的 C# 專案。然後，將對 Aspose.PDF for .NET 程式庫的參考新增到您的專案中。這將使您能夠使用庫的功能來操作 PDF 文件。

#### Q：我可以使用本教學在特定文字周圍繪製矩形嗎？

答：是的，本教學的重點是在 PDF 文件中的特定文字段周圍繪製矩形。它示範如何使用正規表示式找到所需的文本，在識別的文本段周圍建立矩形，以及保存修改後的 PDF。

#### Q：如何指定要搜尋的文字並在其周圍繪製矩形？

答：若要指定要搜尋的文字並在其周圍繪製矩形，請建立一個`TextFragmentAbsorber`對象並使用設定其模式`Text`範圍。替換預設模式`@"[\S]+"`在教學課程的程式碼中加入您所需的正規表示式模式。

#### Q：如何啟用文字的正規表示式搜尋？

 A：透過建立一個來啟用正規表示式搜尋`TextSearchOptions`對象並將其值設為`true`。將此物件分配給`TextSearchOptions`的財產`TextFragmentAbsorber`實例。這可確保在文字搜尋期間使用正規表示式模式。

#### 問：如何在找到的文字周圍繪製矩形？

 A：使用辨識文本段後`TextFragmentAbsorber`，本教程提供了一個循環來迭代這些段落。對於每個文字段，本教學示範如何使用以下命令在其周圍建立一個矩形：`DrawBox`方法並指定矩形的外觀。

#### Q：保存修改後的繪製矩形的PDF的步驟是什麼？

答：在所需的文字段周圍繪製矩形後，使用`Document`班級的`Save`方法保存修改後的文件。本教學的範例程式碼展示如何儲存編輯後的 PDF 並顯示成功訊息。

#### Q：我可以自訂繪製矩形的外觀嗎？

答：是的，您可以自訂繪製矩形的外觀。在本教程的範例程式碼中，`DrawBox`方法用於建立矩形。您可以修改顏色、樣式和厚度等屬性來自訂繪製矩形的外觀。