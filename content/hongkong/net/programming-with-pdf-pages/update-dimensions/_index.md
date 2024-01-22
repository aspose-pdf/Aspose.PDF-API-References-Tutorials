---
title: 更新 PDF 頁面尺寸
linktitle: 更新 PDF 頁面尺寸
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 更新 PDF 頁面尺寸的逐步指南。根據您的需求檢查尺寸。
type: docs
weight: 150
url: /zh-hant/net/programming-with-pdf-pages/update-dimensions/
---
在本教學中，我們將引導您逐步完成使用 Aspose.PDF for .NET 更新 PDF 文件中的頁面尺寸的過程。我們將解釋捆綁的 C# 原始程式碼，並為您提供全面的指南，幫助您理解並在自己的專案中實現此功能。在本教學結束時，您將了解如何使用 Aspose.PDF for .NET 變更 PDF 文件中的頁面尺寸。

## 先決條件
在開始之前，請確保您具備以下條件：

- C# 程式語言的基礎知識
- 在您的開發環境中安裝 Aspose.PDF for .NET

## 步驟1：定義文檔目錄
首先，您需要設定文檔目錄的路徑。這是您要儲存編輯的 PDF 文件的位置。將“您的文件目錄”替換為適當的路徑。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步驟 2：開啟 PDF 文檔
然後您可以使用以下命令開啟現有的 PDF 文檔`Document`Aspose.PDF 類別。請務必指定正確的文件路徑。

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## 第三步：取得頁面集合
現在您可以使用以下命令存取 PDF 文件的頁面集合`Pages`的財產`Document`班級。

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## 第四步：取得特定頁面
然後，您可以使用集合中頁面的索引來選擇文件的特定頁面。在此範例中，我們使用第二頁（索引 1）。

```csharp
Page pdfPage = pageCollection[1];
```

## 步驟 5：定義新頁面尺寸
現在您可以使用以下命令設定新的頁面大小`SetPageSize()`的方法`Page`目的。在此範例中，我們將頁面尺寸設為 A4（11.7 x 8.3 英吋），並轉換為磅（1 英吋 = 72 磅）。

```csharp
pdfPage.SetPageSize(597.6, 842.4);
```

## 步驟 6：儲存更新後的文檔
最後，您可以使用以下命令將更新的 PDF 文件儲存到文件中：`Save()`的方法`Document`班級。請務必指定正確的路徑和檔案名稱。

```csharp
dataDir = dataDir + "UpdateDimensions_out.pdf";
pdfDocument.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 更新尺寸的範例原始碼 

```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開啟文件
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
//取得頁面集合
PageCollection pageCollection = pdfDocument.Pages;
//取得特定頁面
Page pdfPage = pageCollection[1];
//將頁面大小設定為 A4（11.7 x 8.3 英吋），在 Aspose.Pdf 中，1 英吋 = 72 點
//因此 A4 尺寸（以點為單位）將為 (842.4, 597.6)
pdfPage.SetPageSize(597.6, 842.4);
dataDir = dataDir + "UpdateDimensions_out.pdf";
//儲存更新後的文檔
pdfDocument.Save(dataDir);
System.Console.WriteLine("\nPage dimensions updated successfully.\nFile saved at " + dataDir);

```

## 結論
在本教學中，我們學習如何使用 Aspose.PDF for .NET 更新 PDF 文件中頁面的尺寸。透過遵循此逐步指南，您可以根據需要輕鬆變更 PDF 文件中頁面的尺寸。 Aspose.PDF 提供了強大且靈活的 API，用於處理 PDF 檔案並執行各種操作，包括更改頁面尺寸。有了這些知識，您就可以控制和自訂 PDF 頁面的尺寸，以滿足您的特定需求。

### 更新 PDF 頁面尺寸的常見問題解答

#### Q：如何使用 Aspose.PDF for .NET 更新 PDF 文件中特定頁面的尺寸？

答：若要使用 Aspose.PDF for .NET 更新 PDF 文件中特定頁面的尺寸，您可以依照下列步驟操作：

1. 透過指定原始 PDF 檔案所在的路徑以及要儲存更新的 PDF 檔案的路徑來設定文件目錄。將“您的文件目錄”替換為適當的路徑。
2. 使用以下命令開啟要更新的現有 PDF 文檔`Document`Aspose.PDF 類別。請務必指定原始 PDF 文件的正確路徑。
3. 使用以下命令存取 PDF 文件的頁面集合`Pages`的財產`Document`班級。
4. 使用頁面索引從頁面集合中選擇要更新的特定頁面。在提供的 C# 原始程式碼中，我們使用第二頁（索引 1）。
5. 使用以下命令定義新的頁面大小`SetPageSize()`的方法`Page`目的。在範例中，我們將頁面尺寸設定為 A4 尺寸（11.7 x 8.3 英吋），並轉換為磅（1 英吋 = 72 磅）。
6. 使用以下命令將更新的 PDF 文件儲存到文件中`Save()`的方法`Document`班級。請務必指定正確的路徑和檔案名稱。

#### Q：我可以同時更新PDF文件中多個頁面的尺寸嗎？

答：是的，您可以修改提供的原始程式碼以同時更新 PDF 文件中多個頁面的尺寸。您可以循環瀏覽頁面集合中的所有頁面並為每個頁面設定所需的頁面大小，而不是選擇特定頁面（如步驟 4 所示）。

#### Q：使用 Aspose.PDF for .NET 時如何將頁面尺寸從英吋轉換為磅？

答：在 Aspose.PDF for .NET 中，頁面尺寸的測量單位是點，其中 1 吋相當於 72 點。要將英吋轉換為磅，您可以使用以下公式：`points = inches * 72`。例如，要將頁面尺寸設為 11.7 x 8.3 英寸，您可以將相應的尺寸（以磅為單位）計算為 (11.7 * 72) 和 (8.3 * 72)。

#### Q：更新頁面尺寸會影響PDF文件的內容佈局嗎？

答：是的，更新頁面尺寸將影響該特定頁面上 PDF 文件的內容佈局。當您變更頁面尺寸時，頁面上的內容將會相應調整以適應新尺寸。

#### Q：更新後是否可以恢復變更並恢復原始頁面尺寸？

答：是的，如果您想恢復變更並恢復原始頁面尺寸，您可以在進行變更之前保留原始 PDF 文件的副本，或者在不儲存變更的情況下再次重新開啟原始 PDF 文件。這樣，原始尺寸將被保留。