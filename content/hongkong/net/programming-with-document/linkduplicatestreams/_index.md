---
title: 連結重複的串流
linktitle: 連結重複的串流
second_title: Aspose.PDF for .NET API 參考
description: 透過此逐步指南，了解如何使用 Aspose.PDF for .NET Link Duplicate Streams 功能來最佳化您的 PDF 文件。
type: docs
weight: 230
url: /zh-hant/net/programming-with-document/linkduplicatestreams/
---
Aspose.PDF for .NET 是一個全面且強大的程式庫，提供了多種處理 PDF 檔案的功能。其主要功能之一是優化 PDF 文件的能力。在本文中，我們將說明如何使用 Aspose.PDF for .NET 的連結重複流功能來最佳化 PDF 檔案。我們將提供逐步說明並包含完整的原始程式碼範例，以便開發人員輕鬆遵循。

## 第 1 步：開啟 PDF 文檔

若要使用 Aspose.PDF for .NET 開啟 PDF 文檔，請依照下列步驟操作：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開啟文件
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

在上面的程式碼中，將“YOUR DOCUMENT DIRECTORY”替換為專案目錄的路徑。

## 步驟 2：設定 LinkDuplicateStreams 選項

若要設定 LinkDuplicateStreams 選項，請依照下列步驟操作：

```csharp
//設定 LinkDuplicateStreams 選項
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    LinkDuplcateStreams = true
};
```

在上面的程式碼中，我們建立了 OptimizationOptions 的新實例並將 LinkDuplicateStreams 選項設為 true。

## 步驟 3：最佳化 PDF 文件

若要最佳化 PDF 文檔，請依照下列步驟操作：

```csharp
//使用 OptimizationOptions 優化 PDF 文檔
pdfDocument.OptimizeResources(optimizeOptions);
```

在上面的程式碼中，我們使用 pdfDocument 物件的 OptimizeResources 方法，透過先前建立的 OptimizationOptions 來優化 PDF 文件。

## 步驟 4：儲存更新後的文檔

若要儲存更新的文檔，請依照下列步驟操作：

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
//儲存更新的文檔
pdfDocument.Save(dataDir);
```

在上面的程式碼中，我們使用 pdfDocument 物件的 Save 方法將更新的文件儲存到專案目錄中名為「OptimizeDocument_out.pdf」的新檔案中。

### 使用 Aspose.PDF for .NET 連結重複流的範例原始碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開啟文件
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
//設定 LinkDuplicateStreams 選項
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	LinkDuplcateStreams = true
};
//使用 OptimizationOptions 優化 PDF 文檔
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "OptimizeDocument_out.pdf";
//儲存更新的文檔
pdfDocument.Save(dataDir);
```

## 結論

Aspose.PDF for .NET 的連結重複流功能提供了一種透過縮小 PDF 檔案大小來優化 PDF 檔案的有效方法。透過識別和連結重複流，該程式庫有助於創建更有效率的 PDF 文檔，而不會犧牲資料完整性或視覺品質。開發人員可以使用提供的步驟和原始程式碼範例輕鬆實現此功能，從而提高 PDF 文件的效能和儲存效率。

### 常見問題解答

#### Q：Aspose.PDF for .NET 中的連結重複流功能的用途是什麼？

答：Aspose.PDF for .NET 中的連結重複流功能用於透過識別和連結文件中的重複流來優化 PDF 文件。在 PDF 檔案中，可能存在重複的流（例如圖像或字體），從而消耗不必要的空間。透過連結這些重複的串流，可以縮小檔案大小，從而產生更有效率且更小的 PDF 文件。

#### Q：連結重複流功能如何運作？

答：「連結重複流」功能的工作原理是分析 PDF 文件的內容流並識別具有相同內容的重複流。該功能不是單獨儲存這些重複的流，而是在它們之間創建鏈接，從而有效地共享相同的內容。這種優化技術可以減少 PDF 文件的整體大小，而不影響其視覺外觀或功能。

#### Q：「連結重複流」功能是否會導致 PDF 文件中的資料或品質遺失？

答：不會，連結重複流功能不會導致 PDF 文件中的任何資料或品質損失。它僅透過連結重複的流來優化文件大小，而不改變文件的內容或視覺外觀。該功能旨在確保 PDF 文件保持完整併保持其原始品質。