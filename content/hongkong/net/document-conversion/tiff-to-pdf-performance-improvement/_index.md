---
title: TIFF 轉 PDF 效能改進
linktitle: TIFF 轉 PDF 效能改進
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 將 TIFF 提高到 PDF 轉換效能的逐步指南。
type: docs
weight: 310
url: /zh-hant/net/document-conversion/tiff-to-pdf-performance-improvement/
---
在本教學中，我們將逐步引導您了解如何使用 .NET 的 Aspose.PDF 庫提高將 TIFF 檔案轉換為 PDF 的效能。我們將詳細介紹所提供的 C# 原始程式碼，並向您展示如何在您自己的專案中實現它。在本教學結束時，您將能夠更快、更有效率地將 TIFF 檔案轉換為 PDF。

## 步驟1：設定文檔目錄
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
代替`"YOUR DOCUMENTS DIRECTORY"`與您儲存文件的路徑。

## 第 2 步：取得 TIFF 檔案列表
```csharp
string[] files = System.IO.Directory.GetFiles(dataDir, "*.tif");
```
取得指定目錄中存在的 TIFF 檔案的清單。

## 第 3 步：實例化 Document 對象
```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```
建立 Document 物件的實例。

## 步驟 4：瀏覽文件並新增至 PDF 文檔
```csharp
foreach (string myFile in files)
{
     FileStream fs = new FileStream(myFile, FileMode.Open, FileAccess.Read);
     byte[] tmpBytes = new byte[fs.Length];
     fs.Read(tmpBytes, 0, Convert.ToInt32(fs.Length));

     MemoryStream mystream = new MemoryStream(tmpBytes);
     Bitmap b = new Bitmap(mystream);
     Aspose.Pdf.Page currpage = doc.Pages.Add();

     currpage.PageInfo.Margin.Top = 5;
     currpage.PageInfo.Margin.Bottom = 5;
     currpage.PageInfo.Margin.Left = 5;
     currpage.PageInfo.Margin.Right = 5;

     currpage.PageInfo.Width = (b.Width / b.HorizontalResolution) * 72;
     currpage.PageInfo.Height = (b.Height / b.VerticalResolution) * 72;

     Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

     currpage.Paragraphs.Add(image1);

     image1.IsBlackWhite = true;
     image1.ImageStream = mystream;
     image1.ImageScale = 0.95F;
}
```
瀏覽每個 TIFF 文件，將其加載為`Bitmap`對象，然後將其新增至 PDF 文件中。還可以配置影像的邊距、解析度和比例等參數。

## 第 5 步：儲存生成的 PDF 文件
```csharp
doc.Save(dataDir + "PerformaceImprovement_out.pdf");
```
將產生的 PDF 文件儲存到指定目錄。

### 使用 Aspose.PDF for .NET 將 TIFF 提高到 PDF 效能的範例原始碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//取得 tiff 影像檔列表
string[] files = System.IO.Directory.GetFiles(dataDir, "*.tif");

//實例化一個文檔對象
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

//瀏覽文件以及 pdf 文件中的文件
foreach (string myFile in files)
{

	//載入位元組數組中的所有 tiff 文件
	FileStream fs = new FileStream(myFile, FileMode.Open, FileAccess.Read);
	byte[] tmpBytes = new byte[fs.Length];
	fs.Read(tmpBytes, 0, Convert.ToInt32(fs.Length));

	MemoryStream mystream = new MemoryStream(tmpBytes);
	Bitmap b = new Bitmap(mystream);
	//在 Pdf 文件中建立一個新頁面
	Aspose.Pdf.Page currpage = doc.Pages.Add();

	//設定邊距以使影像適合等。
	currpage.PageInfo.Margin.Top = 5;
	currpage.PageInfo.Margin.Bottom = 5;
	currpage.PageInfo.Margin.Left = 5;
	currpage.PageInfo.Margin.Right = 5;

	currpage.PageInfo.Width = (b.Width / b.HorizontalResolution) * 72;
	currpage.PageInfo.Height = (b.Height / b.VerticalResolution) * 72;

	//建立影像對象
	Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

	//將圖像加入頁面的段落集合中
	currpage.Paragraphs.Add(image1);

	//將 IsBlackWhite 屬性設為 true 以提高效能
	image1.IsBlackWhite = true;
	//將 ImageStream 設定為 MemoryStream 對象
	image1.ImageStream = mystream;
	//設定所需的影像比例
	image1.ImageScale = 0.95F;
}

//儲存 PDF
doc.Save(dataDir + "PerformaceImprovement_out.pdf");
```

## 結論
在本教學中，我們學習如何使用 .NET 的 Aspose.PDF 庫提高將 TIFF 檔案轉換為 PDF 的效能。透過按照提供的步驟操作，您將能夠更快、更有效地將 TIFF 檔案轉換為 PDF。在優化應用程式效能的同時獲得精確和專業的結果

### 常見問題解答

#### Q：什麼是 Aspose.PDF for .NET？

答：Aspose.PDF for .NET 是一個功能強大的程式庫，可讓開發人員在 C# 應用程式中處理 PDF 文件。它提供各種功能，包括將 TIFF 檔案轉換為 PDF。

#### Q：為什麼我要提高 TIFF 到 PDF 轉換的效能？

答：提高 TIFF 到 PDF 轉換的效能可以顯著提高應用程式的效率，尤其是在處理大量 TIFF 檔案時。更快的轉換可以改善使用者體驗並減少處理時間。

#### Q：如何設定 TIFF 檔案的目錄？

答：您可以透過替換來設定 TIFF 檔案的目錄`"YOUR DOCUMENTS DIRECTORY"`程式碼中的佔位符與 TIFF 檔案所在的實際路徑。

#### Q：程式碼片段中應用了哪些優化來提高效能？

答：此程式碼片段使用了多種技術來增強轉換效能，例如設定邊距、配置影像解析度和比例以及設定`IsBlackWhite`屬性為真。這些優化有助於簡化轉換過程。

#### Q：我可以自訂生成的 PDF 中的圖像屬性嗎？

答：是的，您可以在生成的 PDF 中自訂影像屬性，例如比例、解析度和邊距，以實現所需的佈局和外觀。