---
title: 在 PDF 檔案中新增文字印記
linktitle: 在 PDF 檔案中新增文字印記
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 檔案中輕鬆新增文字印章。
type: docs
weight: 50
url: /zh-hant/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
在本教學中，我們將逐步指導您如何使用 Aspose.PDF for .NET 在 PDF 檔案中新增文字圖章。我們將向您展示如何使用提供的 C# 原始程式碼將自訂文字圖章新增至 PDF 檔案的特定頁面。

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
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

請務必將「您的文件目錄」替換為 PDF 文件所在目錄的實際路徑。

## 第 3 步：建立文字緩衝區

現在您已經上傳了 PDF 文檔，您可以建立要新增的文字印章。操作方法如下：

```csharp
//建立文字緩衝區
TextStamp textStamp = new TextStamp("Example Stamp");
```

上面的程式碼建立一個包含指定文字的新文字緩衝區。

## 步驟 4：配置文字圖章屬性

在將文字圖章新增至 PDF 文件之前，您可以設定圖章的各種屬性，例如背景、位置、旋轉、字型、大小等。

```csharp
//配置文字緩衝區屬性
textStamp. Background = true;
textStamp. XIndent = 100;
textStamp. YIndent = 100;
textStamp.Rotate = Rotate.on90;
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);
```

您可以根據需要調整這些屬性。

## 第 5 步：將文字圖章新增至 PDF

現在文字圖章已準備就緒，您可以將其新增至 PDF 文件的特定頁面。方法如下：

```csharp
//將文字緩衝區新增至特定頁面
pdfDocument.Pages[1].AddStamp(textStamp);
```

上面的程式碼將文字圖章新增到 PDF 文件的第一頁。如果需要，您可以指定另一個頁面。

## 步驟 6：儲存輸出文檔

新增文字圖章後，您可以儲存編輯後的 PDF 文件。方法如下：

```csharp
//儲存輸出文檔
pdfDocument.Save(dataDir);
```

上面的程式碼將修改後的PDF文件儲存在指定目錄中。

### 使用 Aspose.PDF for .NET 新增文字圖章的範例原始程式碼 
```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//開啟文件
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");

//建立文字印章
TextStamp textStamp = new TextStamp("Sample Stamp");

//設定圖章是否為背景
textStamp.Background = true;

//設定原點
textStamp.XIndent = 100;
textStamp.YIndent = 100;

//旋轉圖章
textStamp.Rotate = Rotation.on90;

//設定文字屬性
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold;
textStamp.TextState.FontStyle = FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);

//新增圖章到特定頁面
pdfDocument.Pages[1].AddStamp(textStamp);
dataDir = dataDir + "AddTextStamp_out.pdf";

//儲存輸出文檔
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);            

```

## 結論

恭喜！您已經了解如何使用 Aspose.PDF for .NET 新增文字印章。現在您可以將這些知識應用到您自己的專案中，以將自訂文字圖章新增至 PDF 文件中。

### 在 PDF 文件中添加文字印記的常見問題解答

#### Q：使用 Aspose.PDF for .NET 在 PDF 檔案中新增文字印章的目的是什麼？

答：新增文字圖章可讓您將自訂文字放置在 PDF 文件的特定頁面上。此功能對於新增標籤、註釋、浮水印或任何其他文字資訊以增強文件內容並提供附加上下文非常有用。

#### Q：我可以自訂文字印章的外觀，例如字體、大小、顏色和旋轉嗎？

答：是的，您可以完全自訂文字印章的外觀。提供的C#原始碼示範如何設定各種屬性`TextStamp`對象，包括字體、字體大小、字體樣式、文字顏色、背景顏色和旋轉。

#### Q：是否可以在同一 PDF 文件的不同頁面上新增多個文字印記？

答：當然，您可以將多個文字圖章新增至同一 PDF 文件的不同頁面。本教學提供的程式碼可讓您指定新增文字圖章的目標頁面，使其適用於文件中的不同頁面。

#### Q：如何指定 PDF 文件中文字印記的位置？

 A：您可以透過修改`XIndent`和`YIndent`的屬性`TextStamp`目的。這些屬性定義圖章左上角相對於頁面原點的座標。

#### Q：我可以將此方法套用到現有 PDF 文件來新增文字圖章嗎？

答：是的，您可以將此方法套用到現有的 PDF 文件來新增文字圖章。本教學提供的程式碼示範如何載入現有 PDF 文件並將文字圖章新增至特定頁面。

#### Q：我可以為文字圖章添加背景色和前景色嗎？

答：是的，您可以為文字印章添加背景色和前景色。透過設定`Background`財產給`true`，您可以為文字圖章提供彩色背景。此外，您還可以設定`TextState.ForegroundColor`屬性來指定文字本身的顏色。

#### Q：如何確保文字印記不會遮蓋 PDF 文件的底層內容？

答：在新增文字印記時，請注意其位置，以確保它不會遮蔽關鍵資訊或對文件的可讀性產生負面影響。您可以調整`XIndent`和`YIndent`屬性來適當定位文本圖章。

#### Q：我可以使用此方法添加文字以外的圖章，例如圖像或標誌嗎？

答：本教學重點在於新增文字印章，但您也可以使用 Aspose.PDF for .NET 以類似方式新增其他類型的印章，例如圖像或標誌。該過程涉及創建適當的圖章物件並配置其屬性。

#### Q：如何自動執行在多個 PDF 文件中新增文字圖章的過程？

答：您可以透過建立腳本或程式來自動執行向多個 PDF 文件新增文字印記的過程，該腳本或程式會迭代文件清單並對每個文件套用相同的文字印記過程。