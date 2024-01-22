---
title: 新增並蒐索 PDF 文件中的隱藏文本
linktitle: 新增並蒐索 PDF 文件中的隱藏文本
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 在 PDF 檔案中新增和搜尋隱藏文字的逐步指南。
type: docs
weight: 20
url: /zh-hant/net/programming-with-text/add-and-search-hidden-text/
---
在本教學中，我們將引導您了解如何使用 Aspose.PDF for .NET 在 PDF 檔案中新增和搜尋隱藏文字。請按照以下步驟輕鬆執行此操作。

## 1. 前提條件

在開始之前，請確保您具備以下條件：

- 安裝並設定 Visual Studio 或任何其他開發環境。
- C# 程式語言的基礎知識。
- 安裝了適用於.NET 的 Aspose.PDF 庫。您可以從Aspose官方網站下載。

## 2. 建立帶有隱藏文字的PDF文檔

首先，使用以下程式碼建立一個包含隱藏文字的新 PDF 文件：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//建立文檔
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
//設定文字屬性-不可見
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

請務必提供 PDF 文件所需的路徑和文件名稱。

## 3. 在文件中搜尋文本

接下來，我們將搜尋PDF文件中的隱藏文字。使用以下程式碼：

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb.Visit(doc.Pages[1]);
foreach(TextFragment fragment in absorber.TextFragments)
{
//用碎片做一些事情
Console.WriteLine("Text '{0}' at position {1}, invisibility: {2} ",
fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

這將搜尋 PDF 文件第二頁中的隱藏文字並顯示相關資訊。

### 使用 Aspose.PDF for .NET 新增和搜尋隱藏文字的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//建立帶有隱藏文字的文檔
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
//設定文字屬性-不可見
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
//搜尋文件中的文字
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
foreach (TextFragment fragment in absorber.TextFragments)
{
	//用碎片做一些事情
	Console.WriteLine("Text '{0}' on pos {1} invisibility: {2} ",
	fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

## 結論

恭喜！您已使用 Aspose.PDF for .NET 在 PDF 文件中成功新增並找到了隱藏文字。現在您可以將此方法應用到您自己的專案中，以操作和搜尋 PDF 文件中的隱藏文字。

### 常見問題解答

#### Q：什麼是 Aspose.PDF for .NET？

答：Aspose.PDF for .NET 是一個強大的程式庫，使開發人員能夠在 .NET 應用程式中建立、操作和轉換 PDF 文件。

#### Q：隱藏文字可以用於浮水印嗎？

答：當然！隱藏文字可以作為為 PDF 文件添加浮水印的有效方法，增加額外的安全層。

#### Q：是否可以顯示 PDF 文件中的隱藏文字？

答：是的，搜尋和顯示 PDF 文件中隱藏文字的過程可以使用本教程中概述的技術來實現。

#### Q：Aspose.PDF for .NET 還提供哪些其他功能？

答：除了隱藏文字操作之外，Aspose.PDF for .NET 還提供了廣泛的功能，包括 PDF 產生、轉換、加密等。