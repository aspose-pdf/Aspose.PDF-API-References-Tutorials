---
title: 在 PDF 檔案中新增 PDF 頁碼
linktitle: 在 PDF 檔案中新增 PDF 頁碼
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 檔案中輕鬆新增 PDF 頁碼。
type: docs
weight: 40
url: /zh-hant/net/programming-with-stamps-and-watermarks/add-pdf-page-stamp/
---
在本教學中，我們將逐步指導您如何使用 Aspose.PDF for .NET 在 PDF 檔案中新增 PDF 頁碼。我們將向您展示如何使用提供的 C# 原始程式碼將自訂圖章新增至 PDF 檔案的特定頁面。

## 第一步：建構環境

在開始之前，請確保您具備以下條件：

- 已安裝的 .NET 開發環境。
- 下載 .NET 的 Aspose.PDF 庫並在您的專案中引用。

## 第 2 步：載入 PDF 文檔

第一步是將現有的 PDF 文件載入到您的專案中。方法如下：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//開啟文件
Document pdfDocument = new Document(dataDir + "PDFPageStamp.pdf");
```

請務必將「您的文件目錄」替換為 PDF 文件所在目錄的實際路徑。

## 第三步：建立頁面緩衝區

現在您已經上傳了 PDF 文檔，您可以建立要新增的頁戳。操作方法如下：

```csharp
//建立頁面緩衝區
PdfPageStamp pageStamp = new PdfPageStamp(pdfDocument.Pages[1]);
```

上面的程式碼使用 PDF 文件的第一頁建立一個新的頁面緩衝區。

## 步驟 4：設定頁面緩衝區屬性

在將頁面圖章新增至 PDF 文件之前，您可以設定圖章的各種屬性，例如背景、位置、旋轉等。

```csharp
//配置頁面緩衝區屬性
pageStamp. Background = true;
pageStamp. XIndent = 100;
pageStamp. YIndent = 100;
pageStamp.Rotate = Rotate.on180;
```

您可以根據需要調整這些屬性。

## 第 5 步：將頁碼新增至 PDF

現在頁面圖章已準備就緒，您可以將其新增至 PDF 文件的特定頁面。方法如下：

```csharp
//將頁面緩衝區新增至特定頁面
pdfDocument.Pages[1].AddStamp(pageStamp);
```

上面的程式碼將頁碼新增到 PDF 文件的第一頁。如果需要，您可以指定另一個頁面。

## 步驟 6：儲存輸出文檔

新增頁戳後，您可以儲存修改後的 PDF 文件。方法如下：

```csharp
//儲存輸出文檔
pdfDocument.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 新增 PDFPage Stamp 的範例原始碼 
```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//開啟文件
Document pdfDocument = new Document(dataDir+ "PDFPageStamp.pdf");

//建立頁戳
PdfPageStamp pageStamp = new PdfPageStamp(pdfDocument.Pages[1]);
pageStamp.Background = true;
pageStamp.XIndent = 100;
pageStamp.YIndent = 100;
pageStamp.Rotate = Rotation.on180;

//新增圖章到特定頁面
pdfDocument.Pages[1].AddStamp(pageStamp);
dataDir = dataDir + "PDFPageStamp_out.pdf";

//儲存輸出文檔
pdfDocument.Save(dataDir);
Console.WriteLine("\nPdf page stamp added successfully.\nFile saved at " + dataDir);

```

上述程式碼將編輯後的PDF文件儲存到指定目錄。

## 結論

恭喜！您已經了解如何使用 Aspose.PDF for .NET 新增 PDF 頁戳記。現在，您可以將這些知識應用到您自己的專案中，以將自訂圖章新增至 PDF 文件的特定頁面。

### 在 PDF 檔案中新增 PDF 頁戳記的常見問題解答

#### Q：使用 Aspose.PDF for .NET 新增 PDF 頁戳記的目的為何？

答：新增 PDF 頁面圖章可讓您在 PDF 文件的特定頁面上放置自訂圖章。此功能對於添加浮水印、徽標、簽名或任何其他視覺元素以增強文件的外觀並傳達附加資訊非常有用。

#### Q：我可以在同一 PDF 文件的不同頁面上新增多個頁面印記嗎？

答：是的，您可以將多個頁面印記新增至同一 PDF 文件的不同頁面。提供的 C# 原始程式碼可讓您指定新增頁戳的目標頁面，使其適用於文件中的不同頁面。

#### Q：如何調整 PDF 文件中頁籤的位置和旋轉？

 A：您可以透過修改頁籤的屬性來自訂頁籤的位置和旋轉。`PdfPageStamp`目的。本教程中提供的程式碼示範如何設定屬性，例如`XIndent`, `YIndent`， 和`Rotate`控製印章的定位和方向。

#### Q：頁面印記可以有透明或半透明的背景嗎？

答：是的，您可以設定`Background`的財產`PdfPageStamp`反對`true`為頁面標記啟用透明或半透明背景。這對於不應該完全遮蓋內容的水印或其他圖章很有用。

#### Q：我可以將此方法套用到現有 PDF 文件來新增頁碼嗎？

答：當然可以，您可以將此方法套用到現有的 PDF 文件來新增頁籤。本教學提供的程式碼示範如何載入現有 PDF 文件並向特定頁面新增頁戳。

#### Q：如何指定要新增頁籤的頁面？

答：您可以透過使用引用所需的頁面來指定新增頁戳的目標頁面。`pdfDocument.Pages[index]`句法。提供的 C# 原始程式碼顯示如何使用以下命令將頁碼新增至第一頁`pdfDocument.Pages[1]`，但您可以修改索引以定位不同的頁面。

#### Q：我可以使用此方法添加浮水印以外的印章，例如徽標或簽名嗎？

答：是的，您可以使用此方法添加各種類型的印章，包括浮水印、標誌、簽名或任何其他視覺元素。可以自訂教學課程的程式碼，以將所需的圖章新增至您的 PDF 文件中。

#### Q：在 PDF 文件中新增頁戳時有什麼注意事項或限制嗎？

答：雖然新增頁戳很簡單，但請考慮 PDF 文件的整體佈局和內容。確保新增的頁戳不會妨礙關鍵資訊或對文件的可讀性產生負面影響。

#### Q：我可以自動執行新增頁戳到多個 PDF 文件的過程嗎？

答：是的，您可以透過建立腳本或程式來自動執行向多個 PDF 文件新增頁戳記的過程，該腳本或程式會迭代文件清單並對每個文件套用相同的頁戳過程。
