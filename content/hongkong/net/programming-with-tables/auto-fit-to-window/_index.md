---
title: 自動適應視窗
linktitle: 自動適應視窗
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 並在 PDF 生成中實現自動適應視窗的逐步指南。
type: docs
weight: 50
url: /zh-hant/net/programming-with-tables/auto-fit-to-window/
---
以下文章逐步指南介紹如何使用提供的 C# 原始程式碼透過適用於 .NET 的 Aspose.PDF 庫實現自動適應視窗功能。自動適應視窗功能可讓您產生佈局適合查看視窗的 PDF 檔案。當您希望 PDF 文件自動調整為使用者使用的 PDF 閱讀器視窗的大小時，此功能特別有用。

## 第 1 步：設定環境

在開始之前，您需要在電腦上安裝適用於 .NET 的 Aspose.PDF 庫。還要確保將必要的命名空間匯入到您的專案中。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：建立 PDF 文檔

首先，您需要建立一個`Document`物件透過呼叫其預設建構函數。

```csharp
Document doc = new Document();
```

接下來，在`Pdf`目的。

```csharp
Page sec1 = doc.Pages.Add();
```

## 步驟 3：為文件新增表格

在此步驟中，我們將向 PDF 文件新增一個表格。首先創建一個`Table`目的。

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

接下來，將該表新增到該部分的段落集合中。

```csharp
sec1.Paragraphs.Add(tab1);
```

##  第 4 步：自訂表格外觀

您可以透過設定儲存格邊框和邊距等屬性來自訂表格的外觀。

```csharp
tab1. ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);

Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin.Right = 5f;
margin. Bottom = 5f;

tab1. DefaultCellPadding = margin;
```

##  步驟 4：在表格中新增行和儲存格

現在讓我們在表格中新增行和儲存格。首先建立一行並向該行新增單元格。

```csharp
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");

Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
```

## 第 5 步：儲存文檔

最後，指定輸出檔案路徑並儲存文件。

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
doc.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 自動適應視窗的範例原始碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//透過呼叫空建構函數來實例化 Pdf 對象
Document doc = new Document();
//在 Pdf 物件中建立部分
Page sec1 = doc.Pages.Add();

//實例化一個表對象
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
//將表格新增至所需部分的段落集合中
sec1.Paragraphs.Add(tab1);

//設定表格的列寬
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

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

//在表格中建立行，然後在行中建立儲存格
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");

dataDir = dataDir + "AutoFitToWindow_out.pdf";
//儲存包含表格物件的更新文檔
doc.Save(dataDir);
```

## 結論

在本教學中，我們學習如何使用 Aspose.PDF for .NET 產生具有自動適應視窗功能的 PDF 檔案。當您希望 PDF 文件自動調整為檢視視窗的大小時，此功能非常有用。 Aspose.PDF for .NET 提供了許多其他強大的功能來產生和操作 PDF 檔案。我鼓勵您進一步探索這個庫以發現它的所有功能。

### 常見問題解答

#### Q：PDF 生成中「自動適應視窗」功能的用途是什麼？

答：PDF 產生中的自動適應視窗功能可確保 PDF 文件的佈局會自動調整為使用者使用的 PDF 閱讀器視窗的大小。這樣可以實現更好的觀看效果，並確保內容完全適合可用的觀看區域。

#### Q：我可以自訂表格的外觀，例如字體大小和顏色嗎？

答：是的，您可以使用 Aspose.PDF for .NET 自訂 PDF 文件中表格的外觀。提供的程式碼片段示範如何設定單元格邊框、邊距和列寬等屬性。您可以進一步自訂表格及其內容的字體大小、顏色和其他樣式方面。

#### Q：如何將 Aspose.PDF for .NET 整合到我的 C# 專案中？

答：要在 C# 專案中使用 Aspose.PDF for .NET，您需要先在電腦上安裝 Aspose.PDF for .NET 程式庫。然後，您可以在 C# 專案中新增對該庫的參考。最後，導入必要的命名空間以存取 Aspose.PDF for .NET 提供的類別和方法。

#### Q：Aspose.PDF for .NET 與 .NET Core 應用程式相容嗎？

答：是的，Aspose.PDF for .NET 與 .NET Core 應用程式相容。它支援各種.NET平台，包括.NET Framework、.NET Core和.NET 5.0+。

#### Q：我可以在 PDF 文件中新增更多表格嗎？

答：是的，您可以按照程式碼片段中示範的類似步驟將多個表格新增到 PDF 文件中。只需建立新的實例`Aspose.Pdf.Table`類別並將它們新增至 PDF 文件的不同部分或頁面。