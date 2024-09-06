---
title: 頁眉頁尾部分中的圖像和頁碼
linktitle: 頁眉頁尾部分中的圖像和頁碼
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose 在 PDF 文件的頁首和頁尾中新增圖像和頁碼。
type: docs
weight: 110
url: /zh-hant/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section/
---
在本教學中，我們將逐步指導您如何使用 Aspose.PDF for .NET 在 PDF 文件的頁首和頁尾部分中添加圖像和頁碼。我們將向您展示如何使用提供的 C# 原始程式碼建立頁面、設定頁首和頁尾、向頁首添加圖像以及在文件頁腳 PDF 新增帶有頁碼的文字。

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
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

//在文件中建立頁面
Aspose.Pdf.Page page = doc.Pages.Add();
```

上面的程式碼在 PDF 文件中建立一個新的 Document 物件和一個空頁面。

## 步驟 3：新增帶有圖像的標題

現在頁面已創建，我們可以添加帶有圖像的標題部分。方法如下：

```csharp
//建立標題部分
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//設定頁眉
page. Header = header;

//建立影像對象
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

//設定圖片路徑
image1.File = dataDir + "aspose-logo.jpg";

//將影像新增至 PDF 文件的頁眉
header.Paragraphs.Add(image1);
```

上面的程式碼會建立一個標題部分，使用此部分設定頁面標題，並為標題添加圖像。

## 步驟 4：新增頁尾和頁碼

現在新增了頁眉，我們可以新增帶有頁碼的頁尾部分。方法如下：

```csharp
//建立頁尾部分
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

//定義 PDF 文件的頁尾
page. Footer = footer;

//建立一個 TextFragment 對象
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P)");

//將帶有頁碼的文字新增至 PDF 文件的頁腳
footer.Paragraphs.Add(txt);
```

上面的程式碼建立一個頁腳部分，用此部分設定頁面的頁腳，並新增一個包含文字「Page: ($p of $P )」的 TextFragment

  顯示頁碼。

## 步驟5：儲存修改後的PDF文檔

在新增頁首和頁尾後，我們就可以儲存修改後的PDF文件。方法如下：

```csharp
//儲存修改後的PDF文檔
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");
```

上述程式碼將編輯後的PDF文件儲存到指定目錄。

### 使用 Aspose.PDF for .NET 的頁首頁尾部分中的圖片和頁碼範例原始碼 
```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

//在文件物件中建立頁面
Aspose.Pdf.Page page = doc.Pages.Add();

//建立文件的標題部分
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//設定 PDF 檔案的標題
page.Header = header;

//在頁面中建立一個圖像對象
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

//設定圖片檔案路徑
image1.File = dataDir + "aspose-logo.jpg";

//將圖像新增至 Pdf 檔案的頁眉
header.Paragraphs.Add(image1);

//建立文檔的頁尾部分
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

//設定 PDF 文件的頁腳
page.Footer = footer;

//建立文字對象
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P ) ");

//將文字新增至 Pdf 檔案的頁首部分
footer.Paragraphs.Add(txt);

//儲存 PDF 文件
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");

```

## 結論

恭喜！您已經了解如何使用 Aspose.PDF for .NET 在 PDF 文件的頁首和頁尾部分中新增圖像和頁碼。現在您可以使用此方法自訂 PDF 文件中的頁首和頁尾。

### 常見問題解答

#### Q：在 PDF 文件的頁首和頁尾部分添加圖像和頁碼的目的是什麼？

答：在 PDF 文件的頁首和頁尾部分添加圖像和頁碼可以增強其視覺吸引力、品牌和導航元素。圖像可以代表徽標、浮水印或任何圖形元素，而頁碼可以幫助使用者追蹤進度並找到特定頁面。

#### Q：提供的 C# 原始程式碼如何協助將圖像和頁碼新增至 PDF 文件的頁首和頁尾？

答：提供的程式碼示範如何建立 PDF 文件、新增頁面，然後自訂頁首和頁尾部分。它演示瞭如何將圖像添加到頁眉以及如何將帶有頁碼的文字片段添加到頁腳。

#### Q：標題可以使用任何圖像格式嗎？

答：是的，您可以使用各種圖像格式（例如 JPEG、PNG、GIF 等）作為標題圖像。影像的路徑是使用指定的`File`的財產`Aspose.Pdf.Image`目的。

#### Q：如何自訂標題部分中圖像的外觀和位置？

答：您可以透過調整影像的屬性來自訂影像的外觀和位置。`Aspose.Pdf.Image`對象，然後將其新增至標題部分。例如，您可以設定影像的尺寸、對齊方式、旋轉、不透明度等。

####  Q：這樣做的目的是什麼`TextFragment` object used for the footer?

答： 的`TextFragment`物件用於建立將在頁腳部分顯示的文字並設定其格式。在提供的程式碼中，它用於顯示頁碼和總頁數。

#### Q：我可以修改頁尾文字以包含其他資訊或格式嗎？

 A：是的，您可以透過修改頁腳的內容來修改頁尾文本`TextFragment`目的。您可以根據需要添加其他文字、更改字體、顏色和格式。

#### Q：我可以對 PDF 文件的不同頁面套用不同的頁首和頁尾內容嗎？

答：是的，您可以透過建立單獨的頁面來將不同的頁首和頁尾內容套用到不同的頁面`HeaderFooter`物件並使用以下方法將它們指派給特定頁面`Header`和`Footer`的屬性`Aspose.Pdf.Page`目的。

#### Q：如何進一步自訂頁首和頁腳，例如變更字體樣式或新增其他元素？

答：您可以使用 Aspose.PDF for .NET 提供的各種類別和屬性來自訂頁首和頁尾。例如，您可以使用不同的文字格式選項，為頁首和頁尾部分新增更多段落、圖像甚至表格。

#### Q：如果需要，我可以刪除或清除頁首和頁尾部分嗎？

答：是的，您可以透過設定刪除或清除頁首和頁尾部分`Header`和`Footer`的屬性`Aspose.Pdf.Page`反對`null`.

#### Q：如何確保新增的影像和頁碼在不同裝置和檢視者之間保持一致？

答：Aspose.PDF for .NET 提供了建立標準化且一致的 PDF 文件的功能，確保新增的影像和頁碼在不同的裝置和 PDF 檢視器中顯示一致。