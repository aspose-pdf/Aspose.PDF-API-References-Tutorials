---
title: 新增目錄到 PDF 文件
linktitle: 新增目錄到 PDF 文件
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 將目錄新增至 PDF 檔案。帶有範例原始程式碼的分步指南。增強文件導航！
type: docs
weight: 40
url: /zh-hant/net/programming-with-document/addtoc/
---
在本教學中，我們將探討如何使用 Aspose.PDF for .NET 的「將 TOC（目錄）新增至 PDF 檔案」功能將目錄新增至 PDF 文件。我們將提供逐步指南並解釋實現此目的所需的 C# 原始程式碼。在本教學結束時，您將能夠使用 Aspose.PDF for .NET 產生帶有目錄的 PDF 文件。


## 第 1 步：載入現有 PDF 文件

首先，我們需要載入現有的 PDF 檔案。代替`"YOUR DOCUMENT DIRECTORY"`在以下程式碼中新增 PDF 檔案的實際路徑：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

## 步驟 2：為目錄建立一個新頁面

我們將建立一個新頁面來保存目錄。以下程式碼在索引 1 處插入一個新頁面：

```csharp
Page tocPage = doc.Pages.Insert(1);
```

## 步驟 3：定義目錄訊息

接下來，我們需要定義目錄資訊。我們將設定目錄的標題和其他屬性。新增以下程式碼：

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

## 第 4 步：建立目錄元素

現在，我們將建立目錄的元素。在本教程中，我們將建立對應於不同頁面的四個目錄元素。根據您的要求修改以下程式碼：

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";

for (int i = 0; i < 2; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);

    heading2.DestinationPage = doc.Pages[i + 2];
    heading2.Top = doc.Pages[i + 2].Rect.Height;

    segment2.Text = titles[i];
    tocPage.Paragraphs.Add(heading2);
}
```

## 步驟 5：儲存更新後的文檔

最後，我們需要將修改後的文件與目錄一起儲存。代替`"YOUR DOCUMENT DIRECTORY"`在下面的程式碼中使用所需的輸出檔案路徑：

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

### 使用 Aspose.PDF for .NET 將 TOC 新增至 PDF 文件的範例原始程式碼

```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//載入現有的 PDF 文件
Document doc = new Document(dataDir + "AddTOC.pdf");

//造訪 PDF 檔案的第一頁
Page tocPage = doc.Pages.Insert(1);

//建立物件來表示 TOC 訊息
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

//設定目錄標題
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;

//建立將用作目錄元素的字串對象
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
for (int i = 0; i < 2; i++)
{
	//建立標題對象
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);

	//指定標題物件的目標頁面
	heading2.DestinationPage = doc.Pages[i + 2];

	//目的地頁面
	heading2.Top = doc.Pages[i + 2].Rect.Height;

	//目的地座標
	segment2.Text = titles[i];

	//將標題新增至包含目錄的頁面
	tocPage.Paragraphs.Add(heading2);
}
dataDir = dataDir + "TOC_out.pdf";
//儲存更新後的文檔
doc.Save(dataDir);

Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

## 結論

在本教學中，我們探討如何使用 Aspose.PDF for .NET 將目錄 (TOC) 新增至 PDF 文件。透過遵循逐步指南並利用提供的 C# 原始程式碼，您可以輕鬆產生帶有目錄的 PDF 文件。 TOC 增強了文件的可用性，讓使用者更有效地導航到特定部分或頁面。 Aspose.PDF for .NET 提供了一個強大且用戶友好的解決方案，用於在 .NET 應用程式中處理 PDF 文件，使您能夠輕鬆建立動態和互動式 PDF 文件。

### 將目錄新增至 PDF 檔案的常見問題解答

#### Q：什麼是 Aspose.PDF for .NET？

答：Aspose.PDF for .NET 是一個功能強大的程式庫，可讓開發人員在 .NET 應用程式中有效地處理 PDF 檔案。它提供了廣泛的功能，可以程式設計方式建立、操作和管理 PDF 文件。

#### Q：在 PDF 文件中新增目錄 (TOC) 的目的是什麼？

答：目錄 (TOC) 為使用者提供導覽協助，使他們能夠快速跳到 PDF 文件中的特定部分或頁面。它提高了文件的可用性和用戶體驗。

#### Q：如何使用 Aspose.PDF for .NET 將目錄新增至 PDF 文件？

答：要使用 Aspose.PDF for .NET 將目錄新增至 PDF 文件中，您需要建立一個新頁面來保存 TOC，定義目錄信息，然後建立與特定頁面或對應的 TOC 元素文件中的部分。

#### Q：我可以自訂目錄的外觀嗎？

答：是的，您可以透過設定目錄元素的各種屬性（例如字體大小、字體樣式和對齊方式）來自訂目錄的外觀。 Aspose.PDF for .NET 提供了設計目錄的靈活性，以配合您所需的外觀和感覺。

#### Q：Aspose.PDF for .NET 是否適合為 PDF 文件新增進階功能？

答：當然，Aspose.PDF for .NET 是一個功能豐富的函式庫，可讓您為 PDF 文件添加進階功能，包括互動元素、表單欄位、數位簽章等。