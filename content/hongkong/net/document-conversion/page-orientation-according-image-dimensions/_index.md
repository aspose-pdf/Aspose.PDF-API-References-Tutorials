---
title: 根據影像尺寸決定頁面方向
linktitle: 根據影像尺寸決定頁面方向
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 根據影像尺寸設定頁面方向的逐步指南。
type: docs
weight: 80
url: /zh-hant/net/document-conversion/page-orientation-according-image-dimensions/
---
在本教學中，我們將引導您完成使用 Aspose.PDF for .NET 根據影像尺寸設定頁面方向的過程。我們將循環遍歷給定目錄中的 JPG 圖像列表，並根據每個圖像的寬度自動調整頁面方向。請按照以下步驟來實現此目的。

## 先決條件
在開始之前，請確保滿足以下先決條件：

- C# 程式語言的基礎知識。
- 您的系統上安裝了適用於 .NET 的 Aspose.PDF 庫。
- 開發環境，例如 Visual Studio。

## 第 1 步：瀏覽 JPG 圖像
在此步驟中，我們將瀏覽給定目錄中的所有 JPG 圖像。請按照以下程式碼操作：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//建立新的 PDF 文檔
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

//檢索特定目錄中所有 JPG 檔案的名稱
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");
```

一定要更換`"YOUR DOCUMENTS DIRECTORY"`與 JPG 影像所在的實際目錄。

## 第2步：建立頁面和圖像
瀏覽 JPG 檔案後，我們將為每個檔案建立一個頁面和一個圖像。使用以下程式碼：

```csharp
int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
//建立頁面對象
Aspose.Pdf.Page page = doc.Pages.Add();

//建立影像對象
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = fileEntries[counter];
```

## 第 3 步：檢查影像尺寸
現在讓我們檢查每個圖像的尺寸以確定頁面方向。使用以下程式碼：

```csharp
//建立 BitMap 物件以從影像檔案中獲取訊息
Bitmap myimage = new Bitmap(fileEntries[counter]);

//檢查圖像的寬度是否大於頁面的寬度
if (myimage.Width > page.PageInfo.Width)
//

  If the width of the image is greater than the width of the page, set the page orientation to landscape
page.PageInfo.IsLandscape = true;
else
//如果圖像的寬度小於頁面的寬度，請將頁面方向設定為縱向
page.PageInfo.IsLandscape = false;
```

## 步驟 4：將影像新增至 PDF 文檔
檢查影像的尺寸後，我們將把影像加入 PDF 文件的段落集合中。使用以下程式碼：

```csharp
//將影像加入PDF文件的段落集合中
page.Paragraphs.Add(image1);
```

## 步驟 5：儲存 PDF 文件
將所有圖像新增至 PDF 文件後，我們現在可以儲存生成的 PDF 文件。這是最後一步：

```csharp
//儲存 PDF 文件
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

代替`"YOUR DOCUMENTS DIRECTORY"`以及要儲存輸出 PDF 檔案的所需目錄。

### 使用 Aspose.PDF for .NET 根據圖像尺寸確定頁面方向的範例原始程式碼

```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

//檢索特定目錄中所有 JPG 檔案的名稱
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");

int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
	//建立頁面對象
	Aspose.Pdf.Page page = doc.Pages.Add();

	//建立影像對象
	Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
	image1.File = fileEntries[counter];

	//建立一個BitMap物件以取得影像檔案的信息
	Bitmap myimage = new Bitmap(fileEntries[counter]);
	//檢查圖像檔案的寬度是否大於頁面寬度
	if (myimage.Width > page.PageInfo.Width)
		//如果影像寬度大於頁面寬度，則將頁面方向設為橫向
		page.PageInfo.IsLandscape = true;
	else
		//如果圖像寬度小於頁面寬度，則將頁面方向設定為縱向
		page.PageInfo.IsLandscape = false;
	//將影像新增至 PDF 文件的段落集合中
	page.Paragraphs.Add(image1);
}
//儲存 PDF 文件
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

## 結論
在本教學中，我們介紹了使用 Aspose.PDF for .NET 根據圖像尺寸設定頁面方向的逐步過程。按照上述說明，您現在應該能夠建立每個影像具有正確頁面方向的 PDF 文件。當您有不同尺寸的圖像並希望將它們嵌入 PDF 文件中時，此功能非常有用。

### 常見問題解答

#### Q：我可以使用其他圖像格式代替 JPG 來根據圖像尺寸設定頁面方向嗎？

答：是的，除了 JPG 之外，您還可以使用其他圖像格式（例如 PNG、BMP 或 GIF）來根據圖像尺寸設定頁面方向。提供的程式碼循環遍歷所有擴展名為“.JPG”的圖像文件，但您也可以修改它以包含其他圖像格式。

#### Q：如果圖像的尺寸剛好等於頁面寬度會發生什麼事？

答：如果影像的寬度恰好等於頁面寬度，則頁面方向將設定為縱向。在提供的程式碼中，僅當影像的寬度大於頁面寬度時，頁面方向才會設定為橫向。

#### Q：我可以根據具體需求自訂頁面方向邏輯嗎？

A：是的，您可以根據特定需求自訂頁面方向邏輯。例如，您可以設定閾值來確定何時應將頁面方向設定為橫向或縱向。此外，您可以考慮影像高度或寬高比等因素來決定頁面方向。

#### Q：我可以將其他內容（例如文字或表格）與圖像一起添加到 PDF 文件中嗎？

答：是的，您可以將其他內容（例如文字或表格）與圖像一起添加到 PDF 文件中。 Aspose.PDF for .NET 提供了一組豐富的功能來操作 PDF 文檔，包括在頁面上新增文字、圖像、表格和其他元素。