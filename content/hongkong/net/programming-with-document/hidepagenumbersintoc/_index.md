---
title: 隱藏目錄中的頁碼
linktitle: 隱藏目錄中的頁碼
second_title: Aspose.PDF for .NET API 參考
description: 透過此逐步指南，了解如何使用 Aspose.PDF for .NET 在目錄中隱藏頁碼。
type: docs
weight: 220
url: /zh-hant/net/programming-with-document/hidepagenumbersintoc/
---
在本文中，我們將討論使用 C# 實作 Aspose.PDF for .NET 的「在目錄中隱藏頁碼」功能。我們將從 Aspose.PDF for .NET 的簡要介紹開始，然後深入了解實現此功能的逐步指南。 

## Aspose.PDF for .NET 簡介

Aspose.PDF for .NET 是一個功能強大的 PDF 操作元件，可讓開發人員以程式設計方式建立、編輯和操作 PDF 檔案。它提供了廣泛的功能和功能，可以輕鬆處理 PDF 文件。 Aspose.PDF for .NET 支援 32 位元和 64 位元作業系統，並且可與 .NET Framework、.NET Core 和 Xamarin 平台一起使用。 

## 什麼是在目錄中隱藏頁碼功能？

目錄 (TOC) 是 PDF 文件的重要組成部分，可讓使用者快速概覽內容。有時，使用者可能希望隱藏目錄中的頁碼以使其更加用戶友好。 Aspose.PDF for .NET 提供了一個內建功能來隱藏目錄中的頁碼。此功能可用於建立更用戶友好的 PDF 文件。 

## 先決條件

要學習本教程，您將需要以下內容：

- Visual Studio 2010 或更高版本
- 您的系統上安裝了 Aspose.PDF for .NET
- C# 程式語言基礎知識

## 實施「在目錄中隱藏頁碼」功能的逐步指南

請依照下列步驟使用 Aspose.PDF for .NET 實作隱藏目錄中的頁碼功能：

## 步驟 1：在 Visual Studio 中建立新的 C# 控制台應用程式

開啟 Visual Studio 並建立一個新的 C# 控制台應用程式。

## 步驟 2：新增 Aspose.PDF for .NET 的引用

右鍵單擊項目中的“引用”資料夾，然後選擇“新增引用”。瀏覽到系統上安裝 Aspose.PDF for .NET 的位置並新增對其的參考。

## 第 1 步：建立一個新的 PDF 文檔

使用以下程式碼建立一個新的 PDF 文件：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
```

## 第 2 步：建立目錄頁面

使用以下程式碼為目錄建立一個新頁面並將其新增至 PDF 文件：

```csharp
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
```

## 步驟 3：將清單部分新增至 PDF 文件的部分集合中

使用以下程式碼將清單部分新增至 PDF 文件的部分集合：

```csharp
tocPage.TocInfo = tocInfo;
```

## 步驟4：定義四級清單的格式

透過使用以下程式碼設定每個層級的左邊距和文字格式設定來定義四級清單的格式：

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
```

## 步驟 5：在該部分中新增四個標題

```csharp

for (int Level = 1; Level != 5; Level++)
{ 
	Heading heading2 = new Heading(Level); 
	TextSegment segment2 = new TextSegment(); 
	heading2.TocPage = tocPage; 
	heading2.Segments.Add(segment2); 
	heading2.IsAutoSequence = true; 
	segment2.Text = "this is heading of level " + Level; 
	heading2.IsInList = true; 
	page.Paragraphs.Add(heading2); 
}
doc.Save(outFile);

```

### 使用 Aspose.PDF for .NET 在目錄中隱藏頁碼的範例原始碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
//將清單部分新增至 Pdf 文件的部分集合中
tocPage.TocInfo = tocInfo;
//透過設定左邊距和定義四級列表的格式
//各級別文字格式設定

tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
//在該部分中添加四個標題
for (int Level = 1; Level != 5; Level++)
	{ 
		Heading heading2 = new Heading(Level); 
		TextSegment segment2 = new TextSegment(); 
		heading2.TocPage = tocPage; 
		heading2.Segments.Add(segment2); 
		heading2.IsAutoSequence = true; 
		segment2.Text = "this is heading of level " + Level; 
		heading2.IsInList = true; 
		page.Paragraphs.Add(heading2); 
	}
doc.Save(outFile);
```

## 結論

在本教學中，我們探討如何使用 Aspose.PDF for .NET 處理 PDF 文件中的 XMP 元資料。 XMP 元資料提供有關 PDF 文件的寶貴信息，包括標題、作者、建立日期等。 Aspose.PDF for .NET 允許開發人員存取和操作這些元數據，提供靈活且強大的 API 來處理 PDF 文件。

### 常見問題解答

#### Q：PDF 文件中的 XMP 元資料是什麼？

答：PDF 文件中的 XMP（可擴充元資料平台）元資料是用於儲存有關文件的元資料資訊的標準格式。它包括文檔標題、作者、創建日期、關鍵字等詳細資訊。 XMP 元資料提供了一種結構化且標準化的方式來儲存和分享有關 PDF 文件的資訊。

#### Q：我可以使用 Aspose.PDF for .NET 修改 PDF 文件的 XMP 元資料嗎？

答：是的，您可以使用 Aspose.PDF for .NET 以程式設計方式修改 PDF 文件的 XMP 元資料。您可以訪問`Info`的財產`Document`對象，它使您可以存取 XMP 元資料屬性。然後，您可以更新這些屬性的值以修改 PDF 文件的 XMP 元資料。

#### Q：我可以使用 Aspose.PDF for .NET 從 PDF 文件中提取自訂 XMP 元資料屬性嗎？

答：是的，您可以使用 Aspose.PDF for .NET 從 PDF 文件中提取自訂 XMP 元資料屬性。您可以使用`Metadata`的財產`Document`對象，它提供對 PDF 文件的所有 XMP 元資料屬性的存取。然後，您可以提取自訂屬性並根據需要使用它們的值。