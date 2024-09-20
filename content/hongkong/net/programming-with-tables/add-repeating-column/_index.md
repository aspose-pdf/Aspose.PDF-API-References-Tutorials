---
title: 在 PDF 文件中新增重複列
linktitle: 在 PDF 文件中新增重複列
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 將重複列新增至 PDF 文件。帶有範例和程式碼的逐步指南。非常適合開發人員。
type: docs
weight: 20
url: /zh-hant/net/programming-with-tables/add-repeating-column/
---
## 介紹

如果您正在處理 PDF 文件並需要新增重複列，那麼您來對地方了！使用 Aspose.PDF for .NET，您可以輕鬆管理 PDF 中的表單和內容。無論您是建立動態報告、發票或任何其他結構化文檔，重複列都可以改變組織資料的遊戲規則。讓我們深入了解如何在 PDF 文件中新增重複列的逐步指南。

## 先決條件

在我們進入程式碼之前，讓我們確保您已完成所有設定：

- Aspose.PDF for .NET：您需要在專案中安裝 Aspose.PDF for .NET 程式庫。
- [下載 .NET 版 Aspose.PDF](https://releases.aspose.com/pdf/net/)
- [免費試用](https://releases.aspose.com/)
- 開發環境：確保您安裝了 .NET 相容 IDE，例如 Visual Studio。
- 對 C# 的基本了解：雖然我們將分解所有內容，但對 C# 的基本了解將幫助您順利進行。
  
如果您還沒有 Aspose.PDF for .NET，您可以取得[臨時執照](https://purchase.aspose.com/temporary-license/)開始探索它的功能。

## 導入包

首先，您需要從 Aspose.PDF for .NET 匯入必要的命名空間。操作方法如下：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

這些套件提供了處理 PDF 文件和操作表格所需的基本類別和方法。

現在，讓我們將該過程分解為多個步驟，以將重複列新增至 PDF 文件。跟著走吧！

## 第 1 步：設定文檔目錄的路徑

在建立或操作任何文件之前，我們需要定義生成的 PDF 的保存路徑。在您的 C# 專案中，將目錄路徑設定為檔案所在位置：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
```

此路徑指向保存輸出 PDF 的目錄。代替`"YOUR DOCUMENT DIRECTORY"`與您機器上的實際路徑。

## 第 2 步：建立新的 PDF 文檔

首先，實例化一個新的`Document`目的。這將作為 PDF 中所有頁面和內容的容器。

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

在這裡，我們建立了一個新的 PDF 文件並向其中添加了一個空白頁。這`doc.Pages.Add()`方法將新頁面插入文件中。

## 第三步：實例化外表

接下來，我們創造一個外表。該表將跨越頁面的整個寬度，並用作其他表的容器，包括包含重複列的表。

```csharp
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;
```

我們已經設定了`ColumnWidths`屬性設定為“100%”，這意味著表格將延伸到整個頁面寬度。

## 第四步：建立內表

現在，讓我們建立內表，該表將具有重複列。這裡的關鍵屬性是`Broken`，這允許表在同一頁上繼續，並且`ColumnAdjustment`，它會自動調整列寬以適合內容。

```csharp
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

該內部表將嵌套在外部表內。

## 第 5 步：將表格新增至頁面

現在我們已經準備好了外表和內表，讓我們將它們添加到頁面中。此步驟確保表格包含在文件的結構中。

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
```

在這裡，我們添加了`outerTable`到頁面，然後在外表中，我們嵌套`mytable`。另外，我們設定`RepeatingColumnsCount`到 5，指定新增資料時應重複的列數。

## 第 6 步：新增標題行

現在是時候將標題添加到表中了。標題行提供資料上下文並幫助建立列。 

```csharp
Aspose.Pdf.Row row = mytable.Rows.Add();
row.Cells.Add("header 1");
row.Cells.Add("header 2");
row.Cells.Add("header 3");
row.Cells.Add("header 4");
row.Cells.Add("header 5");
row.Cells.Add("header 6");
row.Cells.Add("header 7");
row.Cells.Add("header 11");
row.Cells.Add("header 12");
row.Cells.Add("header 13");
row.Cells.Add("header 14");
row.Cells.Add("header 15");
row.Cells.Add("header 16");
row.Cells.Add("header 17");
```

此程式碼片段添加第一行（我們將用作標題），並使用包含“標題 1”、“標題 2”等文字的單元格填充它。

## 第7步：新增資料行

最後，我們可以在表中添加一些資料。此循環動態建立行並用內容填充單元格：

```csharp
for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
    Aspose.Pdf.Row row1 = mytable.Rows.Add();
    row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 4");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 5");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 6");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 7");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 11");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 12");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 13");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 14");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 15");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 16");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 17");
}
```

此循環迭代六次，添加行並用相應的列資料填充每個單元格（例如，「col 1, 1」、「col 2, 2」等）。

## 第 8 步：儲存文檔

新增所有行和列後，最後一步是將文件儲存到指定的檔案路徑。

```csharp
doc.Save(outFile);
```

您的文件現在已儲存為重複列！

## 結論

給你了！透過這些簡單的步驟，您可以使用 Aspose.PDF for .NET 建立具有重複列的 PDF 文件。透過利用巢狀表格的靈活性，您可以實現複雜的佈局，使您的 PDF 看起來專業且有條理。在您的下一個專案中嘗試一下，並探索 Aspose.PDF 的全部潛力來滿足您的 PDF 生成需求。

## 常見問題解答

### 什麼是 Aspose.PDF for .NET？
Aspose.PDF for .NET 是一個功能強大的程式庫，可讓開發人員以程式設計方式建立、編輯和管理 PDF 文件。

### 我可以動態調整重複列的數量嗎？
是的，您可以透過修改來更改重複列的數量`RepeatingColumnsCount`財產。

### 如何向 Aspose.PDF for .NET 申請許可證？
您可以按照以下方式從文件或串流套用許可證[文件](https://reference.aspose.com/pdf/net/).

### 是否可以將圖像新增至表格單元格？
是的，Aspose.PDF for .NET 支援將各種類型的內容（包括影像）新增至表格儲存格。

### 我可以進一步自訂表格佈局嗎？
絕對地！ Aspose.PDF 提供了廣泛的自訂表格樣式的功能，包括邊框、填充、對齊方式等。