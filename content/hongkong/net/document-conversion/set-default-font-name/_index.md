---
title: 設定預設字體名稱
linktitle: 設定預設字體名稱
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 在 PDF 檔案中設定預設字體名稱的逐步指南。
type: docs
weight: 270
url: /zh-hant/net/document-conversion/set-default-font-name/
---
在本教學中，我們將向您展示如何使用 Aspose.PDF for .NET 在 PDF 檔案中設定預設字體名稱。有時，當您從 PDF 文件中提取圖像時，可能會遇到缺少字體的問題。透過指定預設字體名稱，您可以確保提取的文字能夠正確顯示。請依照以下步驟設定 PDF 檔案中的預設字體名稱。

## 先決條件
在開始之前，請確保滿足以下先決條件：

- C# 程式語言的基礎知識。
- 您的系統上安裝了適用於 .NET 的 Aspose.PDF 庫。
- 開發環境，例如 Visual Studio。

## 第 1 步：載入 PDF 文檔
第一步是將 PDF 文件載入到`Document`目的。使用以下程式碼：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     //要新增的程式碼
}
```

一定要更換`"YOUR DOCUMENTS DIRECTORY"`與您的 PDF 檔案所在的實際目錄。

## 第2步：設定預設字體名稱
接下來，我們將使用以下命令設定預設字體名稱`DefaultFontName`的選項`RenderingOptions`目的。使用以下程式碼：

```csharp
using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
     {
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         RenderingOptions ro = new RenderingOptions();
         ro.DefaultFontName = "Arial";
         pngDevice.RenderingOptions = ro;
        
         //要新增的程式碼
     }
}
```

一定要更換`"Arial"`與所需的字體名稱。

## 第三步：影像擷取
接下來，我們將從PDF文件的指定頁面中提取影像。使用以下程式碼：

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```

請務必在中指定正確的頁碼`pdfDocument.Pages[1]`.

### 使用 Aspose.PDF for .NET 設定預設字體名稱的範例原始碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
	using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
	{
		Resolution resolution = new Resolution(300);
		PngDevice pngDevice = new PngDevice(resolution);
		RenderingOptions ro = new RenderingOptions();
		ro.DefaultFontName = "Arial";
		pngDevice.RenderingOptions = ro;
		pngDevice.Process(pdfDocument.Pages[1], imageStream);
	}
}
```

## 結論
在本教學中，我們學習如何使用 Aspose.PDF for .NET 在 PDF 檔案中設定預設字體名稱。透過指定預設字體名稱，您可以確保提取的文字能夠正確顯示。使用此方法可以解決從 PDF 文件中提取圖像時丟失字體的問題。

### 常見問題解答

#### Q：什麼是 Aspose.PDF for .NET？

答：Aspose.PDF for .NET 是一個功能強大的程式庫，可讓開發人員在 C# 應用程式中處理 PDF 文件。它提供各種功能，包括設定 PDF 文件中的預設字體名稱。

#### Q：為什麼需要在 PDF 檔案中設定預設字體名稱？

答：從 PDF 文件中提取文字時，設定預設字體名稱非常有用。如果 PDF 包含提取機上不可用的字體的文本，則指定預設字體名稱可確保正確的文本顯示。

#### Q：如何使用 Aspose.PDF for .NET 載入 PDF 文件並設定預設字型名稱？

 A：要載入PDF文件並設定預設字體名稱，您可以使用`Document`類別來載入 PDF 文件和`RenderingOptions.DefaultFontName`屬性來指定所需的預設字體名稱。

#### Q：我可以選擇任何字體作為預設字體名稱嗎？

答：是的，您可以選擇提取機上可用的任何字體作為預設字體名稱。使用與原始 PDF 中缺失字體緊密匹配的字體，以確保準確的文字呈現。

#### Q：設定預設字體名稱是否會永久更改 PDF 檔案？

答：不，使用 Aspose.PDF for .NET 設定預設字型名稱是在文字擷取過程中進行的臨時變更。它不會修改原始 PDF 檔案。