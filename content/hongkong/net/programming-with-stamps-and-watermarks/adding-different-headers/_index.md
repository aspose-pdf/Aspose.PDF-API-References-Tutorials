---
title: 在 PDF 檔案中新增不同的標題
linktitle: 在 PDF 檔案中新增不同的標題
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 輕鬆為 PDF 檔案的每個頁面新增不同的頁首。
type: docs
weight: 30
url: /zh-hant/net/programming-with-stamps-and-watermarks/adding-different-headers/
---
在本教學中，我們將逐步指導您如何使用 Aspose.PDF for .NET 在 PDF 檔案中新增不同的標題。我們將向您展示如何使用提供的 C# 原始程式碼將自訂頁眉新增至 PDF 檔案的每個頁面。

## 第一步：建構環境

在開始之前，請確保您具備以下條件：

- 已安裝的 .NET 開發環境。
- 下載 .NET 的 Aspose.PDF 庫並在您的專案中引用。

## 第 2 步：載入 PDF 文檔

第一步是將現有的 PDF 文件載入到您的專案中。就是這樣：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//開啟來源文檔
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "AddingDifferentHeaders.pdf");
```

請務必將「您的文件目錄」替換為 PDF 文件所在目錄的實際路徑。

## 第 3 步：建立標頭緩衝區

現在您已經上傳了 PDF 文檔，您可以建立要新增的頁首圖章。就是這樣：

```csharp
//建立三個標頭緩衝區
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");
```

上面的程式碼建立了三個包含指定文字的新標頭緩衝區。

## 步驟 4：配置標頭緩衝區屬性

在將頁首圖章新增至 PDF 文件之前，您可以為每個圖章配置不同的屬性，例如對齊方式、大小、顏色等。操作方法如下：

```csharp
//配置第一個標頭緩衝區
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp1.TextState.FontStyle = FontStyles.Bold;
stamp1.TextState.ForegroundColor = Color.Red;
stamp1.TextState.FontSize = 14;

//第二個標頭緩衝區的配置
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp2.Zoom = 10;

//配置第三個標頭緩衝區
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp3.RotateAngle = 35;
stamp3.TextState.BackgroundColor = Color.Pink;
stamp3.TextState.Font = FontRepository.FindFont("Verdana");
```

您可以根據需要調整每個標頭緩衝區的這些屬性。

## 第 5 步：為 PDF 新增頁眉圖章

現在頁首標記已準備就緒，您可以將它們新增至 PDF 文件的每個特定頁面。就是這樣：

```csharp
//將標頭緩衝區新增至特定頁面
doc.Pages[1].AddStamp(stamp1);
doc.Pages[2].AddStamp(stamp2);
doc.Pages[3].AddStamp(stamp3);
```

上面的程式碼將每個頁首標記新增到 PDF 文件的對應頁面。

## 步驟 6：儲存輸出文檔

新增頁首印記後，您可以儲存編輯後的 PDF 文件。就是這樣：

```csharp
//儲存更新後的文檔
doc.Save(dataDir);
```

上述程式碼將編輯後的PDF文件儲存到指定目錄。

### 使用 Aspose.PDF for .NET 新增不同標頭的範例原始碼 
```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//開源文檔
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddingDifferentHeaders.pdf");

//創建三個印章
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");

//設定圖章對齊（將圖章放置在頁面頂部，水平置中）
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

//將字型樣式指定為粗體
stamp1.TextState.FontStyle = FontStyles.Bold;

//將文字前景色資訊設定為紅色
stamp1.TextState.ForegroundColor = Color.Red;

//指定字體大小為14
stamp1.TextState.FontSize = 14;

//現在我們需要將第二個圖章物件的垂直對齊設定為頂部
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

//將圖章的水平對齊資訊設定為中心對齊
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

//設定圖章物件的縮放係數
stamp2.Zoom = 10;

//設定第三個圖章物件的格式
//將圖章物件的垂直對齊資訊指定為 TOP
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

//將圖章物件的水平對齊資訊設定為中心對齊
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

//設定圖章物件的旋轉角度
stamp3.RotateAngle = 35;

//將粉紅色設定為郵票的背景顏色
stamp3.TextState.BackgroundColor = Color.Pink;

//將印章的字體資訊更改為 Verdana
stamp3.TextState.Font = FontRepository.FindFont("Verdana");

//第一頁加上第一枚印章；
doc.Pages[1].AddStamp(stamp1);

//第二頁加上第二枚印章；
doc.Pages[2].AddStamp(stamp2);

//第三張郵票加在第三頁。
doc.Pages[3].AddStamp(stamp3);
dataDir = dataDir + "multiheader_out.pdf";

//儲存更新後的文檔
doc.Save(dataDir);
Console.WriteLine("\nDifferent headers added successfully.\nFile saved at " + dataDir);

```

## 結論

恭喜！您已經了解如何使用 Aspose.PDF for .NET 為 PDF 文件的每個頁面新增不同的頁首。現在您可以將這些知識應用到您自己的專案中，為您的 PDF 文件自訂標題。

### 在 PDF 檔案中新增不同標題的常見問題解答

#### Q：使用 Aspose.PDF for .NET 在 PDF 檔案中新增不同標題的目的是什麼？

答：使用 Aspose.PDF for .NET 將不同的標題新增至 PDF 檔案中，您可以自訂每個頁面頂部顯示的內容。此功能對於新增標題、章節名稱、頁碼和其他在 PDF 文件的不同頁面上有所不同的資訊特別有用。

#### Q：我可以自訂每個標題的外觀，例如對齊方式、字體、大小、顏色和旋轉嗎？

答：是的，您可以完全自訂每個標題圖章的外觀。提供的C#原始碼示範如何設定各種屬性`TextStamp`每個標題的對象，包括垂直和水平對齊、字體樣式、字體大小、字體顏色、背景顏色和旋轉角度。

#### Q：是否可以在 PDF 文件的同一頁上新增多個頁首印記？

答：雖然提供的教學示範了將不同的頁首新增至 PDF 文件的不同頁面，但您可以調整程式碼以將多個頁首圖章新增至同一頁。如果您想在同一部分中顯示不同的標題，這可能很有用。

#### Q：如何確保頁首不會與 PDF 頁面的主要內容重疊？

答：為了防止重疊，您可以調整`VerticalAlignment`, `HorizontalAlignment`，以及其他屬性`TextStamp`對象。這些設定將控制標題在頁面上的位置，讓您以不妨礙主要內容的方式放置它們。

#### Q：我可以使用此方法為現有的不同頁數的 PDF 文件添加頁首嗎？

答：是的，您可以調整提供的原始程式碼，將頁首新增至具有不同頁數的現有 PDF 文件中。只需調整程式碼以符合您要新增的標題數量，並將每個標題與所需的頁面相關聯。

#### Q：如果我想在特定頁面上新增標題，而不僅僅是前三頁，該怎麼辦？

答：出於說明目的，本教學示範了向前三頁新增標題。若要在三個頁面之外的特定頁面向前新增標題，請透過引用相應的頁面索引並建立`TextStamp`每個頁面的物件。

#### Q：我可以使用圖像代替文字作為標題嗎？

答：提供的教程重點介紹添加基於文字的標題。但是，您可以應用類似的方法來新增基於圖像的標題`ImageStamp`對象而不是`TextStamp`對象。這將涉及創建和配置`ImageStamp`具有所需屬性的物件。

#### Q：如何應用這些知識為 PDF 文件的每個頁面添加不同的頁尾？

答：本教學中示範的相同方法可用於在 PDF 文件的每個頁面中新增不同的頁尾。您可以建立和配置而不是標頭`TextStamp`或者`ImageStamp`物件並使用以下命令將它們添加到每個頁面的底部`AddStamp`方法。

#### Q：我可以自動執行批次操作中新增頁首至多個 PDF 文件的過程嗎？

答：是的，您可以使用腳本或程式自動執行向多個 PDF 文件新增頁首的過程，該腳本或程式迭代文件清單並將頁首標記過程套用到每個文件。