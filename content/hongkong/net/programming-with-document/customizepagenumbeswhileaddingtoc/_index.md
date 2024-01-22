---
title: 新增目錄時自訂頁碼
linktitle: 新增目錄時自訂頁碼
second_title: Aspose.PDF for .NET API 參考
description: 透過此逐步指南和程式碼範例，了解如何使用 Aspose.PDF for .NET 新增目錄 (TOC) 時自訂頁碼。
type: docs
weight: 100
url: /zh-hant/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---
在本教學中，我們將探討如何使用 Aspose.PDF for .NET 新增目錄 (TOC) 時自訂頁碼。我們將提供逐步指導以及程式碼範例，以幫助您實現這一目標。

## 第 1 步：載入現有 PDF 文件

首先，我們需要載入現有的 PDF 檔案。在本教學中，我們將使用位於「您的文件目錄」目錄中的檔案「42824.pdf」。將此目錄路徑替換為文件目錄的實際路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
Document doc = new Document(inFile);
```

## 第 2 步：新增 TOC 頁面

接下來，我們需要在文件的開頭新增一個頁面作為目錄頁面。我們可以透過使用來實現這一點`Insert()`的方法`Pages`的集合`Document`目的。

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

## 第 3 步：建立 TOC 對象

要建立 TOC 對象，我們首先需要建立一個`TocInfo`對象並設定其屬性。在本教程中，我們將目錄標題設為“目錄”，頁碼前綴設定為“P”。

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

## 第 4 步：建立目錄條目

要建立目錄條目，我們需要循環遍歷文件的所有頁面（目錄頁面除外），並為每個頁面建立標題物件。然後，我們可以將標題物件新增至目錄頁面並指定其目標頁面。

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    //建立標題對象
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    //指定標題物件的目標頁面
    heading2.DestinationPage = doc.Pages[i + 1];
    //目的地頁面
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    //目的地座標
    segment2.Text = "Page " + i.ToString();
    //將標題新增至包含目錄的頁面
    tocPage.Paragraphs.Add(heading2);
}
```

## 步驟 5：儲存更新的文檔

最後，我們需要將更新的文檔儲存到新文件中。我們可以透過使用來實現這一點`Save()`的方法`Document`目的。

```csharp
doc.Save(outFile);
```

### 使用 Aspose.PDF for .NET 新增目錄時自訂頁碼的範例原始碼

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
//載入現有的 PDF 文件
Document doc = new Document(inFile);
//造訪 PDF 檔案的第一頁
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
//建立物件來表示 TOC 訊息
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
//設定目錄標題
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
for (int i = 1; i<doc.Pages.Count; i++)
{
	//建立標題對象
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);
	//指定標題物件的目標頁面
	heading2.DestinationPage = doc.Pages[i + 1];
	//目的地頁面
	heading2.Top = doc.Pages[i + 1].Rect.Height;
	//目的地座標
	segment2.Text = "Page " + i.ToString();
	//將標題新增至包含目錄的頁面
	tocPage.Paragraphs.Add(heading2);
}

//儲存更新後的文檔
doc.Save(outFile);
```

## 結論

在本教學中，我們提供瞭如何使用 Aspose.PDF for .NET 新增目錄時自訂頁碼的逐步指南。我們還提供了一個程式碼範例，您可以在自己的系統中實現此功能時作為參考。

### 常見問題解答

#### Q：什麼是 PDF 文件中的目錄 (TOC)？

答：PDF 文件中的目錄 (TOC) 是一種導覽輔助工具，它提供了文件部分或章節的組織清單及其對應的頁碼。它允許讀者快速導航到文件中的特定部分。

#### Q：為什麼我要自訂目錄中的頁碼？

答：當您想要使用特定的頁碼格式或在頁碼中包含其他資訊時，自訂目錄中的頁碼非常有用。它允許您創建更個性化和資訊豐富的目錄。

#### Q：我可以在目錄中包含超連結來連結到 PDF 文件中的特定部分或頁面嗎？

答：是的，Aspose.PDF for .NET 允許您在目錄中建立超鏈接，連結到 PDF 文件中的特定部分或頁面。這增強了 PDF 文件的互動性和導航性。

#### Q：Aspose.PDF for .NET 與 PDF/A 標準相容嗎？

答：是的，Aspose.PDF for .NET 支援 PDF/A 標準，包括 PDF/A-1、PDF/A-2 和 PDF/A-3。它允許您建立符合存檔和長期保存要求的 PDF 文件。

#### Q：我可以為目錄條目添加更多格式嗎，例如字體樣式或顏色？

答：是的，您可以使用 Aspose.PDF for .NET 在 TOC 條目中新增其他格式，例如字體樣式、顏色和字體大小。這允許您根據您的要求自訂目錄的外觀。
