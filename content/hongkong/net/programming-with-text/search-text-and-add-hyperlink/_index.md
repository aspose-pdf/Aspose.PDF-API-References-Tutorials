---
title: 搜尋文字並添加超鏈接
linktitle: 搜尋文字並添加超鏈接
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 中搜尋文字、新增超連結到找到的文字以及儲存修改後的文件。
type: docs
weight: 450
url: /zh-hant/net/programming-with-text/search-text-and-add-hyperlink/
---
本教學課程介紹如何使用 Aspose.PDF for .NET 搜尋 PDF 文件中的特定文字、新增找到的文字的超連結以及儲存修改後的文件。提供的 C# 原始程式碼逐步演示了該過程。

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## 第三步：設定文檔目錄路徑

使用以下命令設定文檔目錄的路徑`dataDir`多變的：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

## 第四步：建立一個TextFragmentAbsorber

創建一個`TextFragmentAbsorber`物件尋找輸入搜尋短語的所有實例：

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

代替`"\\d{4}-\\d{4}"`與您想要的正規表示式模式。

## 第 5 步：啟用正規表示式搜尋

透過設定啟用正規表示式搜尋`TextSearchOptions`吸收體的特性：

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## 步驟6：開啟並綁定PDF文檔

創建一個`PdfContentEditor`物件並將其綁定到來源 PDF 檔案：

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

代替`"SearchRegularExpressionPage.pdf"`與您的 PDF 檔案的實際名稱。

## 第 7 步：接受頁面的吸收器

接受文件所需頁面的吸收器：

```csharp
editor.Document.Pages[1].Accept(absorber);
```

代替`1`與所需的頁碼。

## 步驟 8：將超連結加入找到的文本

循環檢索到的文字片段並向其添加超連結：

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    //根據文字片段的位置建立一個矩形
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    //將網頁連結新增至矩形
    editor.CreateWebLink(rect, "http://www.aspose.com", 1, System.Drawing.Color.Blue);
}
```

代替`"http://www.aspose.com"`與所需的超連結 URL。

## 步驟9：儲存並關閉修改後的文檔

儲存修改後的文件並關閉編輯器：

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

確保更換`"SearchTextAndAddHyperlink_out.pdf"`與所需的輸出檔名。

### 使用 Aspose.PDF for .NET 搜尋文字和新增超連結的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//建立吸收器物件以尋找輸入搜尋短語的所有實例
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
//啟用正規表示式搜尋
absorber.TextSearchOptions = new TextSearchOptions(true);
//開啟文件
PdfContentEditor editor = new PdfContentEditor();
//綁定來源PDF文件
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
//接受頁面的吸收器
editor.Document.Pages[1].Accept(absorber);
int[] dashArray = { };
String[] LEArray = { };
System.Drawing.Color blue = System.Drawing.Color.Blue;
//循環遍歷片段
foreach (TextFragment textFragment in absorber.TextFragments)
{
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
		(int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
		(int)Math.Round(textFragment.Rectangle.Height + 1));
	Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
	editor.CreateWebLink(rect, "http://www.aspose.com", 1, 藍色, actionName);
	editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
		(float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

## 結論

恭喜！您已經成功學習如何在 PDF 文件中搜尋特定文字、在找到的文字中新增超連結以及使用 Aspose.PDF for .NET 儲存修改後的文件。本教程提供了從設定項目到執行所需操作的逐步指南。現在，您可以將此程式碼合併到您自己的 C# 專案中，以操作文字並在 PDF 文件中新增超連結。

### 常見問題解答

#### Q：「搜尋文字並加入超連結」教學的目的是什麼？

答：「搜尋文字並新增超連結」教學課程旨在示範如何使用 Aspose.PDF .NET 程式庫在 PDF 文件中搜尋特定文本，為找到的文字新增超鏈接，然後儲存修改後的文件。本教程提供了全面的指南和 C# 程式碼範例來說明逐步過程。

#### Q：本教學如何幫助您在 PDF 文件中新增指向特定文字的超連結？

答：本教學將引導您完成使用 Aspose.PDF 庫來尋找 PDF 文件中的特定文字、將超連結套用到所識別的文字以及儲存修改後的 PDF 的過程。它涵蓋了一些基本步驟，例如設定項目、載入文件、啟用正規表示式搜尋以及在找到的文字中新增超連結。

#### Q：學習本教程需要什麼先決條件？

答：開始之前，您應該對 C# 程式語言有基本的了解。此外，您還需要安裝 Aspose.PDF for .NET 程式庫，該程式庫可以從 Aspose 網站取得或在專案中使用 NuGet 安裝。

#### Q：如何設定我的專案來遵循本教學？

答：首先在您首選的整合開發環境 (IDE) 中建立一個新的 C# 專案。然後，新增對 Aspose.PDF for .NET 程式庫的引用，這將使您能夠在專案中利用該程式庫的功能。

#### Q：我可以使用本教學添加指向特定文字的超連結嗎？

答：是的，本教學特別關注在 PDF 文件中添加指向特定文字的超連結。它示範如何使用正規表示式來尋找和提取所需的文字、建立與文字片段關聯的超連結以及儲存修改後的 PDF。

#### Q：如何定義要搜尋的文字並新增超連結？

答：若要指定要搜尋的文字並新增超鏈接，請建立一個`TextFragmentAbsorber`對象並使用設定其模式`Text`範圍。替換預設模式`"\\d{4}-\\d{4}"`在教學課程的程式碼中加入您所需的正規表示式模式。

#### Q：如何啟用文字的正規表示式搜尋？

 A：透過建立一個來啟用正規表示式搜尋`TextSearchOptions`對象並將其值設為`true`。將此物件分配給`TextSearchOptions`的財產`TextFragmentAbsorber`實例。這可確保在文字搜尋期間套用正規表示式模式。

#### Q：如何為找到的文字添加超連結？

 A：使用辨識文字片段後`TextFragmentAbsorber`，本教程提供了一個循環來迭代這些片段。對於每個文字片段，本教學示範如何將文字顏色設為藍色並使用`CreateWebLink`方法。

#### Q：保存修改後的帶有超連結的PDF的步驟是什麼？

 A：將超連結加入所需的文字片段後，使用`PdfContentEditor`類別來保存修改後的文件。本教學的範例程式碼展示如何儲存編輯後的 PDF、關閉編輯器以及顯示成功訊息。