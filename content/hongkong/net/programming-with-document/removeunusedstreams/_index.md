---
title: 刪除 PDF 檔案中未使用的串流
linktitle: 刪除 PDF 檔案中未使用的串流
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 刪除 PDF 檔案中未使用的串流。我們的逐步指南。
type: docs
weight: 270
url: /zh-hant/net/programming-with-document/removeunusedstreams/
---
在此範例中，我們將討論如何使用 Aspose.PDF for .NET 刪除 PDF 檔案中未使用的串流。我們將提供有關如何執行此操作的逐步指南，包括完整的原始程式碼和解釋。

## 第1步：文檔目錄的路徑

程式碼的第一行設定 PDF 文件所在目錄的路徑。確保將“您的文件目錄”替換為實際的目錄路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步驟 2：開啟文檔

下一行程式碼使用 Aspose.PDF for .NET 函式庫開啟 PDF 文件。

```csharp
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## 步驟3：設定RemoveUnusedStreams選項

下一步是將 RemoveUnusedStreams 選項設為 true。這將從 PDF 文件中刪除所有未使用的流。

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	RemoveUnusedStreams = true
};
```

## 步驟 4：使用 OptimizationOptions 優化 PDF 文檔

現在我們已經設定了最佳化選項，我們可以使用以下程式碼行來優化 PDF 文件。

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## 第 5 步：儲存更新的文檔

最後，我們可以使用 Document 類別的 Save 方法來儲存更新的文件。

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
pdfDocument.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 刪除未使用的串流的範例原始程式碼

以下是使用 Aspose.PDF for .NET 刪除未使用的串流的範例原始程式碼。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開啟文件
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
//設定RemoveUsedStreams選項
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	RemoveUnusedStreams = true
};
//使用 OptimizationOptions 優化 PDF 文檔
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "OptimizeDocument_out.pdf";
//儲存更新的文檔
pdfDocument.Save(dataDir);
```

## 結論

透過刪除未使用的串流來優化 PDF 文件對於提高效能和減小檔案大小至關重要。 Aspose.PDF for .NET 透過提供一個方便的方法來使用以下命令刪除未使用的串流，從而簡化了此過程`OptimizationOptions`。逐步指南和提供的 C# 原始程式碼可讓開發人員輕鬆地在其 .NET 應用程式中實現此功能。透過遵循這些說明，開發人員可以有效優化其 PDF 文件並改善 .NET 專案中的整體 PDF 處理。

### 刪除 PDF 檔案中未使用的串流的常見問題解答

#### Q：PDF 文件中未使用的流是什麼？

答：PDF 文件中未使用的流是文件內容中未引用或使用的文件部分。這些流可能包括不再需要但仍存在於 PDF 文件中的圖像、字體或其他資源。

#### Q：刪除未使用的串流對 PDF 文件有何好處？

答：從 PDF 文件中刪除未使用的串流可減少檔案大小，從而縮短載入時間並提高效能。它有助於優化 PDF 文件，以獲得更好的用戶體驗和高效的儲存。

#### Q：開發人員能否指定使用 Aspose.PDF for .NET 刪除哪些串流？

答：是的，開發人員可以透過設定來控制未使用的流的刪除`RemoveUnusedStreams`選項中的`OptimizationOptions`。這使他們可以根據自己的具體需求靈活地選擇要刪除的串流。