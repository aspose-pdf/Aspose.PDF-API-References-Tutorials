---
title: 頁眉頁腳部分內嵌的影像和頁碼
linktitle: 頁眉頁腳部分內嵌的影像和頁碼
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 的內嵌段落在頁首和頁尾中新增圖像和頁碼。
type: docs
weight: 120
url: /zh-hant/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
在本教學中，我們將逐步指導您如何使用 Aspose.PDF for .NET 在 PDF 文件的頁首和頁尾部分中添加圖像和頁碼。我們將使用提供的 C# 原始程式碼建立頁面、設定頁首和頁尾、使用 PDF 文件頁首中的內嵌段落新增圖像和文字。

## 第一步：建構環境

在開始之前，請確保您具備以下條件：

- 已安裝的 .NET 開發環境。
- 下載 .NET 的 Aspose.PDF 庫並在您的專案中引用。

## 第 2 步：建立 PDF 文件和頁面

第一步是在 PDF 文件中建立一個新的 Document 物件和一個頁面。方法如下：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//建立一個新的文檔對象
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

//在文件中建立頁面
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

上面的程式碼在 PDF 文件中建立一個新的 Document 物件和一個空頁面。

## 步驟 3：新增帶有圖像和內嵌文字的標題

現在頁面已創建，我們可以使用內聯段落添加帶有圖像和文字的標題部分。方法如下：

```csharp
//建立標題部分
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//設定頁眉
page. Header = header;

//為第一個內聯文字建立 TextFragment 對象
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a robust component developed by");

//指定文字顏色
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

//為影像建立一個 Image 對象
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

//設定圖片路徑
image1.File = dataDir + "aspose-logo.jpg";

//定義影像的尺寸
image1.FixWidth = 50;
image1.FixHeight = 20;

//指示第一個內嵌文字是影像
image1.IsInLineParagraph = true;

//建立第二個內嵌文字
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;

//將項目新增至標題
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

上面的程式碼建立一個標題部分，使用此部分設定頁面標題，添加一個帶有內聯文字和內聯圖像物件的 TextFragment。

## 第四步：儲存修改後的PDF文檔

在新增帶有圖像和內嵌文字的標題後，我們可以儲存修改後的 PDF 文件。方法如下：

```csharp
//儲存修改後的PDF文檔
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

上述程式碼將編輯後的PDF文件儲存到指定目錄。

### 使用 Aspose.PDF for .NET 在頁首頁尾部分內聯中的圖像和頁碼範例原始碼 
```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//透過呼叫其空建構函數來實例化 Document 對象
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

//在 Pdf 物件中建立頁面
Aspose.Pdf.Page page = pdf1.Pages.Add();

//建立文件的標題部分
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//設定 PDF 檔案的標題
page.Header = header;

//建立文字對象
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");

//指定顏色
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

//在該部分中建立圖像對象
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

//設定圖片檔案路徑
image1.File = dataDir + "aspose-logo.jpg";

//設定圖像寬度資訊
image1.FixWidth = 50;
image1.FixHeight = 20;

//指示 seg1 的 InlineParagraph 是圖像。
image1.IsInLineParagraph = true;
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);

//儲存 PDF
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");

```

## 結論

恭喜！您已經了解如何使用 Aspose.PDF for .NET 的內嵌段落在 PDF 文件的頁首和頁尾部分添加圖像和頁碼。現在您可以靈活自訂 PDF 文件的頁首和頁尾。

### 常見問題解答

#### Q：使用內嵌段落將圖像和文字新增至 PDF 文件的頁首有什麼優勢？

答：使用內嵌段落可以讓您將圖像和文字無縫整合在同一段落中，從而精確控制它們的位置和格式。此方法對於創建具有視覺元素的自訂標題特別有用。

#### Q：提供的C#原始碼如何實作PDF文件中標題的內聯段落？

答：提供的程式碼示範如何建立 PDF 文件、新增頁面以及使用內嵌段落自訂頁首。它添加一個帶有內聯文字的 TextFragment、一個內聯圖像和另一個內聯 TextFragment。

#### Q：如何指定頁首內嵌文字的顏色？

答：內聯文字的顏色是使用`ForegroundColor`的財產`TextState`的`TextFragment`目的。

#### Q：我可以調整頁眉內嵌影像的尺寸嗎？

答：是的，您可以使用`FixWidth`和`FixHeight`的屬性`Image`目的。這允許您控制標題內圖像的寬度和高度。

#### Q：我可以在標題中包含其他內聯元素，例如超連結或不同的字體樣式嗎？

答：是的，您可以透過建立更多內容在標題中包含其他內聯元素`TextFragment`或者`Image`具有所需屬性的物件。這允許您進一步自訂標題，包括超連結、不同的字體樣式或其他視覺元素。

#### Q：如何確保內嵌影像和文字在不同裝置和檢視器中保持正確對齊和格式？

答：Aspose.PDF for .NET 可確保內嵌影像和文字正確對齊和格式化，從而在不同裝置和 PDF 檢視器中獲得一致的外觀。

#### Q：我可以將內嵌段落也應用到頁腳部分嗎？

答：是的，您可以透過建立一個`Footer`物件並向其添加內聯元素（例如文字和圖像）。

#### Q：是否可以將內聯段落與其他頁首或頁尾自訂方法結合？

答：是的，您可以將內嵌段落與 Aspose.PDF for .NET 提供的其他頁首或頁尾自訂方法結合起來，以建立更複雜且自訂的頁首或頁尾設計。

#### Q：如果需要，我可以從標題中刪除或清除內聯元素嗎？

 A：是的，您可以透過修改內容來刪除或清除內嵌元素`HeaderFooter`物件並刪除對應的內聯段落。

#### Q：如何將內嵌段落套用至 PDF 文件的特定頁面？

答：要將內嵌段落套用至特定頁面，您可以建立單獨的段落`HeaderFooter`每個頁面的物件並使用`Header`各自的財產`Aspose.Pdf.Page`對象。