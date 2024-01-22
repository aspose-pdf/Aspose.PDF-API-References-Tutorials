---
title: XPS 轉 PDF
linktitle: XPS 轉 PDF
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 將 XPS 檔案轉換為 PDF 的逐步指南。
type: docs
weight: 350
url: /zh-hant/net/document-conversion/xps-to-pdf/
---
在本教學中，我們將逐步引導您了解如何使用 Aspose.PDF 庫 for .NET 將 XPS 檔案轉換為 PDF。我們將詳細介紹所提供的 C# 原始程式碼，並向您展示如何在您自己的專案中實現它。在本教學結束時，您將能夠輕鬆地將 XPS 檔案轉換為 PDF 文件。

## 步驟1：設定文檔目錄
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
代替`"YOUR DOCUMENTS DIRECTORY"`與您儲存文件的路徑。

## 步驟 2：使用 XPS 載入選項實例化 LoadOptions 對象
```csharp
Aspose.Pdf.LoadOptions options = new XpsLoadOptions();
```
使用 XPS 載入選項建立 LoadOptions 物件的實例。

## 第 3 步：建立文檔對象
```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);
```
建立指定輸入 XPS 檔案和載入選項的 Document 物件。

## 步驟 4：儲存產生的 PDF 文檔
```csharp
document.Save(dataDir + "XPSToPDF_out.pdf");
```
將產生的 PDF 文件儲存到指定目錄。

### 使用 Aspose.PDF for .NET 將 XPS 轉換為 PDF 的範例原始碼

```csharp
try
{
	
	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	//使用 XPS 載入選項實例化 LoadOption 對象
	Aspose.Pdf.LoadOptions options = new XpsLoadOptions();

	//建立文檔對象
	Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);

	//儲存生成的 PDF 文檔
	document.Save(dataDir + "XPSToPDF_out.pdf");
	
}
catch(Exception ex)
   
{
	Console.WriteLine(ex.Message);
}
```

## 結論
在本教學中，我們學習如何使用 .NET 的 Aspose.PDF 庫將 XPS 檔案轉換為 PDF。透過按照提供的步驟操作，您可以在自己的應用程式中輕鬆執行此轉換。將 XPS 檔案轉換為 PDF 時獲得準確、專業的結果。

### 常見問題解答

#### Q：什麼是 XPS，為什麼我要將其轉換為 PDF？

答：XPS（XML 紙張規格）是 Microsoft 開發的一種固定版式文件格式。將 XPS 轉換為 PDF 可以使文件更易於存取和廣泛相容，因為 PDF 是跨不同平台和裝置的普遍支援的格式。

#### Q：Aspose.PDF 庫是否支援 XPS 以外的其他文件格式？

答：是的，Aspose.PDF for .NET 支援各種其他檔案格式的轉換，例如 HTML、EPUB、SVG、XML 等。它還允許您以程式設計方式建立和操作 PDF 文件。

#### Q：我可以自訂 PDF 轉換過程，例如設定頁面大小、邊距或其他選項嗎？

答：是的，您可以使用 Aspose.PDF for .NET 自訂 PDF 轉換過程。該庫提供了多種選項來控制頁面大小、邊距、圖像壓縮、字體嵌入和其他 PDF 相關設置，以滿足您的特定要求。

#### Q：是否有 Aspose.PDF for .NET 的試用版可供測試？

答：是的，您可以從 Aspose 官方網站下載並試用 Aspose.PDF for .NET 的試用版。試用版可讓您在購買之前探索該庫的功能。

#### Q：我可以批次將多個 XPS 檔案轉換為 PDF 嗎？

答：是的，您可以透過實作循環或迭代 XPS 檔案清單並使用提供的程式碼將每個檔案轉換為 PDF，以批次方式將多個 XPS 檔案轉換為 PDF。