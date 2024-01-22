---
title: 在表格單元格中新增圖像
linktitle: 在表格單元格中新增圖像
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 在表格儲存格中新增影像，這是精確操作 PDF 文件中影像的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-tables/add-image-in-a-table-cell/
---
在本教學中，我們將引導您完成使用 Aspose.PDF for .NET 將影像新增至表格儲存格的過程。提供的 C# 原始程式碼演示瞭如何實現此功能。透過執行下面列出的步驟，您將能夠有效地將影像合併到表格儲存格中。

在我們深入研究程式碼之前，請確保您已在專案中安裝並引用了 Aspose.PDF for .NET 程式庫。

## 第 1 步：設定文檔

首先，我們需要建立一個新的實例`Document`來自 Aspose.Pdf 命名空間的類別。此類代表 PDF 文件。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//實例化一個文檔對象
Document pdfDocument = new Document();
```

## 第 2 步：建立頁面

接下來，我們需要在 PDF 文件中新增頁面。頁面充當表格和其他元素的容器。

```csharp
//在 pdf 文件中建立頁面
Page sec1 = pdfDocument.Pages.Add();
```

## 第 3 步：新增表

在此步驟中，我們將透過實例化來建立一個表`Table`來自 Aspose.Pdf 命名空間的類別。

```csharp
//實例化一個表對象
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## 步驟 4：設定預設儲存格邊框

為了確保一致性，我們可以使用以下命令設定預設單元格邊框`DefaultCellBorder`表的屬性`BorderInfo`目的。

```csharp
//使用 BorderInfo 物件設定預設儲存格邊框
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## 第 5 步：設定列寬

要定義表格中每列的寬度，我們可以設定`ColumnWidths`財產。將寬度指定為具有空格分隔值的字串。

```csharp
//設定表格的列寬
tab1.ColumnWidths = "100 100 120";
```

## 步驟 6：將影像新增至表格儲存格

現在是令人興奮的部分，將圖像添加到表格單元格。為此，我們將遵循以下子步驟：

## 步驟 6.1：建立影像對象

建立一個實例`Image`來自 Aspose.Pdf 命名空間的類別。設定`File`屬性到要新增的圖像檔案的路徑。

```csharp
//建立影像對象
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
```

## 步驟 6.2：建立行和儲存格

要將圖像新增到表格中，我們首先需要建立一行和必要的儲存格。

```csharp
//在表中建立一行
Aspose.Pdf.Row row1 = tab1.Rows.Add();

//將文字儲存格新增至行中
row1.Cells.Add("Sample text in cell");

//新增儲存影像的儲存格
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
```

## 步驟 6.3：將影像新增至表格儲存格

最後，我們可以透過將圖像新增為單元格內的段落來將圖像新增至表格單元格。

```csharp
//將圖像新增至表格單元格
cell2.Paragraphs.Add(img);
```

## 步驟 6.4：新增額外的儲存格

新增圖像單元格後，如果需要，我們可以向該行添加更多單元格。

```csharp
//將另一個儲存格新增至該行
row1.Cells.Add("Previous cell with image");

//調整第三個單元格的垂直對齊方式
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
```

## 步驟7：儲存文檔

最後，我們可以使用以下命令將修改後的文件儲存到指定位置`Save`方法。

```csharp
//儲存文件
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

恭喜！您已成功學習如何使用 Aspose.PDF for .NET 將影像新增至表格儲存格。請隨意探索更多自訂選項並將此功能整合到您的專案中。

### 使用 Aspose.PDF for .NET 在表格單元格中新增圖像的範例原始程式碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//實例化一個文檔對象
Document pdfDocument = new Document();
//在 pdf 文件中建立頁面
Page sec1 = pdfDocument.Pages.Add();
//實例化一個表對象
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
//在所需頁面的段落集合中新增表格
sec1.Paragraphs.Add(tab1);
//使用 BorderInfo 物件設定預設儲存格邊框
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
//設定表格的列寬
tab1.ColumnWidths = "100 100 120";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
//在表格中建立行，然後在行中建立儲存格
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Sample text in cell");
//新增儲存影像的儲存格
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
//將圖像新增至表格單元格
cell2.Paragraphs.Add(img);
row1.Cells.Add("Previous cell with image");
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
//儲存文件
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

## 結論

在本教學中，我們介紹如何使用 Aspose.PDF for .NET 將影像新增至表格儲存格的逐步指南。我們首先設定文件、建立頁面並新增表格。然後，我們設定預設的儲存格邊框和列寬。我們示範如何將影像新增至表格儲存格並調整儲存格的垂直對齊方式。最後，我們儲存修改後的文件。透過執行以下步驟，您可以使用表格單元格中的影像有效地增強 PDF 文件。

### 常見問題解答

#### Q：我可以使用 Aspose.PDF for .NET 將多個影像新增至同一表格內的不同儲存格嗎？

答：是的，您可以使用 Aspose.PDF for .NET 將多個影像新增至同一表格內的不同儲存格。對於要添加到表中的每個圖像，只需遵循教程中演示的相同過程即可。

#### Q：我可以自訂表格儲存格中的圖像大小和位置嗎？

答：是的，您可以透過調整表格單元格的屬性來自訂圖像大小和位置。`Image`目的。您可以設定影像的寬度和高度，以及儲存格內的對齊方式。

#### Q：我可以將圖像新增到具有動態行數和列數的表格中嗎？

答：是的，您可以將圖像新增到具有動態行數和列數的表格中。 Aspose.PDF for .NET 提供了建立不同尺寸表格的彈性。您可以根據需要添加行和單元格，然後相應地將圖像添加到特定單元格。

#### Q：Aspose.PDF for .NET 支援哪些影像格式來將影像新增至表格儲存格？

答：Aspose.PDF for .NET 支援多種影像格式，包括 JPEG、PNG、GIF、BMP 和 TIFF。您可以使用任何這些格式的圖像將它們新增至表格單元格。

#### Q：我可以將圖像新增到現有 PDF 文件的表格中嗎？

答：是的，您可以使用 Aspose.PDF for .NET 將影像新增至現有 PDF 文件的表格中。只需載入現有文件並按照教程中演示的相同步驟將圖像添加到表中即可。