---
title: 取消嵌入字體並優化 PDF 文件
linktitle: 取消嵌入字體並優化 PDF 文件
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 取得非嵌入字體並優化 PDF 檔案。逐步指南。
type: docs
weight: 370
url: /zh-hant/net/programming-with-document/unembedfonts/
---
Aspose.PDF for .NET 是一個功能強大的程式庫，提供了廣泛的處理 PDF 文件的功能。它的功能之一是從 PDF 文件中獲取未嵌入的字體。如果您需要從 PDF 文件中提取字體並在其他應用程式中使用它們，這會很有用。

我們將提供逐步指南來解釋 Aspose.PDF for .NET 的取得非嵌入字體功能的以下 C# 原始碼。

## 第一步：設定文檔目錄路徑

在開始之前，我們需要設定 PDF 文件所在目錄的路徑。我們將該路徑儲存在名為「dataDir」的變數中。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

將「您的文件目錄」替換為 PDF 文件所在目錄的實際路徑。

## 第 2 步：開啟 PDF 文檔

第一步是載入您想要執行此操作的 PDF 文檔，使用`Document`.NET 的 Aspose.PDF 類別。以下程式碼片段展示如何載入 PDF 文件：

```csharp
//開啟文件
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## 步驟 3：設定 UnembedFonts 選項

要從 PDF 文件中取得未嵌入的字體，您需要設定`UnembedFonts`選項`true`。此選項可在`OptimizationOptions`班級。以下程式碼片段展示如何設定`UnembedFonts`選項：

```csharp
//設定取消嵌入字體選項
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## 步驟 4：最佳化 PDF 文件

設定後`UnembedFonts`選項，您可以使用以下命令優化 PDF 文檔`OptimizeResources`的方法`Document`班級。以下程式碼片段展示如何優化 PDF 文件：

```csharp
//使用 OptimizationOptions 優化 PDF 文檔
pdfDocument.OptimizeResources(optimizeOptions);
```

## 步驟5：儲存更新後的文檔

 PDF 文件優化後，您可以使用以下命令儲存更新後的文件：`Save`的方法`Document`班級。以下程式碼片段顯示如何儲存更新的文件：

```csharp
//儲存更新的文檔
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## 第 6 步：取得原始檔案大小和縮小後的檔案大小

最後，您可以使用以下命令來取得 PDF 文件的原始文件大小和縮小後的文件大小`FileInfo`System.IO 類別。以下程式碼片段顯示如何取得原始檔案大小和縮小後的檔案大小：

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### 使用 Aspose.PDF for .NET 取得未嵌入字體的範例原始碼

以下是使用 Aspose.PDF for .NET 從 PDF 文件中取得未嵌入字體的完整範例原始碼：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開啟文件
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
//設定取消嵌入字體選項
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
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
```

## 結論

在本教學中，我們示範如何使用 Aspose.PDF for .NET 從 PDF 文件中取得未嵌入的字型。透過遵循逐步指南，您可以在 C# 應用程式中輕鬆實現此功能。當您需要單獨使用提取的字體或確保跨不同平台的字體使用一致時，取消嵌入字體可能會很有用。

## 常見問題解答

#### Q：從 PDF 文件中取消嵌入字體的目的是什麼？

答：從 PDF 文件中取消嵌入字體可讓您提取嵌入的字體並在其他應用程式中使用它們。這對於確保一致的字體渲染和保留文件的視覺外觀非常有用。

#### Q：如何在C#程式碼中指定文檔目錄的路徑？

 A：要指定文件目錄的路徑，替換`"YOUR DOCUMENT DIRECTORY"`在程式碼中新增 PDF 文件所在目錄的實際路徑。

####  Q：什麼是`UnembedFonts` option do, and where is it set?

答： 的`UnembedFonts`選項，可在`OptimizationOptions`類，啟用或停用從 PDF 文件中取消嵌入字體。將此選項設為`true`，使用以下程式碼：

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### Q：我可以恢復優化過程中所做的變更嗎？

答：Aspose.PDF for .NET 在最佳化過程中不會對原始 PDF 文件進行永久性變更。最佳化過程是在文件的副本上執行的，保持原始文件不變。

#### Q：如何查看優化後的原始檔案大小和縮小後的檔案大小？

答：您可以使用`FileInfo`類的`System.IO`取得原始檔案大小和縮小後的檔案大小。以下是實現此目的的範例程式碼片段：

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```