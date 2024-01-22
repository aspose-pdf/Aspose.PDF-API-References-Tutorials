---
title: PDF 轉 PNG 字體提示
linktitle: PDF 轉 PNG 字體提示
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 將 PDF 轉換為帶有字體提示的 PNG 的逐步指南。
type: docs
weight: 160
url: /zh-hant/net/document-conversion/pdf-to-png-font-hinting/
---
在本教學中，我們將引導您完成使用 Aspose.PDF for .NET 將 PDF 轉換為 PNG 映像的過程，同時啟用字體提示。字體提示是一種提高小字體可讀性的技術。透過執行以下步驟，您將能夠將 PDF 的每一頁轉換為帶有字體提示的 PNG 圖片。

## 先決條件
在開始之前，請確保滿足以下先決條件：

- C# 程式語言的基礎知識。
- 您的系統上安裝了適用於 .NET 的 Aspose.PDF 庫。
- 開發環境，例如 Visual Studio。

## 第 1 步：開啟來源 PDF 文檔
在此步驟中，我們將使用 Aspose.PDF for .NET 開啟來源 PDF 檔案。請按照以下程式碼操作：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//開啟文件
Document pdfDocument = new Document(dataDir + "input.pdf");
```

一定要更換`"YOUR DOCUMENTS DIRECTORY"`與您的 PDF 檔案所在的實際目錄。

## 第 2 步：啟用字體提示
打開 PDF 檔案後，我們將使用渲染選項啟用字體提示。使用以下程式碼：

```csharp
//建立渲染選項以啟用字體提示
RenderingOptions opts = new RenderingOptions();
opts. UseFontHinting = true;
```

## 第 3 步：轉換為 PNG 影像
現在我們要將 PDF 的每一頁轉換為帶有字體提示的 PNG 圖像。使用以下程式碼：

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
     {
         //建立具有指定屬性的 PNGDevice 對象
         //寬度、高度、解析度、質量
         //質量[0-100]，100為最大
         //建立解析度對象
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         //設定預定義的渲染選項
         pngDevice.RenderingOptions = opts;

         //轉換特定頁面並將圖像儲存到流中
         pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);

         //關閉流
         imageStream.Close();
     }
}
```

上面的程式碼將 PDF 的每個頁面轉換為帶有字體提示的 PNG 圖像，並將每個圖像儲存為單獨的 PNG 檔案。

### 使用 Aspose.PDF for .NET 進行 PDF 到 PNGFont 提示的範例原始碼

```csharp
try
{
	
	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//開啟文件
	Document pdfDocument = new Document(dataDir + "input.pdf");
	//建立 Aspose.Pdf.RenderingOptions 以啟用字體提示
	RenderingOptions opts = new RenderingOptions();
	opts.UseFontHinting = true;
	
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
		{
			//建立具有指定屬性的PNG設備
			//寬度、高度、解析度、質量
			//質量 [0-100]，100 為最大
			//建立解析度對象
			Resolution resolution = new Resolution(300);
			PngDevice pngDevice = new PngDevice(resolution);
			//設定預定義的渲染選項
			pngDevice.RenderingOptions = opts;

			//轉換特定頁面並將圖像儲存到流中
			pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);

			//關閉流
			imageStream.Close();
		}
	}
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 結論
在本教程中，我們介紹了使用 Aspose.PDF for .NET 將 PDF 轉換為帶有字體提示的 PNG 圖像的逐步過程。按照上述說明，您現在應該能夠將 PDF 的每一頁轉換為帶有字體提示的 PNG 圖像。當您希望在轉換為 PNG 映像時保持小字體的可讀性時，此功能非常有用。

### 常見問題解答

#### Q：什麼是字體提示？為什麼它在將 PDF 轉換為 PNG 時很重要？

答：字體提示是一種透過調整小字體的形狀和位置來提高小字體可讀性的技術。將 PDF 轉換為 PNG 圖像時，啟用字體提示可確保生成的 PNG 圖片中的文字保持清晰易讀，尤其是對於小字體。這對於將 PDF 文件轉換為圖像時保持文字的品質和可讀性非常重要。

#### Q：字體提示如何影響 PNG 轉換過程？

答：在 PDF 到 PNG 轉換過程中，字體提示會影響生成的 PNG 圖片中文字的呈現方式。透過啟用字體提示，Aspose.PDF 庫可以調整字體渲染，以確保小字體保持其清晰度和可讀性，從而使 PNG 圖像更具視覺吸引力和可讀性。

#### Q：我可以調整字體提示設定來自訂 PNG 轉換嗎？

答：是的，Aspose.PDF for .NET 函式庫提供了自訂 PNG 轉換過程的選項，包括字體提示設定。在提供的程式碼範例中，`UseFontHinting`的財產`RenderingOptions`對象設定為`true`啟用字體提示。您可以透過調整其他屬性來進一步微調轉換過程`RenderingOptions`根據您的要求上課。

#### Q：PNG轉換過程中如何保存PNG影像？

答：在提供的程式碼範例中，PDF 文件的每一頁都會轉換為單獨的 PNG 映像。 PNG 圖像保存為單獨的文件，檔案名稱遵循「圖像{pageCount}_出.png”，其中`{pageCount}`是正在轉換的頁數。每個 PNG 影像代表原始 PDF 文件的一頁。