---
title: 在 PDF 檔案中新增日期時間戳
linktitle: 在 PDF 檔案中新增日期時間戳
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 檔案中輕鬆新增日期和時間戳記。
type: docs
weight: 10
url: /zh-hant/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
在本文中，我們將逐步指導您如何使用 Aspose.PDF for .NET 在 PDF 文件中新增日期和時間戳記。我們將向您展示如何使用提供的 C# 原始程式碼向現有 PDF 文件新增日期和時間戳記。

## 要求

在開始之前，請確保您具備以下條件：

- 已安裝的 .NET 開發環境。
- 下載 .NET 的 Aspose.PDF 庫並在您的專案中引用。

## 第一步：建構環境

在新增日期和時間戳記之前，您需要設定開發環境。以下是要遵循的步驟：

1. 打開您最喜歡的 IDE（整合開發環境）。
2. 建立一個新的 C# 專案。
3. 請確定您已新增對 .NET 的 Aspose.PDF 庫的參考。

## 第2步：新增Aspose.PDF庫

需要使用適用於 .NET 的 Aspose.PDF 庫來處理專案中的 PDF 文件。

## 第 3 步：載入 PDF 文檔

新增日期和時間戳的第一步是將現有 PDF 文件載入到您的專案中。方法如下：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//開啟文件
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

請務必將「您的文件目錄」替換為 PDF 文件所在目錄的實際路徑。

## 步驟 4：建立日期和時間戳

現在您已經上傳了文檔

  PDF，您可以建立要新增的日期和時間戳記。操作方法如下：

```csharp
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt");

//建立文字緩衝區
TextStamp textStamp = new TextStamp(annotationText);
```

上面的程式碼建立一個包含當前日期和時間的新文字緩衝區。

## 步驟 5：配置圖章屬性

在將圖章新增至 PDF 文件之前，您可以設定圖章的各種屬性，例如邊距、水平和垂直對齊方式等。

```csharp
//設定緩衝區屬性
textStamp.BottomMargin = 10;
textStamp. RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

您可以根據需要調整這些屬性。

## 第 6 步：將圖章新增至 PDF

現在日期和時間戳記已準備就緒，您可以將其新增至 PDF 文件的特定頁面。方法如下：

```csharp
//將圖章加入到頁面的圖章集中
pdfDocument.Pages[1].AddStamp(textStamp);
```

上面的程式碼將圖章新增到 PDF 文件的第一頁。如果需要，您可以指定另一個頁面。

## 步驟7：儲存輸出文檔

新增日期和時間戳記後，您可以儲存修改後的 PDF 文件。方法如下：

```csharp
//儲存輸出文檔
pdfDocument.Save(dataDir);
```

上述程式碼將編輯後的PDF文件儲存到指定目錄。

### 使用 Aspose.PDF for .NET 新增日期時間戳記的範例原始碼 
```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//開啟文件
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");

//建立文字印章
TextStamp textStamp = new TextStamp(annotationText);

//設定圖章的屬性
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

//在集郵上新增郵票
pdfDocument.Pages[1].AddStamp(textStamp);
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;

Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddDateTimeStamp_out.pdf";

//儲存輸出文檔
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);  
          
```

## 結論

恭喜！您已經了解如何使用 Aspose.PDF for .NET 新增日期和時間戳記。現在您可以將這些知識應用到您自己的專案中，以在 PDF 文件中新增日期和時間戳記。

### 在 PDF 檔案中新增日期時間戳記的常見問題解答

#### Q：使用 Aspose.PDF for .NET 為 PDF 文件新增日期和時間戳記的目的是什麼？

答：在 PDF 文件中新增日期和時間戳記可以指示文件的修改或建立時間，從而增強其資訊價值。此功能對於追蹤文件變更並為文件歷史記錄提供參考點非常有用。

#### Q：我可以自訂日期和時間戳記的格式以滿足特定要求嗎？

答：是的，您可以根據您的喜好自訂日期和時間戳記的格式。提供的 C# 原始碼使用`DateTime.Now.ToString()`方法產生特定格式的時間戳記。您可以修改此程式碼以根據需要格式化時間戳。

#### Q：是否可以將日期和時間戳記新增至 PDF 頁面上的特定位置？

答：當然可以，您可以透過修改 PDF 頁面的屬性來調整日期和時間戳記在 PDF 頁面上的位置。`TextStamp`目的。本教學中提供的程式碼示範如何設定邊距、對齊方式和垂直定位等屬性。

#### Q：我可以在同一 PDF 文件的不同頁面上新增多個日期和時間戳記嗎？

答：是的，您可以將多個日期和時間戳記新增至相同 PDF 文件的不同頁面。只需重複建立的過程`TextStamp`物件並為每個所需頁面配置其屬性。

#### Q：如何更改日期和時間戳文字的字體、大小或顏色？

答：要修改日期和時間戳文字的字體、大小或顏色，您可以自訂日期和時間戳文字的屬性。`DefaultAppearance`用於建立的對象`TextStamp`。調整字體名稱、大小和顏色值以獲得所需的外觀。

#### Q：是否可以使用 Aspose.PDF for .NET 將其他類型的註解或圖章加入 PDF 文件中？

答：是的，Aspose.PDF for .NET 提供了多種註解類型，您可以將其新增至 PDF 文件中，包括文字註解、圖章、線條、形狀等。您可以瀏覽 Aspose.PDF 文件以取得有關使用註解的更多詳細資訊。

#### Q：在 PDF 文件中新增日期和時間戳記時有任何限製或註意事項嗎？

答：雖然新增日期和時間戳很簡單，但請考慮文件佈局和現有內容等因素。確保印章的位置不會掩蓋重要資訊或影響文件的可讀性。

#### Q：如何將此方法整合到我自己的專案中，為 PDF 文件添加日期和時間戳記？

答：要整合此方法，請按照提供的步驟操作並調整程式碼以適合您的專案結構。您可以為現有 PDF 文件添加日期和時間戳，以增強其實用性並提供清晰的更改時間表。

#### Q：我可以自動執行新增日期和時間戳記的過程嗎？

答：是的，您可以透過建立腳本或程式來自動執行為多個 PDF 文件新增日期和時間戳記的過程，該腳本或程式會迭代文件清單並對每個文件套用相同的標記過程。