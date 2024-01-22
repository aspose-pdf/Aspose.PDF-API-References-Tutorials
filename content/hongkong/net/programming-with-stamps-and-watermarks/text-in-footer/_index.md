---
title: PDF 檔案頁尾中的文字
linktitle: PDF 檔案頁尾中的文字
second_title: Aspose.PDF for .NET API 參考
description: 學習使用 Aspose.PDF for .NET 在 PDF 檔案的頁尾中新增文字。
type: docs
weight: 180
url: /zh-hant/net/programming-with-stamps-and-watermarks/text-in-footer/
---
在本教學中，我們將學習如何使用 Aspose.PDF for .NET 在 PDF 檔案的頁尾中新增文字。請依照以下步驟操作：

## 第一步：專案準備

請確定您已安裝 Aspose.PDF for .NET 並建立了 C# 專案。

## 第 2 步：導入命名空間

將以下命名空間新增至 C# 原始檔：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 步驟 3：開啟文檔

使用提供的路徑開啟現有的 PDF 文件：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document pdfDocument = new Document(dataDir + "TextinFooter.pdf");
```

請務必將「您的文件目錄」替換為文件目錄的實際路徑。

## 第 4 步：建立頁腳文本

使用要在頁腳中新增的文字建立新的文字圖章：

```csharp
TextStamp textStamp = new TextStamp("footer text");
```

您可以透過變更文字屬性（例如下邊距、水平對齊方式和垂直對齊方式）來自訂文字。

## 步驟 5：為所有頁面新增頁尾文本

瀏覽 PDF 文件的所有頁面並在頁腳中新增文字圖章：

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## 第6步：儲存PDF文檔

在所有頁面上新增頁尾文字後，儲存更新的 PDF 文件：

```csharp
dataDir = dataDir + "TextinFooter_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at: " + dataDir);
```

請務必將「您的文件目錄」替換為您要儲存 PDF 文件的目錄的實際路徑。

### 使用 Aspose.PDF for .NET 的 Textin 頁尾範例原始碼 
```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//開啟文件
Document pdfDocument = new Document(dataDir+ "TextinFooter.pdf");

//創建頁腳
TextStamp textStamp = new TextStamp("Footer Text");

//設定圖章的屬性
textStamp.BottomMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

//在所有頁面上新增頁腳
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}
dataDir = dataDir + "TextinFooter_out.pdf";

//儲存更新的 PDF 文件
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at " + dataDir);

```

## 結論

恭喜！您已經了解如何使用 Aspose.PDF for .NET 在 PDF 文件的頁尾中新增文字。現在，您可以透過在 PDF 文件中新增其他文字來自訂頁腳。

### PDF 檔案頁尾文字的常見問題解答

#### Q：在 PDF 文件頁腳中新增文字的目的是什麼？

答：在 PDF 文件的頁腳中新增文字可讓您包含重要訊息，例如版權聲明、頁碼、文件版本或您希望在每頁底部一致顯示的任何其他文字。

#### Q：提供的C#原始碼是如何實作PDF文件頁尾新增文字的？

答：程式碼示範了開啟現有PDF 文件、使用所需頁尾文字建立文字圖章、自訂文字屬性、將文字圖章新增至所有頁面，最後儲存包含新增的頁尾文字的更新的PDF 文件的過程。

#### Q：我可以修改頁腳文字的外觀，例如字體、大小、顏色和對齊方式嗎？

答：是的，您可以透過修改頁腳的屬性來自訂頁腳文字的外觀。`TextStamp`目的。此程式碼範例包括設定下邊距、水平對齊和垂直對齊等屬性。您還可以調整字體、大小、顏色和其他與文字相關的屬性。

#### Q：是否可以在每個頁面的頁腳添加不同的文字？

答：是的，您可以透過建立單獨的頁腳來為每個頁面的頁腳添加不同的文本`TextStamp`具有不同文字內容或屬性的對象，然後根據需要將它們新增至特定頁面。

#### Q：如何確保頁尾文字在 PDF 文件的每一頁上一致顯示？

答：透過使用循環遍歷 PDF 文件的所有頁面並為每個頁面添加相同的文字圖章，可以確保頁腳文字在每個頁面上一致顯示。

#### Q：我可以新增多行文字或使用換行符號設定頁尾文字格式嗎？

答：是的，您可以透過在文字字串中包含換行符號來為頁腳添加多行文字。例如，您可以使用轉義序列`\n`指示文字中的換行符。

#### Q：如果我想在同一個 PDF 文件的頁首和頁尾中添加不同的內容，會發生什麼情況？

答：若要為頁首和頁尾部分新增不同的內容，您將為這兩個部分執行類似的步驟。程式碼演示了向頁腳添加文字；您可以使用類似的方法將文字新增至標題。

#### Q：是否可以使用此方法在頁尾文字旁邊添加圖像或其他元素？

答：雖然提供的程式碼專門示範了向頁腳添加文本，但您可以擴展該方法，使用 Aspose.PDF 庫將其他元素（例如圖像、線條、形狀或任何其他內容）添加到頁腳部分。