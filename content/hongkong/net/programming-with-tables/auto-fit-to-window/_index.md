---
title: 自動適應視窗
linktitle: 自動適應視窗
second_title: Aspose.PDF for .NET API 參考
description: 在這份詳細的逐步指南中了解如何使用 Aspose.PDF for .NET 自動調整表格到視窗。非常適合在 PDF 中創建精美且合適的表格。
type: docs
weight: 50
url: /zh-hant/net/programming-with-tables/auto-fit-to-window/
---
## 介紹

處理 PDF 時，通常會處理表格，有時您需要這些表格完全適合頁面的寬度。在本教學中，我們將探討如何使用 Aspose.PDF for .NET 將表格自動調整到視窗。這可以使您的表格看起來整潔有序，防止列溢出或不均勻等問題。準備好學習了嗎？讓我們深入了解吧！

## 先決條件

在我們開始逐步指南之前，您需要準備一些東西：

1. Aspose.PDF for .NET 安裝在您的專案中。如果你還沒有得到它，你可以[在這裡下載](https://releases.aspose.com/pdf/net/)或探索他們的[免費試用版](https://releases.aspose.com/).
2. 對 .NET 程式設計有基本的了解。
3. Visual Studio 或系統上安裝的任何支援 .NET 的 IDE。

>  PS 不要忘記您需要許可證才能無限制地使用 Aspose.PDF。您可以購買一個[這裡](https://purchase.aspose.com/buy)或得到一個[臨時執照](https://purchase.aspose.com/temporary-license/)嘗試所有功能。

## 導入包

在深入研究程式碼之前，您需要匯入必要的名稱空間：

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

現在我們已經準備就緒，讓我們將其分解為簡單易懂的步驟，以了解如何使用 Aspose.PDF for .NET 將表格自動調整到視窗。

## 第 1 步：初始化文檔對象

首先，您需要建立一個 PDF 文件。將此文件視為一張空白紙，您將在其中新增頁面和表格。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//透過呼叫空建構函數來實例化 Pdf 對象
Document doc = new Document();
```
  
在這裡，我們使用以下命令建立一個新文檔`Document`來自 Aspose.PDF 的類別。這`dataDir`是完成後儲存 PDF 的位置。

## 步驟 2：新增頁面

PDF 文件需要頁面，對吧？讓我們添加一個。

```csharp
//在 Pdf 物件中建立一個部分（頁面）
Page sec1 = doc.Pages.Add();
```
  
我們使用以下命令為文件新增了一個新頁面`Pages.Add()`方法。您可以將此視為向文件中新增一個工作表，您將在其中放置表格。

## 步驟 3：建立並配置表

現在是時候創建一個表格並調整它以適合視窗了。

```csharp
//實例化一個表對象
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
//將表格新增至所需部分的段落集合中
sec1.Paragraphs.Add(tab1);
```
  
我們初始化了一個新的`Table`物件並將其新增至頁面的段落集合中。每個 PDF 頁面可以有不同的段落，這裡我們將表格視為一個段落。

## 第 4 步：定義列寬並自動適應窗口

接下來，我們設定列寬並確保表格自行調整以適應視窗。

```csharp
//設定表格的列寬
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
```
  
我們為表格設定了固定的列寬，但也新增了`ColumnAdjustment.AutoFitToWindow`，這可確保表格調整其大小以適合可用的視窗。

## 步驟 5：設定表格和儲存格的邊框和邊距

沒有邊框的表格通常難以閱讀。讓我們定義邊框和邊距以使其看起來整齊。

```csharp
//使用 BorderInfo 物件設定預設儲存格邊框
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

//使用另一個自訂的 BorderInfo 物件設定表格邊框
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);

//建立 MarginInfo 物件並設定其左、下、右、上邊距
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;

//將預設儲存格填入設定為 MarginInfo 對象
tab1.DefaultCellPadding = margin;
```
  
使用以下命令將邊框新增至表格和儲存格中`BorderInfo`類，您可以在其中定義厚度。設定邊距是為了提供單元格一些填充空間。

## 第 6 步：將行和單元格新增至表中

沒有內容的表格？這樣可不行啊！讓我們添加一些行和單元格。

```csharp
//在表格中建立行，然後在行中建立儲存格
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");

Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
```
  
我們創建兩行並向每行添加三個單元格。您將在此處輸入實際資料（可以是從字串到更複雜的元素的任何資料）。

## 步驟7：儲存文檔

一切設定完畢後，您將需要儲存新建立的 PDF 文件。

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
//儲存包含表格物件的更新文檔
doc.Save(dataDir);
```
  
這`doc.Save()`方法將PDF儲存到指定目錄。在這種情況下，文件將另存為`AutoFitToWindow_out.pdf`在您定義的目錄中。

## 結論

現在你就擁有了！您剛剛使用 Aspose.PDF for .NET 建立了一個自動適合視窗的表單。這不僅確保您的表格看起來專業且合適，而且還為您提供處理不同資料大小時的靈活性。無論您是建立報告、發票還是任何需要表格的文檔，此方法都是保持乾淨且可讀的佈局的好方法。

## 常見問題解答

### 我可以動態新增更多行嗎？  
是的，您可以使用以下命令繼續新增行`tab1.Rows.Add()`方法，根據內容動態地進行。

### 如果我不希望表格自動調整，如何調整表格？  
您可以手動設定`ColumnWidths`不使用`ColumnAdjustment.AutoFitToWindow`保持固定的表格寬度。

### 我可以在單元格內添加圖像或其他內容嗎？  
是的，Aspose.PDF 允許您在單元格內添加圖像、文本，甚至其他表格！

### 如果我需要更複雜的表格樣式怎麼辦？  
您可以使用背景顏色、文字對齊方式和字體設定等屬性進一步自訂表格和儲存格樣式。

### 是否可以將此表匯出為 PDF 以外的格式？  
絕對地！ Aspose.PDF 支援匯出為各種格式，如 HTML、DOCX 等。