---
title: 允許重複使用頁面內容
linktitle: 允許重複使用頁面內容
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 啟用「允許重複使用頁面內容」功能來最佳化 PDF。減小檔案大小並提高效能。
type: docs
weight: 50
url: /zh-hant/net/programming-with-document/allowresusepagecontent/
---
在本教學中，我們將說明如何使用 Aspose.PDF for .NET 啟用「允許重複使用頁面內容」功能。此功能透過重複使用頁面內容、減少檔案大小並提高效能來優化 PDF 文件。請按照以下逐步指南進行操作：

## 第 1 步：載入 PDF 文檔

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## 步驟 2：設定AllowReusePageContent 選項

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
};
```

## 步驟 3：最佳化 PDF 文件

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## 步驟 4：儲存更新後的文檔

```csharp
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## 步驟 5：檢查檔案大小減少狀況

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

恭喜！您已成功允許重複使用 PDF 文件中的頁面內容。

### 使用 Aspose.PDF for .NET 允許重複使用頁面內容的範例原始碼：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//開啟文件
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");

//設定允許重複使用頁面內容選項
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
};

Console.WriteLine("Start");

//使用 OptimizationOptions 優化 PDF 文檔
pdfDocument.OptimizeResources(optimizeOptions);

//儲存更新的文檔
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");

Console.WriteLine("Finished");

var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);

Console.WriteLine("\nAllowed reuse of page content successfully.\nFile saved at " + dataDir);
```

現在，您可以透過允許重複使用頁面內容來有效優化 PDF 文件。

## 結論

在本教學中，我們說明如何使用 Aspose.PDF for .NET 啟用「允許重複使用頁面內容」功能。透過遵循提供的逐步指南並利用 C# 原始程式碼，您可以透過允許重複使用頁面內容來有效優化 PDF 文件。此最佳化會產生更小的 PDF 文件，從而在處理大型 PDF 文件時加快載入時間並提高效能。 Aspose.PDF for .NET 為 PDF 優化提供了強大且使用者友好的解決方案，讓您輕鬆建立高效且高品質的 PDF 檔案。

### 常見問題解答

#### Q：在 PDF 文件中啟用「允許重複使用頁面內容」功能的目的是什麼？

答：在 PDF 文件中啟用「允許重複使用頁面內容」功能可以透過重複使用頁面內容來優化文件，從而減少檔案大小並提高整體效能。此優化可產生更小的 PDF 文件，而不會影響內容品質。

#### 問：「允許重複使用頁面內容」功能如何運作？

答：啟用「允許重複使用頁面內容」功能後，PDF 文件中的相同頁面物件將被共用和重複使用，而不是每次出現時重複。這種頁面內容的共享顯著減少了整體文件大小。

#### Q：我可以恢復優化並恢復原始文件嗎？

答：不會，一旦執行「允許重複使用頁面內容」優化並保存 PDF 文檔，所做的更改就是永久性的。建議在執行任何最佳化之前保留原始文件的備份。

#### Q：啟用此功能是否會影響 PDF 文件的視覺外觀或內容？

答：啟用「允許重複使用頁面內容」功能不會影響 PDF 文件的視覺外觀或內容。它僅優化文件的內部結構，以減少冗餘並提高效率。

#### Q：Aspose.PDF for .NET 是 PDF 最佳化和操作的可靠解決方案嗎？

答：是的，Aspose.PDF for .NET 是一個可靠且功能豐富的 PDF 最佳化和操作庫。它提供了廣泛的選項來優化 PDF 文件，包括減小文件大小、刪除未使用的資源以及增強整體效能。