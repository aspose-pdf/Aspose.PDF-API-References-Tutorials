---
title: 改變方向
linktitle: 改變方向
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 變更 PDF 頁面方向的逐步指南。易於在您的專案中遵循和實施。
type: docs
weight: 10
url: /zh-hant/net/programming-with-pdf-pages/change-orientation/
---
在本教學中，我們將引導您完成使用 Aspose.PDF for .NET 變更 PDF 文件頁面方向的逐步程序。我們將解釋捆綁的 C# 原始程式碼，並為您提供全面的指南，幫助您理解並在自己的專案中實現此功能。在本教學結束時，您將了解如何使用 Aspose.PDF for .NET 變更 PDF 文件的頁面方向。

## 先決條件
在開始之前，請確保您具備以下條件：

- C# 程式語言的基礎知識
- 在您的開發環境中安裝 Aspose.PDF for .NET

## 步驟1：定義文檔目錄
首先，您需要設定文檔目錄的路徑。這是輸入 PDF 檔案所在的位置，也是您要儲存修改後的輸出 PDF 檔案的位置。將“您的文件目錄”替換為適當的路徑。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：載入 PDF 文檔
然後您可以使用以下命令從輸入文件載入 PDF 文檔`Document`Aspose.PDF 類別。請務必指定 PDF 檔案的正確路徑。

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 步驟 3：更改頁面方向
現在我們將瀏覽文件的每一頁並更改其方向。對於每個頁面，我們修改媒體框的尺寸（`MediaBox`）透過交換寬度和高度，然後我們調整媒體框的座標以保持頁面的位置。最後，我們將頁面旋轉設定為90度。

```csharp
foreach(Page page in doc.Pages)
{
Aspose.Pdf.Rectangle r = page.MediaBox;
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page. Rotate = Rotate. on90;
}
```

## 第四步：儲存修改後的PDF文檔
最後，您可以使用以下命令將修改後的 PDF 文件儲存到輸出檔案：`Save()`的方法`Document`班級。請務必指定正確的路徑和檔案名稱。

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 變更方向的範例原始碼 

```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
foreach (Page page in doc.Pages)
{
	Aspose.Pdf.Rectangle r = page.MediaBox;
	double newHeight = r.Width;
	double newWidth = r.Height;
	double newLLX = r.LLX;
	//我們必須將頁面上移以補償頁面大小的變化
	//（頁面的下緣是 0,0，訊息通常從
	//頁面頂部。這就是為什麼我們將情人邊緣移至上方
	//新舊高度。
	double newLLY = r.LLY + (r.Height - newHeight);
	page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	//有時我們還需要設定CropBox（如果它在原始檔案中設定過）
	page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	//設定頁面旋轉角度
	page.Rotate = Rotation.on90;
}
dataDir = dataDir + "ChangeOrientation_out.pdf";
//儲存輸出檔案
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);

```

## 結論
在本教學中，我們學習如何使用 Aspose.PDF for .NET 變更 PDF 文件的頁面方向。透過執行上述步驟，您可以在自己的專案中輕鬆實現此功能。請隨意進一步探索 Aspose.PDF 文檔，以發現處理 PDF 文件的其他有用功能。

### 常見問題解答

#### Q：更改 PDF 文件頁面方向的目的是什麼？

答：更改 PDF 文件中的頁面方向可讓您將頁面內容旋轉 90 度。這在需要以不同方向顯示或列印原始內容的情況下非常有用，例如從縱向模式切換到橫向模式，反之亦然。

#### Q：我可以更改 PDF 文件中特定頁面的方向嗎？

答：是的，您可以變更 PDF 文件中特定頁面的方向。在提供的 C# 原始碼中，`foreach`循環用於遍歷文件的每一頁並更改其方向。如果您只想變更特定頁面的方向，則可以修改循環以根據頁碼或其他條件定位這些頁面。

#### Q：更改頁面方向是否會影響頁面內容的佈局？

答：是的，更改頁面方向會影響頁面內容的佈局。內容將旋轉 90 度，頁面的寬度和高度將交換。因此，頁面上內容的位置和對齊方式可能會改變。

#### Q：我可以將頁面旋轉 90 度以外的角度嗎？

答：在提供的 C# 原始程式碼中，頁面旋轉設定為 90 度，使用`page.Rotate = Rotate.on90;`。但是，如果需要，您可以將旋轉角度變更為其他值。例如，您可以使用`Rotate.on180`將頁面旋轉 180 度或`Rotate.on270`將其旋轉 270 度。

#### Q：改變方向後頁面內容溢出如何處理？

答：變更頁面方向時，頁面尺寸可能會發生變化，導致內容溢位。要解決此問題，您可能需要調整頁面內容的佈局和格式。您可以使用 Aspose.PDF for .NET 提供的功能，例如調整元素大小、調整邊距或重新組織內容，以確保頁面內容在方向變更後正確適合。