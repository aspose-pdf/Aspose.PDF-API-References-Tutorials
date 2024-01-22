---
title: 頁首頁腳中使用浮動框的頁碼
linktitle: 頁首頁腳中使用浮動框的頁碼
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件的頁首和頁尾中新增頁碼。
type: docs
weight: 150
url: /zh-hant/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
在本教學中，我們將逐步指導您如何使用 FloatingBox 和 Aspose.PDF for .NET 在 PDF 文件的頁首和頁尾中新增頁碼。我們將使用提供的 C# 原始程式碼建立 PDF 文檔，新增頁面，建立 FloatingBox，設定其位置並新增頁碼，然後儲存修改後的 PDF 文件。

## 第一步：建構環境

在開始之前，請確保您具備以下條件：

- 已安裝的 .NET 開發環境。
- 下載 .NET 的 Aspose.PDF 庫並在您的專案中引用。

## 步驟 2：建立 PDF 文件並新增頁面

第一步是建立 PDF 文件的實例並向其中新增頁面。就是這樣：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//實例化 PDF 文件
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

//為 PDF 文件新增頁面
Aspose.Pdf.Page page = pdf.Pages.Add();
```

請務必將「您的文件目錄」替換為您要儲存 PDF 文件的目錄的實際路徑。

## 第三步：建立FloatingBox並新增頁碼

現在頁面已新增到 PDF 文件中，我們可以建立一個 FloatingBox，設定其位置，並向其添加頁碼。就是這樣：

```csharp
//建立一個寬度為 140、高度為 80 的 FloatingBox
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

//設定段落的左側位置
box1. Left = 2;

//設定段落頂部位置
box1. Top = 10;

//將頁碼加入 FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

//將FloatingBox加入到頁面中
page.Paragraphs.Add(box1);
```

上面的程式碼建立了一個寬度為 140、高度為 80 的 FloatingBox。接下來，我們透過指定 left 和 top 值來設定其位置。最後，我們使用包含語法「($p/ $P )」的 TextFragment 將頁碼新增至 FloatingBox，該語法將會取代為目前頁碼和總頁數。

## 第四步：儲存修改後的PDF文檔

使用 FloatingBox 將頁碼新增至頁首或頁尾後，我們就可以儲存修改後的 PDF 文件。就是這樣：

```csharp
//儲存修改後的PDF文檔
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```

上述程式碼將編輯後的PDF文件儲存到指定目錄。

### 使用 Aspose.PDF for .NET 使用浮動框在頁首頁腳中頁碼的範例原始碼 
```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//實例化文件實例
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

//將頁面新增至 pdf 文件中
Aspose.Pdf.Page page = pdf.Pages.Add();

//初始化 FloatingBox 類別的新實例
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

//指示段落左側位置的浮點數值
box1.Left = 2;

//指示段落頂部位置的浮點數值
box1.Top = 10;

//將巨集加入到 FloatingBox 的段落集合中
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

//給頁面新增一個floatingBox
page.Paragraphs.Add(box1);

//儲存文件
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");

```

## 結論

恭喜！您已經學習如何使用 FloatingBox 和 Aspose.PDF for .NET 在 PDF 文件的頁首和頁尾中新增頁碼。現在，您可以透過新增頁碼等動態資訊來自訂頁首和頁尾。

### 常見問題解答

#### Q：什麼是 FloatingBox，如何使用它在 PDF 文件的頁首或頁尾中添加頁碼？

答：FloatingBox 是 Aspose.PDF 中的多功能佈局元素，可容納各種內容，包括文字和圖像。在本教程中，它用於建立頁碼容器，允許您動態地將當前頁碼和總頁數插入頁首或頁尾中。

#### Q：提供的C#原始碼是如何實現使用FloatingBox新增頁碼的？

答：程式碼片段示範如何建立 PDF 文件、新增頁面、建立 FloatingBox、設定其在頁面內的位置以及使用 TextFragment 插入頁碼。 TextFragment 中的語法「($p/ $P )」被替換為目前頁碼和總頁數。

#### Q：我可以自訂使用 FloatingBox 新增的頁碼的外觀和格式嗎？

答：是的，您可以透過修改 FloatingBox 內 TextFragment 的屬性來自訂頁碼的外觀。您可以變更字體大小、顏色、樣式、對齊方式和其他格式選項。

#### Q：是否可以使用類似的方法為頁首或頁尾添加不同的動態元素（例如日期和時間）？

答：當然，您可以透過修改 FloatingBox 中的 TextFragment 內容來新增不同的動態元素，例如日期、時間、文件元資料或自訂文字。您可以使用「($p/ $P )」等巨集來表示頁碼，或使用「($date)」來表示目前日期。

#### Q：如何指定 FloatingBox 在頁首或頁尾部分中的位置？
答：提供的程式碼使用以下指令設定 FloatingBox 的位置`Left`和`Top`特性。您可以調整這些值以根據需要在頁首或頁尾部分中定位 FloatingBox。

#### Q：頁首或頁尾中的頁碼可以使用不同的字體或樣式嗎？

答：是的，您可以透過修改 FloatingBox 中的 TextFragment 屬性來自訂頁碼文字的字型、樣式和其他格式屬性。

#### Q：如果 FloatingBox 中的內容超出其尺寸會發生什麼？

答：如果 FloatingBox 內的內容超出其尺寸，則可能會被截斷或出現佈局問題。確保 FloatingBox 的尺寸適合容納內容，並根據需要考慮調整頁面佈局。

#### Q：是否可以在同一頁面的頁首或頁尾新增多個不同內容的FloatingBox？

答：是的，您可以透過建立單獨的 FloatingBox 實例並將它們新增到頁面的 Paragraphs 集合中，將多個具有不同內容的 FloatingBox 新增到同一頁面的頁首或頁尾。

#### Q：我可以使用 FloatingBox 方法將內容新增至 PDF 文件的其他部分，例如正文或頁邊距嗎？

答：雖然 FloatingBox 通常用於頁首和頁腳，但您也可以使用它們將內容新增至 PDF 文件的其他部分，例如正文或頁邊距，方法是將它們相應地定位在頁面內。