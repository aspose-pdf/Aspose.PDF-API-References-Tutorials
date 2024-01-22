---
title: 在 PDF 檔案中指定行距
linktitle: 在 PDF 檔案中指定行距
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 檔案中指定行距。
type: docs
weight: 510
url: /zh-hant/net/programming-with-text/specify-line-spacing/
---
本教學課程說明如何使用 Aspose.PDF for .NET 在 PDF 檔案中指定行距。提供的 C# 原始程式碼逐步演示了該過程。

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
using System.IO;
```

## 第三步：設定文檔目錄路徑

使用以下命令設定文檔目錄的路徑`dataDir`多變的：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

## 第 4 步：載入輸入的 PDF 文件

使用以下命令載入輸入 PDF 文件`Document`班級：

```csharp
Document doc = new Document();
```

## 第 5 步：建立 TextFormattingOptions

創建一個`TextFormattingOptions`物件並將行距模式設定為`FullSize`:

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

## 第 6 步：建立一個 TextFragment

創建一個`TextFragment`物件並指定文字內容：

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

## 第7步：載入字型檔案（可選）

如果要在文字中使用特定字體，請將 TrueType 字體檔案載入到`FileStream`目的：

```csharp
string fontFile = dataDir + "HPSimplified.TTF";
using (FileStream fontStream = File.OpenRead(fontFile))
{
    textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
}
```

代替`"HPSimplified.TTF"`與實際的字體檔案名稱。

## 步驟8：指定文字位置和行距

設定文字片段的位置並指定`TextFormattingOptions`到`TextState.FormattingOptions`財產：

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

## 步驟 9：將文字加入文件中

將文字片段新增至文件中，方法是將其附加到`TextBuilder`或直接到頁面`Paragraphs`收藏：

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

## 第10步：儲存生成的PDF文檔

儲存修改後的PDF文件：

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

確保更換`"SpecifyLineSpacing_out.pdf"`與所需的輸出檔名。

### 使用 Aspose.PDF for .NET 指定行距的範例原始程式碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
//加載輸入 PDF 文件
Document doc = new Document();
//使用 LineSpacingMode.FullSize 建立 TextFormattingOptions
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
//為文件第一頁建立文字產生器對象
//TextBuilder textBuilder = new TextBuilder(doc.Pages[1]);
//使用範例字串建立文字片段
TextFragment textFragment = new TextFragment("Hello world");
if (fontFile != "")
{
	//將 TrueType 字型載入到串流物件中
	using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
	{
		//設定文字字串的字體名稱
		textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
		//指定文字片段的位置
		textFragment.Position = new Position(100, 600);
		//將目前片段的 TextFormattingOptions 設定為預先定義（指向 LineSpacingMode.FullSize）
		textFragment.TextState.FormattingOptions = formattingOptions;
		//將文字新增至 TextBuilder，以便可以將其放置在 PDF 文件上
		//textBuilder.AppendText(textFragment);
		var page = doc.Pages.Add();
		page.Paragraphs.Add(textFragment);
	}
	dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
	//儲存生成的 PDF 文檔
	doc.Save(dataDir);
}
```

## 結論

恭喜！您已成功學習如何使用 Aspose.PDF for .NET 在 PDF 文件中指定行距。本教學課程提供了從設定項目到儲存修改後的文件的逐步指南。現在，您可以將此程式碼合併到您自己的 C# 專案中，以自訂 PDF 檔案中文字的行距。

### 常見問題解答

#### Q：「指定 PDF 檔案中的行距」教學的目的為何？

答：「在 PDF 檔案中指定行距」教學課程旨在指導使用者如何使用 .NET 的 Aspose.PDF 庫自訂 PDF 文件中文字的行距。本教程提供逐步說明和 C# 程式碼範例來演示該過程。

#### Q：本教學如何幫助指定 PDF 文件中的行間距？

答：本教學幫助使用者了解如何利用 Aspose.PDF for .NET 的功能來指定 PDF 文件中文字的行距。透過遵循提供的步驟和程式碼範例，使用者可以根據自己的喜好調整行間距。

#### Q：學習本教程需要滿足哪些先決條件？

答：在開始本教學之前，您應該對 C# 程式語言有基本的了解。此外，您需要安裝 Aspose.PDF for .NET 程式庫。您可以從 Aspose 網站取得它或使用 NuGet 將其安裝到您的專案中。

#### Q：如何設定我的專案來遵循本教學？

答：首先，在您首選的整合開發環境 (IDE) 中建立一個新的 C# 項目，並新增對 Aspose.PDF for .NET 程式庫的參考。這使您能夠利用該程式庫的功能來處理 PDF 文件和自訂行距。

#### Q：我可以使用本教學指定任何類型文字的行間距嗎？

答：是的，本教學提供如何使用 Aspose.PDF for .NET 為 PDF 文件中的任何文字內容指定行距的說明。您可以使用提供的程式碼範例根據您的需求調整文字的行距。

#### Q：教學中如何指定行距模式？

答：本教學示範如何創建`TextFormattingOptions`對象並設定其`LineSpacing`財產給`TextFormattingOptions.LineSpacingMode.FullSize`。此模式指定文字內容的整行間距。

#### Q：如何載入文字的特定字體？

答：如果您希望在文字內容中使用特定字體，本教學提供如何將 TrueType 字體檔案載入到`FileStream`對象並將其設定為字體`TextFragment`。這使您能夠自訂文字的字體及其行距。

#### Q：如何自訂 PDF 文件中文字的位置？

 A：若要自訂文字的位置，請建立一個`TextFragment`對象並設定其`Position`屬性到所需的座標（X 和 Y）。這使您可以控製文字在 PDF 文件中的放置位置。

#### Q：我可以將這些行間距修改套用到現有 PDF 文件嗎？

答：是的，您可以修改現有 PDF 文件中文字的行距。本教學示範如何創建`TextFragment`以指定的行距和位置，然後將其新增至頁面的`Paragraphs`收藏。