---
title: PDF 檔案中的文字和圖像作為段落
linktitle: PDF 檔案中的文字和圖像作為段落
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 檔案中新增文字和影像作為內聯段落。
type: docs
weight: 530
url: /zh-hant/net/programming-with-text/text-and-image-as-paragraph/
---
本教學課程說明如何使用 Aspose.PDF for .NET 在 PDF 檔案中新增文字和影像作為內嵌段落。提供的 C# 原始程式碼逐步演示了該過程。

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
using Aspose.Pdf.Drawing;
```

## 第三步：設定文檔目錄路徑

使用以下命令設定文檔目錄的路徑`dataDir`多變的：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

## 第 4 步：建立新文件和頁面

創建一個新的`Document`物件並將頁面新增至其頁面集合中：

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## 第 5 步：建立 TextFragment 並將其新增為段落

創建一個`TextFragment`物件並將其新增至頁面的段落集合中：

```csharp
TextFragment text = new TextFragment("Hello World.. ");
page.Paragraphs.Add(text);
```

## 步驟 6：新增影像作為內嵌段落

創建一個`Aspose.Pdf.Image`物件並將其設定為內聯段落，以便它出現在上一個段落之後：

```csharp
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
image.IsInLineParagraph = true;
image.File = dataDir + "aspose-logo.jpg";
image.FixHeight = 30; //可選：設定影像高度
image.FixWidth = 100; //可選：設定圖像寬度
page.Paragraphs.Add(image);
```

代替`"aspose-logo.jpg"`與實際的影像檔案名，並根據需要調整可選的影像高度和寬度。

## 第 7 步：新增另一個 TextFragment 作為內嵌段落

重新初始化`TextFragment`具有不同內容的物件並將其新增為內嵌段落：

```csharp
text = new TextFragment(" Hello Again..");
text.IsInLineParagraph = true;
page.Paragraphs.Add(text);
```

## 步驟8：儲存PDF文檔

儲存修改後的PDF文件：

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
```

確保更換`"TextAndImageAsParagraph_out.pdf"`與所需的輸出檔名。

### 使用 Aspose.PDF for .NET 的文字和圖像作為段落的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//實例化文件實例
Document doc = new Document();
//將頁面加入到 Document 實例的頁面集合中
Page page = doc.Pages.Add();
//建立文字片段網
TextFragment text = new TextFragment("Hello World.. ");
//將文字片段加入到 Page 物件的段落集合中
page.Paragraphs.Add(text);
//建立圖像實例
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
//將圖像設定為內聯段落，以便它出現在
//上一段物件（TextFragment）
image.IsInLineParagraph = true;
//指定影像檔案路徑
image.File = dataDir + "aspose-logo.jpg";
//設定影像高度（可選）
image.FixHeight = 30;
//設定圖像寬度（可選）
image.FixWidth = 100;
//將圖像加入頁面物件的段落集合中
page.Paragraphs.Add(image);
//使用不同的內容重新初始化 TextFragment 對象
text = new TextFragment(" Hello Again..");
//將 TextFragment 設定為內嵌段落
text.IsInLineParagraph = true;
//將新建立的 TextFragment 加入到頁面的段落集合中
page.Paragraphs.Add(text);
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as an inline paragraphs.\nFile saved at " + dataDir);
```

## 結論

恭喜！您已成功學習如何使用 Aspose.PDF for .NET 在 PDF 文件中新增文字和影像作為內聯段落。本教學課程提供了從設定項目到儲存修改後的文件的逐步指南。現在，您可以將此程式碼合併到您自己的 C# 專案中，以自訂 PDF 檔案中文字和圖像的佈局。

### 常見問題解答

#### Q：「文字和圖像作為 PDF 文件中的段落」教學的目的是什麼？

答：「文字和圖像作為 PDF 文件中的段落」教學課程旨在指導使用者如何使用 Aspose.PDF for .NET 在 PDF 文件中添加文字和圖像作為內聯段落。本教程提供逐步說明和 C# 程式碼範例來演示該過程。

#### Q：本教學如何幫助添加文字和圖像作為內嵌段落？

答：本教學幫助使用者了解如何使用 Aspose.PDF for .NET 將文字和影像合併為 PDF 文件中的內嵌段落。透過遵循提供的步驟和程式碼範例，使用者可以建立具有結合文字和圖像的自訂佈局的 PDF 檔案。

#### Q：學習本教程需要滿足哪些先決條件？

答：在開始本教學之前，您應該對 C# 程式語言有基本的了解。此外，您需要安裝 Aspose.PDF for .NET 程式庫。您可以從 Aspose 網站取得它或使用 NuGet 將其安裝到您的專案中。

#### Q：如何設定我的專案來遵循本教學？

答：首先，在您首選的整合開發環境 (IDE) 中建立一個新的 C# 項目，並新增對 Aspose.PDF for .NET 程式庫的參考。這使您可以利用該庫的功能來處理 PDF 文件、文字片段和圖像。

#### Q：我可以使用本教學在 PDF 中添加多個文字和圖像段落嗎？

答：是的，您可以使用提供的程式碼範例在同一 PDF 文件中新增文字和圖像段落的多個實例。本教學課程示範如何建立內嵌段落，從而輕鬆包含文字和圖像的不同組合。

#### Q：如何指定文字段落和圖像的內容和外觀？

 A：本教學示範如何創建`TextFragment`代表文本段落的物件和`Aspose.Pdf.Image`物件來表示圖像。您可以使用提供的程式碼範例自訂文字和圖像的內容、尺寸和外觀。

#### Q：我可以調整內嵌段落的佈局嗎？

答：是的，您可以透過控制內嵌段落在頁面內的位置、尺寸和順序來調整內嵌段落的佈局。本教學展示如何設定內聯屬性，例如`IsInLineParagraph`，控製文字和圖像段落的佈局。

#### Q：如何儲存修改後的PDF文件？

 A：若要儲存修改後的PDF文檔，您可以使用`Save`的方法`Document`目的。本教學提供了示範如何保存生成的 PDF 文件的程式碼範例。