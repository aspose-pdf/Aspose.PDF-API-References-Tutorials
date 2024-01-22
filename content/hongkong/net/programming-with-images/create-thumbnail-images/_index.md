---
title: 在 PDF 檔案中建立縮圖
linktitle: 在 PDF 檔案中建立縮圖
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 在 PDF 檔案中輕鬆建立縮圖。
type: docs
weight: 100
url: /zh-hant/net/programming-with-images/create-thumbnail-images/
---
本指南將逐步指導您如何使用 Aspose.PDF for .NET 在 PDF 文件中建立縮圖。確保您已設定環境並按照以下步驟操作：

## 步驟1：定義文檔目錄

開始之前，請確保為文件設定正確的目錄。代替`"YOUR DOCUMENT DIRECTORY"`在程式碼中包含包含 PDF 檔案的目錄路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步驟2：取得目錄中所有PDF檔案的名稱

在此步驟中，我們將使用 C# 檢索指定目錄中存在的所有 PDF 檔案的名稱`Directory`班級。文件將儲存在字串數組中。

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
```

## 步驟 3：瀏覽所有 PDF 文件及其頁面

在此步驟中，我們將遍歷所有 PDF 文件及其頁面來建立圖像縮圖。我們將使用一個`for`循環遍歷所有文件。

```csharp
for (int counter = 0; counter < fileEntries.Length; counter++)
{
     //開啟 PDF 文檔
     Document pdfDocument = new Document(fileEntries[counter]);
    
     //瀏覽文件的所有頁面
     for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
     {
         //建立一個流來保存縮圖
         using (FileStream imageStream = new FileStream(dataDir + "\\Thumbnails" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
         {
             //建立解析度對象
             Resolution resolution = new Resolution(300);
            
             //建立具有指定屬性的 JPEG 設備
             JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
            
             //轉換特定頁面並將圖像儲存到流中
             jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
            
             //關閉流
             imageStream.Close();
         }
     }
}
```

### 使用 Aspose.PDF for .NET 建立縮圖的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//檢索特定目錄中所有 PDF 檔案的名稱
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
//遍歷數組中的所有文件條目
for (int counter = 0; counter < fileEntries.Length; counter++)
{
	//開啟文件
	Document pdfDocument = new Document(fileEntries[counter]);
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "\\Thumbanils" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
		{
			//建立解析度對象
			Resolution resolution = new Resolution(300);
			//JpegDevice jpegDevice = new JpegDevice(500, 700, 解析度, 100);
			JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
			//轉換特定頁面並將圖像儲存到流中
			jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
			//關閉流
			imageStream.Close();
		}
	}
}
System.Console.WriteLine("PDF pages are converted to thumbnails successfully!");
```

## 結論

恭喜！您已使用 Aspose.PDF for .NET 從 PDF 檔案成功建立影像縮圖。圖像縮圖保存在指定目錄中。現在您可以使用這些縮圖來顯示 PDF 檔案的視覺預覽。

### 在 PDF 檔案中建立縮圖的常見問題解答

#### Q：使用 Aspose.PDF for .NET 從 PDF 檔案建立縮圖的目的是什麼？

答：從 PDF 檔案建立縮圖可讓您產生 PDF 中每個頁面的小型視覺預覽，這對於快速預覽和瀏覽內容非常有用。

#### Q：Aspose.PDF for .NET 如何促進從 PDF 檔案建立縮圖？

答：Aspose.PDF for .NET 提供了一個逐步過程來開啟 PDF 文件、遍歷其頁面、建立縮圖並使用以下命令將它們儲存到指定目錄：`JpegDevice`班級。

#### Q：為什麼在開始建立縮圖之前定義文件目錄很重要？

答：指定文件目錄可確保 PDF 檔案正確定位，並將產生的縮圖儲存在所需的輸出路徑中。

#### 問：如何`Document` class in Aspose.PDF for .NET help in the creation of thumbnail images?

答： 的`Document`類別允許您開啟和操作 PDF 文件。在本例中，它用於載入從中建立縮圖的 PDF 檔案。

####  Q： 有何作用`JpegDevice` class play in the creation of thumbnail images?

答： 的`JpegDevice`類別負責將 PDF 頁面轉換為 JPEG 影像，這些影像用作縮圖。它允許您指定寬度、高度、解析度和品質等屬性。

#### Q：如何將 PDF 文件的每一頁轉換為單獨的縮圖？

答：嵌套的`for`循環用於迭代每個 PDF 文件及其頁面。對於每個頁面，都會建立一個具有指定屬性的 JPEG 設備，並且`Process`方法用於將頁面轉換為縮圖並將其儲存到流中。

#### Q：我可以在創建過程中調整生成的縮圖的解析度或品質嗎？

 A：是的，您可以透過配置來修改解析度、寬度、高度、品質等屬性`JpegDevice`轉換每個頁面之前的物件。

#### Q：創建過程後如何在我的專案或應用程式中使用生成的縮圖？

答：產生的縮圖可用於提供 PDF 檔案的視覺預覽，幫助使用者快速辨識和瀏覽內容。

#### ：使用此創建過程從 PDF 文件生成的縮圖的數量有限制嗎？

答：產生的縮圖的數量取決於每個 PDF 文件的頁數。每個頁面將被轉換為單獨的縮圖。