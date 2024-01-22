---
title: 取得頁面中的所有註釋
linktitle: 取得頁面中的所有註釋
second_title: Aspose.PDF for .NET API 參考
description: 透過此逐步指南，了解如何使用 Aspose.PDF for .NET 從 PDF 頁面擷取所有註解。
type: docs
weight: 70
url: /zh-hant/net/annotations/getallannotationsfrompage/
---
本文將引導您完成使用 Aspose.PDF for .NET 從 PDF 頁面擷取所有註解的過程。 Aspose.PDF for .NET 是一個允許開發人員建立、編輯和轉換 PDF 文件的程式庫。借助本指南，您將能夠使用提供的 C# 原始程式碼從特定 PDF 頁面取得所有註釋。

請依照以下步驟操作如何使用 Aspose.PDF for .NET 取得 PDF 頁面的所有註解：

## 第1步：文檔目錄的路徑

使用 Aspose.PDF for .NET 從 PDF 頁面取得所有註解的第一步是設定儲存 PDF 檔案的文件目錄的路徑。您可以透過修改以下程式碼行來完成此操作：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
## 步驟 2：您的 PDF 文件已存儲

將「您的文件目錄」替換為儲存 PDF 檔案的資料夾路徑。例如：

```csharp
string dataDir = @"C:\Users\JohnDoe\Documents\PDFs\";
```

## 第 3 步：開啟文檔

下一步是開啟包含要提取的註釋的 PDF 文件。您可以透過新增以下程式碼來完成此操作：

```csharp
Document pdfDocument = new Document(dataDir + "GetAllAnnotationsFromPage.pdf");
```

這行程式碼初始化 Document 類別的新實例並載入 PDF 文件「GetAllAnnotationsFromPage.pdf」。將此檔案名稱替換為您的 PDF 檔案的名稱。

## 第 4 步：循環所有註釋

開啟 PDF 文件後，您可以循環瀏覽特定頁面上的所有註釋。例如，若要循環遍歷 PDF 文件第一頁上的所有註釋，請新增以下程式碼：

```csharp
foreach (MarkupAnnotation annotation in pdfDocument.Pages[1].Annotations)
{
    //代碼放在這裡
}
```

此程式碼循環遍歷 PDF 文件第一頁上的所有註釋，並將每個註釋指派給「annotation」變數。

## 第5步：取得註釋屬性

若要擷取每個註解的屬性，您可以在 foreach 迴圈內新增以下程式碼：

```csharp
Console.WriteLine("Title : {0} ", annotation.Title);
Console.WriteLine("Subject : {0} ", annotation.Subject);
Console.WriteLine("Contents : {0} ", annotation.Contents);
```

此程式碼將每個註解的標題、主題和內容寫入控制台。

### 使用 Aspose.PDF for .NET 從頁面取得所有註解的範例原始程式碼

以下是使用 Aspose.PDF for .NET 從 PDF 頁面取得所有註解的完整原始碼：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//開啟文件
Document pdfDocument = new Document(dataDir + "GetAllAnnotationsFromPage.pdf");

//循環遍歷所有註釋
foreach (MarkupAnnotation annotation in pdfDocument.Pages[1].Annotations)
{
	//取得註釋屬性
	Console.WriteLine("Title : {0} ", annotation.Title);
	Console.WriteLine("Subject : {0} ", annotation.Subject);
	Console.WriteLine("Contents : {0} ", annotation.Contents);                
}
```

## 結論

在本教學中，我們探討如何使用 Aspose.PDF for .NET 從 PDF 文件的特定頁面取得所有註解。透過遵循逐步指南並使用提供的 C# 原始程式碼，開發人員可以輕鬆地從 PDF 文件中提取和管理註釋。

### 常見問題解答

#### Q：PDF文件中的註解是什麼？

答：PDF 文件中的註解是互動式元素，可提供有關文件特定部分的附加資訊、註解或註解。註釋可以包括文字註釋、評論、突出顯示和其他互動元素。

#### Q：我可以只取得特定頁面的註解嗎？

答：是的，使用 Aspose.PDF for .NET，您可以根據您的要求從特定頁面甚至整個文件中取得註解。

#### Q：Aspose.PDF for .NET 支援從受密碼保護的 PDF 檔案中提取註解嗎？

答：是的，Aspose.PDF for .NET 支援從受密碼保護的 PDF 檔案中提取註解。使用以下方式載入 PDF 文件時需要提供正確的密碼`Document`班級。

#### Q：我可以根據註釋的屬性（例如內容或作者）過濾註釋嗎？

答：是的，Aspose.PDF for .NET 提供了根據屬性（例如內容、作者或建立日期）存取和過濾註解的方法。您可以循環瀏覽所有註釋並檢查要過濾的特定屬性。

#### Q：Aspose.PDF for .NET 支援從不同類型的 PDF 文件中提取註解嗎？

答：是的，Aspose.PDF for .NET 提供了多種方法從不同類型的 PDF 文件中提取註釋，包括文字標記註釋、自由文字註釋等。