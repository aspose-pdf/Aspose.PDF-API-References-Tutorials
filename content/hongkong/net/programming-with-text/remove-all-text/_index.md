---
title: 刪除 PDF 文件中的所有文本
linktitle: 刪除 PDF 文件中的所有文本
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 刪除 PDF 檔案中的所有文字。
type: docs
weight: 280
url: /zh-hant/net/programming-with-text/remove-all-text/
---
在本教學中，我們將說明如何使用 .NET 的 Aspose.PDF 庫刪除 PDF 檔案中的所有文字。我們將逐步完成開啟 PDF、從每個頁面選擇和刪除文字以及使用提供的 C# 原始碼儲存修改後的 PDF 的過程。

## 要求

在開始之前，請確保您具備以下條件：

- 安裝了 Aspose.PDF for .NET 函式庫。
- 對 C# 程式設計有基本了解。

## 第 1 步：設定文檔目錄

首先，您需要設定 PDF 檔案所在目錄的路徑。代替`"YOUR DOCUMENT DIRECTORY"`在`dataDir`變數包含 PDF 檔案的路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：開啟 PDF 文檔

接下來，我們使用以下命令開啟 PDF 文檔`Document`來自 Aspose.PDF 庫的類別。

```csharp
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
```

## 第 3 步：刪除每頁中的文本

我們循環遍歷 PDF 文件的所有頁面並使用`OperatorSelector`選擇每頁上的所有文字。然後，我們刪除選定的文字。

```csharp
for (int i = 1; i <= pdfDocument.Pages.Count; i++)
{
     Page page = pdfDocument.Pages[i];
     OperatorSelector operatorSelector = new OperatorSelector(new Aspose.Pdf.Operators.TextShowOperator());
     page.Contents.Accept(operatorSelector);
     page.Contents.Delete(operatorSelector.Selected);
}
```

## 第4步：儲存修改後的PDF

最後，我們將修改後的PDF文件儲存到指定的輸出檔。

```csharp
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### 使用 Aspose.PDF for .NET 刪除所有文字的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開啟文件
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
//循環瀏覽 PDF 文件的所有頁面
for (int i = 1; i <= pdfDocument.Pages.Count; i++)
{
	Page page = pdfDocument.Pages[i];
	OperatorSelector operatorSelector = new OperatorSelector(new Aspose.Pdf.Operators.TextShowOperator());
	//選擇頁面上的所有文本
	page.Contents.Accept(operatorSelector);
	//刪除所有文字
	page.Contents.Delete(operatorSelector.Selected);
}
//儲存文件
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## 結論

在本教學中，您學習如何使用 .NET 的 Aspose.PDF 庫從 PDF 文件中刪除所有文字。透過遵循逐步指南並執行提供的 C# 程式碼，您可以開啟 PDF，選擇並刪除每個頁面中的文本，然後儲存修改後的 PDF。

### 常見問題解答

#### Q：「刪除 PDF 檔案中的所有文字」教學的目的是什麼？

答：「刪除 PDF 檔案中的所有文字」教學課程旨在示範如何使用 .NET 的 Aspose.PDF 庫刪除 PDF 文件中的所有文字。本教學提供逐步指南和 C# 原始程式碼，幫助您開啟 PDF 文件、選擇和刪除每個頁面中的文字以及儲存修改後的 PDF。

#### Q：為什麼我要刪除 PDF 文件中的所有文字？

答：在多種情況下，從 PDF 文件中刪除所有文字可能會很有用。例如，您可能希望透過刪除敏感資訊來建立文件的編輯版本，或者您可能需要產生文件的視覺化表示（不包含文字內容）。

#### Q：如何設定文檔目錄？

A：設定文檔目錄：

1. 代替`"YOUR DOCUMENT DIRECTORY"`在`dataDir`變數包含 PDF 檔案所在目錄的路徑。

#### Q：如何從 PDF 文件的每一頁中刪除文字？

答：本教學將引導您完成循環遍歷 PDF 文件的所有頁面，使用選擇器選擇每個頁面上的所有文字的過程。`OperatorSelector`，然後刪除選取的文字。

#### Q：我可以選擇性地刪除特定頁面中的文字嗎？

答：是的，您可以修改循環，透過指定要處理的頁碼選擇性地刪除特定頁面中的文字。本教學中提供的範例示範如何循環瀏覽所有頁面，但您可以對其進行調整以滿足您的要求。

#### Q：如何儲存修改後的PDF文件？

答：刪除每頁文字後，您可以使用以下命令儲存修改後的 PDF 文件：`Save`的方法`Document`班級。提供所需的輸出檔案路徑並指定所需的儲存格式作為參數`Save`方法。

#### Q：本教程的預期輸出是什麼？

答：按照教學課程並執行提供的 C# 程式碼，您將產生一個修改後的 PDF 文檔，其中每頁上的所有文字都已刪除。

#### Q：我可以使用不同的運算子來刪除其他類型的內容嗎？

答：是的，您可以使用不同的運算子來定位和刪除 PDF 文件中的各種類型的內容，例如影像或圖形元素。本教程中提供的範例特別關注刪除文字。

#### Q：本教學需要有效的 Aspose 授權嗎？

答：是的，本教學需要有效的 Aspose 許可證才能正常運作。您可以從 Aspose 網站購買完整許可證或取得 30 天的臨時許可證。