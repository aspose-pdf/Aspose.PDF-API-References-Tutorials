---
title: 刪除 PDF 中的所有文本
linktitle: 刪除 PDF 中的所有文本
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 從 PDF 文件中刪除所有文字。
type: docs
weight: 290
url: /zh-hant/net/programming-with-text/remove-all-text-from-pdf/
---
在本教學中，我們將說明如何使用 .NET 的 Aspose.PDF 庫從 PDF 文件中刪除所有文字。我們將逐步完成使用 PDF 開啟 PDF 的過程`TextFragmentAbsorber`刪除所有文本，並使用提供的 C# 原始程式碼儲存修改後的 PDF。

## 要求

在開始之前，請確保您具備以下條件：

- 安裝了 Aspose.PDF for .NET 函式庫。
- 對 C# 程式設計有基本了解。

## 第 1 步：設定文檔目錄

首先，您需要設定 PDF 檔案所在目錄的路徑。代替`"YOUR DOCUMENT DIRECTORY"`在裡面`dataDir`變數包含 PDF 檔案的路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：開啟 PDF 文檔

接下來，我們使用以下命令開啟 PDF 文檔`Document`來自 Aspose.PDF 庫的類別。

```csharp
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
```

## 第 3 步：刪除所有文本

我們初始化一個`TextFragmentAbsorber`物件並使用它從 PDF 文件中刪除所有吸收的文字。

```csharp
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb. RemoveAllText(pdfDocument);
```

## 第4步：儲存修改後的PDF

最後，我們將修改後的PDF文件儲存到指定的輸出檔。

```csharp
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### 使用 Aspose.PDF for .NET 從 PDF 中刪除所有文字的範例原始程式碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開啟文件
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
//啟動 TextFragmentAbsorber
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
//刪除所有吸收的文本
absorber.RemoveAllText(pdfDocument);
//儲存文件
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## 結論

在本教學中，您學習如何使用 .NET 的 Aspose.PDF 庫從 PDF 文件中刪除所有文字。透過遵循逐步指南並執行提供的 C# 程式碼，您可以開啟 PDF，使用`TextFragmentAbsorber`，並儲存修改後的PDF。

### 常見問題解答

#### Q：「刪除 PDF 中的所有文字」教學的目的是什麼？

答：「從 PDF 中刪除所有文字」教學提供瞭如何使用 .NET 的 Aspose.PDF 庫從 PDF 文件中刪除所有文字的說明。本教學將引導您完成開啟 PDF 的過程，使用`TextFragmentAbsorber`刪除所有文本，並儲存修改後的 PDF。

#### Q：為什麼我要刪除 PDF 文件中的所有文字？

答：在您需要建立不包含任何文字內容的文件版本的情況下，從 PDF 文件中刪除所有文字非常有用。這對於隱私原因或產生文件佈局的視覺表示而不顯示其文字資訊可能很有幫助。

#### Q：如何設定文檔目錄？

A：設定文檔目錄：

1. 代替`"YOUR DOCUMENT DIRECTORY"`在裡面`dataDir`變數包含 PDF 檔案所在目錄的路徑。

#### Q：如何使用 Aspose.PDF 庫刪除 PDF 文件中的所有文字？

答：本教學將逐步引導您完成整個過程：

1. 使用以下命令開啟 PDF 文檔`Document`班級。
2. 初始化一個`TextFragmentAbsorber`目的。
3. 使用吸收器刪除 PDF 文件中所有吸收的文字。
4. 儲存修改後的PDF文件。

#### Q：我可以選擇性地刪除文件特定區域的文字嗎？

答：本教學的重點是從整個 PDF 文件中刪除所有文字。如果您想要選擇性地從特定區域刪除文本，則需要修改方法並使用更複雜的邏輯來識別和刪除特定的文本片段。

#### 問：如何`TextFragmentAbsorber` work to remove text?

答： 的`TextFragmentAbsorber`是Aspose.PDF庫提供的一個類，可以從PDF文件中吸收文字片段。透過使用`RemoveAllText`的方法`TextFragmentAbsorber`類，您可以從文件中刪除所有吸收的文字片段。

#### Q：執行所提供的程式碼的預期結果是什麼？

答：透過遵循教學課程並運行提供的 C# 程式碼，您將從輸入 PDF 文件中刪除所有文本，並將修改後的版本儲存為輸出 PDF 檔案。

#### Q：我可以修改程式碼以僅刪除特定頁面或區域中的文字嗎？

答：是的，您可以修改程式碼來實現這一點。對於選擇性文字刪除，您需要調整程式碼以定位 PDF 文件中的特定頁面或區域。

#### Q：本教學需要有效的 Aspose 授權嗎？

答：是的，需要有效的 Aspose 許可證才能成功執行本教程中的程式碼。您可以從 Aspose 網站取得完整許可證或 30 天臨時許可證。