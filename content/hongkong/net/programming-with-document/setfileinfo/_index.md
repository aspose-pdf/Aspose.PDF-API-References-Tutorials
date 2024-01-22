---
title: 在 PDF 文件中設定文件訊息
linktitle: 在 PDF 文件中設定文件訊息
second_title: Aspose.PDF for .NET API 參考
description: 透過此逐步指南，了解如何使用 Aspose.PDF for .NET 在 PDF 文件中設定文件資訊。
type: docs
weight: 310
url: /zh-hant/net/programming-with-document/setfileinfo/
---
如果您正在開發的專案需要使用 Aspose.PDF for .NET 管理 PDF 文件，您可能想要利用的功能之一是為 PDF 文件設定文件資訊的功能。文件資訊包括各種詳細信息，例如作者、創建日期、關鍵字、修改日期、主題和標題。本指南將引導您完成使用 C# 原始程式碼和 Aspose.PDF for .NET 設定 PDF 文件的文件資訊的過程。

## 使用 Aspose.PDF for .NET 設定文件資訊的逐步指南

1. 在 Visual Studio IDE 中建立一個新的 C# 專案。
2. 在專案中新增對 Aspose.PDF for .NET 函式庫的參考。
3. 透過提供要修改其文件資訊的 PDF 文件的路徑來建立新的 PDF 文件物件。

## 步驟1：設定文檔目錄的路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步驟 2：開啟 PDF 文檔

```csharp
//開啟文件
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## 步驟3：使用DocumentInfo物件存取PDF文件的文件資訊。

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## 步驟 4：使用 DocumentInfo 物件的屬性設定所需的檔案資訊值。

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

## 步驟5：將更新後的PDF文件儲存到指定位置。

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
pdfDocument.Save(dataDir);
```

## 步驟6：驗證文件資訊是否已成功更新。

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

您已使用 Aspose.PDF for .NET 成功設定 PDF 文件的文件資訊。

### 使用 Aspose.PDF for .NET 設定文件資訊的範例原始碼


```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//開啟文件
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");

//指定文檔資訊
DocumentInfo docInfo = new DocumentInfo(pdfDocument);

docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";

dataDir = dataDir + "SetFileInfo_out.pdf";
//儲存輸出文檔
pdfDocument.Save(dataDir);

Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

## 結論

總之，Aspose.PDF for .NET 提供了一個簡單有效的方法來設定 PDF 文件的文件資訊。透過執行上述步驟，您可以使用 C# 原始程式碼輕鬆地為 PDF 文件設定所需的文件資訊值。

### PDF 文件中設定文件資訊的常見問題解答

#### Q：我可以設定範例中未提及的其他文件資訊屬性嗎？

答：是的，您可以使用以下命令設定其他檔案資訊屬性`DocumentInfo`Aspose.PDF for .NET 中的物件。這`DocumentInfo`類別提供了各種屬性，可讓您設定附加訊息，例如生產者、版本和自訂屬性。

#### Q：是否可以從現有 PDF 文件中檢索文件資訊？

答：是的，您可以使用 Aspose.PDF for .NET 從現有 PDF 文件中檢索文件資訊。為此，您可以使用`DocumentInfo`物件存取文件資訊屬性並讀取 PDF 文件中儲存的資訊。

#### Q：設定文件資訊會修改原始PDF文件嗎？

答：不會，使用 Aspose.PDF for .NET 設定文件資訊不會修改原始 PDF 文件。相反，它會使用更新的文件資訊來建立一個新的 PDF 文件。原始 PDF 文件保持不變。