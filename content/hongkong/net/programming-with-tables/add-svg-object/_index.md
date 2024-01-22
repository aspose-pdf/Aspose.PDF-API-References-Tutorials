---
title: 在 PDF 檔案中新增 SVG 對象
linktitle: 在 PDF 檔案中新增 SVG 對象
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 在 PDF 檔案中輕鬆新增 SVG 物件。
type: docs
weight: 30
url: /zh-hant/net/programming-with-tables/add-svg-object/
---
在本教學中，我們將學習如何使用 Aspose.PDF for .NET 函式庫在 PDF 檔案中新增 SVG 物件。 SVG（可縮放向量圖形）是一種流行的向量圖形格式，可以輕鬆縮放而不損失品質。使用 Aspose.PDF，您可以以程式設計方式將 SVG 物件新增至 PDF 文件。

## 要求

在我們開始之前，請確保您具備以下條件：

- 安裝了 Visual Studio
- 安裝了 Aspose.PDF for .NET 函式庫

## 第 1 步：設定環境

首先，我們透過在 Visual Studio 中建立一個新的 C# 專案來設定環境。開啟 Visual Studio 並依照下列步驟操作：

1. 按一下「檔案」>「新建」>「專案」建立一個新專案。
2. 根據您的設置，選擇「控制台應用程式 (.NET Framework)」或「控制台應用程式 (.NET Core)」範本。
3. 為您的專案選擇合適的名稱和位置，然後按一下「建立」。

## 第 2 步：建立文件和圖像對象

在此步驟中，我們將為 PDF 文件和 SVG 影像建立必要的物件。開啟專案的 C# 檔案並新增以下程式碼：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//即時文檔對象
Document doc = new Document();
//建立圖像實例
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```

## 步驟 3：設定影像屬性

接下來，我們將為 SVG 圖像設定屬性。我們將指定檔案類型為 SVG、SVG 檔案的路徑以及影像的尺寸。在上一步之後加入以下程式碼：

```csharp
//將圖像類型設定為 SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
//來源檔案路徑
img.File = dataDir + "SVGToPDF.svg";
//設定圖像實例的寬度
img. FixWidth = 50;
//設定圖像實例的高度
img.FixHeight = 50;
```

## 第 4 步：建立並配置表

現在，讓我們建立一個表格物件並設定列寬。我們將建立一個包含兩列的表，每列的寬度為 100 個單位。新增以下程式碼：

```csharp
//建立實例表
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
//設定表格單元格的寬度
table. ColumnWidths = "100 100";
```

## 第 5 步：將儲存格新增至表格中

在此步驟中，我們將向表格新增行和儲存格。每行代表表中的一個水平行，單元格將會新增到這些行中。新增以下程式碼：

```csharp
//建立行物件並將其新增至表實例
Aspose.Pdf.Row row = table.Rows.Add();
//建立單元格物件並將其新增至行實例
Aspose.Pdf.Cell cell = row.Cells.Add();
```

## 第 6 步：為單元格新增文字和圖像

接下來，我們將文字和 SVG 圖像加入到表格的單元格中。我們將文字「First cell」新增到第一個單元格，將 SVG 圖像新增至第二個單元格。新增以下程式碼：

```csharp
//將文字片段加入到單元格物件的段落集合中
cell.Paragraphs.Add(new TextFragment("First cell"));
//將另一個儲存格新增至行對象
cell = row. Cells. Add();
//將 SVG 圖像新增至最近新增的單元格實例的段落集合中
cell.Paragraphs.Add(img);
```

## 步驟 7：建立頁面並將其新增至文件中

現在，讓我們建立一個頁面物件並將其新增到文件中。該表格將會加入到頁面的段落集合中。新增以下程式碼：

```csharp
//建立頁面物件並將其新增至文件實例的頁面集合中
Page page = doc.Pages.Add();
//將表格加入到頁面物件的段落集合中
page.Paragraphs.Add(table);
```

## 第 8 步：儲存 PDF 文件

最後，我們將PDF文件儲存到指定位置。新增以下程式碼：

```csharp
dataDir = dataDir + "AddSVGObject_out.pdf";
//儲存 PDF 文件
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);
```

### 使用 Aspose.PDF for .NET 新增 SVG 物件的範例原始碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//實例化文檔對象
Document doc = new Document();
//建立圖像實例
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
//將圖像類型設定為 SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
//來源檔案路徑
img.File = dataDir + "SVGToPDF.svg";
//設定圖像實例的寬度
img.FixWidth = 50;
//設定圖像實例的高度
img.FixHeight = 50;
//建立表格實例
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
//設定表格單元格的寬度
table.ColumnWidths = "100 100";
//建立行物件並將其新增至表實例
Aspose.Pdf.Row row = table.Rows.Add();
//建立單元格物件並將其新增至行實例
Aspose.Pdf.Cell cell = row.Cells.Add();
//將文字片段加入到單元格物件的段落集合中
cell.Paragraphs.Add(new TextFragment("First cell"));
//將另一個儲存格新增至行對象
cell = row.Cells.Add();
//將 SVG 圖像新增至最近新增的單元格實例的段落集合中
cell.Paragraphs.Add(img);
//建立頁面物件並將其新增至文件實例的頁面集合中
Page page = doc.Pages.Add();
//將表格加入到頁面物件的段落集合中
page.Paragraphs.Add(table);

dataDir = dataDir + "AddSVGObject_out.pdf";
//儲存 PDF 文件
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);            
```

## 結論

在本教學中，我們學習如何使用 Aspose.PDF for .NET 函式庫將 SVG 物件加入 PDF 檔案中。我們介紹了創建文件、設定環境、將 SVG 圖像添加到表格單元格以及保存 PDF 文件的逐步過程。現在，您可以透過程式設計方式將 SVG 物件合併到 PDF 文件中。

### 在 PDF 檔案中新增 SVG 物件的常見問題解答

#### Q：我可以為 PDF 文件新增多個 SVG 物件嗎？

答：是的，您可以將多個 SVG 物件新增至 PDF 文件中。只需建立並配置額外的`Aspose.Pdf.Image`您要新增的每個 SVG 圖像的實例，然後將它們新增至 PDF 文件中所需的表格單元或段落。

#### Q：如何調整表格單元格中 SVG 影像的大小和位置？

 A：要調整SVG影像在表格儲存格中的大小和位置，可以修改`FixWidth`和`FixHeight`的屬性`Aspose.Pdf.Image`實例。您也可以使用其他屬性，例如`HorizontalAlignment`和`VerticalAlignment`的表格單元格來控制定位。

#### Q：是否可以在同一表格儲存格中的 SVG 圖像旁邊新增文字？

答：是的，可以在同一表格儲存格中的 SVG 圖像旁邊新增文字。您可以使用`cell.Paragraphs.Add(new TextFragment("Your Text Here"));`方法將文字與 SVG 圖像一起添加到單元格。

#### Q：我可以為 SVG 圖像添加超連結嗎？

答：是的，您可以使用以下命令向 SVG 圖像添加超連結：`Hyperlink`的財產`Aspose.Pdf.Image`實例。設定超連結 URL 或操作以使圖像可點擊。

#### Q：Aspose.PDF for .NET 是否與 .NET Core 3.1 或更高版本相容？

答：是的，Aspose.PDF for .NET 與 .NET Core 3.1 及更高版本相容。您可以在 .NET Framework 和 .NET Core 應用程式中使用它。