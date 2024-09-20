---
title: 在 PDF 檔案中新增表格
linktitle: 在 PDF 檔案中新增表格
second_title: Aspose.PDF for .NET API 參考
description: 透過此逐步教學，了解如何使用 Aspose.PDF for .NET 輕鬆將表格新增至 PDF 檔案。非常適合 C# 開發人員。
type: docs
weight: 40
url: /zh-hant/net/programming-with-tables/add-table/
---
## 介紹

無論是在報告、發票或任何需要清晰呈現資訊的文件中，表格對於建立和組織資料至關重要。 Aspose.PDF for .NET 讓以程式設計方式為 PDF 檔案新增表格變得異常簡單。如果您希望自動產生 PDF，本教學正是您所需要的。我們將逐步介紹如何為 PDF 文件添加表格，並以詳細且易於理解的方式進行分解。

## 先決條件

在我們開始編寫程式碼之前，讓我們確保您擁有所需的一切。

-  Aspose.PDF for .NET：您需要安裝該程式庫。你可以[在此下載 Aspose.PDF for .NET](https://releases.aspose.com/pdf/net/).
- .NET Framework：確保您在 .NET 環境中運作。
- Visual Studio 或任何其他 C# IDE：使用您喜歡的 IDE 編寫和執行程式碼。
- 對 C# 的基本了解：本教學假設您熟悉 C# 程式設計。

如果您沒有許可證，請不要擔心！您可以使用[免費試用](https://releases.aspose.com/)或請求[臨時執照](https://purchase.aspose.com/temporary-license/)嘗試這些功能。

## 導入包

在深入了解逐步指南之前，請確保您已匯入必要的命名空間和庫。這些匯入可確保您的程式碼可以與 PDF 文件無縫互動。

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

完成此操作後，您就可以開始編碼了。

## 第 1 步：載入來源 PDF 文檔

首先，我們需要載入要修改或新增表格的 PDF 文件。這是確保您使用正確文件的基礎步驟。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//載入來源 PDF 文件
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "AddTable.pdf");
```
 
這裡，`Aspose.Pdf.Document`用於從指定目錄載入現有 PDF 檔案。文件路徑設定為`dataDir`。該文件現已載入並準備好進行進一步操作。  
將 PDF 檔案想像為您的空白畫布，表格將成為您的傑作！

## 第2步：初始化一個新表

現在您已經載入了 PDF 文檔，下一步是建立一個表格物件。該表稍後將填充行和單元格。

```csharp
//初始化表的新實例
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```
 
這`Table`類別是 Aspose.PDF 庫的一部分。通過初始化它，您實際上是在告訴程序，“嘿，我準備好創建一個表結構了！”這就像在添加肉體（資料）之前先設定骨架。

## 步驟 3：設定表格邊框和儲存格邊框

表格需要結構，邊框有助於定義每個單元格的限制。在此步驟中，您將設定表格外邊框和每個儲存格邊框的外觀。

```csharp
//將表格邊框顏色設定為淺灰色
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));

//設定表格單元格的邊框
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```
 
我們使用以下命令為表格和每個單元格設定了淺灰色邊框`BorderInfo`。這使表格結構具有乾淨、專業的外觀。這就像給你的桌子一個整齊的框架，這樣它看起來就不會顯得雜亂無章。

## 步驟 4：將行和單元格新增至表中

這是您填充表的地方。我們將建立多行，每行包含一些帶有資料的儲存格。

```csharp
//建立一個循環以添加 10 行
for (int row_count = 1; row_count < 10; row_count++)
{
    //將行加入表中
    Aspose.Pdf.Row row = table.Rows.Add();
    //新增表格單元格
    row.Cells.Add("Column (" + row_count + ", 1)");
    row.Cells.Add("Column (" + row_count + ", 2)");
    row.Cells.Add("Column (" + row_count + ", 3)");
}
```
 
在這裡，我們建立了一個運行 10 次的循環，在表中新增 10 行。每行包含三個儲存格。每個單元格中的內容是使用動態產生的`row_count`使表格看起來組織得當。將其視為用資訊填充網格！

## 步驟 5：將表格新增至 PDF 文檔

填入表格後，就可以將其插入 PDF 文件中了。

```csharp
//將表格物件新增至輸入文件的第一頁
doc.Pages[1].Paragraphs.Add(table);
```
 
現在您正在將完全結構化的表格新增至 PDF 文件的第一頁。`Pages[1]`指的是第一頁，並且`Paragraphs.Add()`確保該表作為新段落添加到該頁面上。這是您的表格錨定到 PDF 中的時刻。

## 步驟 6：儲存更新後的 PDF 文檔

最後，新增表格後，儲存文件以保留變更。

```csharp
//儲存包含表格物件的更新文檔
dataDir = dataDir + "document_with_table_out.pdf";
doc.Save(dataDir);
```
 
您現在將更新的文檔保存在指定的目錄中。原始文件保持不變，並使用新增的表產生一個新文件。

## 結論

透過執行這些步驟，您現在已成功使用 Aspose.PDF for .NET 將表格新增至 PDF 檔案。此過程精簡且功能強大，可讓您輕鬆自動產生和編輯文件。表格是呈現結構化資訊的基礎，現在您可以使用工具將它們無縫整合到任何 PDF 文件中。

## 常見問題解答

### 我可以進一步定製表格嗎？
是的！您可以調整儲存格填滿、文字對齊方式，甚至為儲存格新增背景顏色。這`Aspose.PDF.Table`類別提供了許多自訂選項。

### 如何在表中新增更多列？
只需修改將儲存格新增至每行的循環即可。使用以下命令添加所需數量的單元格，而不是三個單元格`row.Cells.Add()`.

### Aspose.PDF是否支援新增圖片至表格？
是的，您可以使用以下命令在表格單元格內插入圖像`ImageFragment`班級。

### 有沒有辦法合併表格中的儲存格？
是的，Aspose.PDF 允許使用水平或垂直合併儲存格`ColSpan`和`RowSpan`特性。

### 我可以將表格新增到 PDF 的特定頁面嗎？
絕對地！而不是`Pages[1]`，您可以指定要插入表格的任何頁碼。