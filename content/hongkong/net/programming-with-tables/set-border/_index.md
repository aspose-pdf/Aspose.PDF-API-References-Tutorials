---
title: 將 PDF 中的邊框設定為表格
linktitle: 將 PDF 中的邊框設定為表格
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 將 PDF 中的邊框設定為表格。
type: docs
weight: 200
url: /zh-hant/net/programming-with-tables/set-border/
---
在本教學中，我們將逐步指導您使用 Aspose.PDF for .NET 在 PDF 文件的表格中設定邊框。我們將解釋提供的 C# 原始程式碼並向您展示如何實現它。

## 第 1 步：實例化 Document 對象
首先，我們將實例化一個 Document 物件：

```csharp
Document doc = new Document();
```

## 步驟 2：為 PDF 文件新增頁面
接下來，我們將在 PDF 文件中新增頁面：

```csharp
Page page = doc.Pages.Add();
```

## 第 3 步：建立 BorderInfo 對象
我們現在將建立一個 BorderInfo 物件來定義表格的邊框：

```csharp
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
```

## 步驟 4：指定頂部和底部邊框
我們將指定頂部和底部邊框為雙邊框：

```csharp
border.Top.IsDoubled = true;
border.Bottom.IsDoubled = true;
```

## 第 5 步：實例化 Table 對象
現在讓我們實例化一個 Table 物件：

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## 步驟 6：指定列寬
我們將指定表格列的寬度：

```csharp
table. ColumnWidths = "100";
```

## 第 7 步：建立行對象
我們將創建一個 Row 物件：

```csharp
Aspose.Pdf.Row row = table.Rows.Add();
```

## 步驟 8：將儲存格新增至行中
接下來，我們將向該行新增一個儲存格：

```csharp
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
```

## 步驟9：設定單元格邊框
我們將定義單元格的邊框（雙邊框）：

```csharp
cell. Border = border;
```

## 第10步：將表格加入到頁面
現在讓我們將表格新增到文件頁面：

```csharp
page.Paragraphs.Add(table);
```

## 第11步：儲存PDF文檔
最後，我們儲存PDF文檔：

```csharp
dataDir = dataDir + "TableBorderTest_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

### 使用 Aspose.PDF for .NET 設定邊框的範例原始碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//實例化文檔對象
Document doc = new Document();
//將頁面新增至 PDF 文檔
Page page = doc.Pages.Add();
//建立BorderInfo對象
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
//指定頂部邊框為雙邊框
border.Top.IsDoubled = true;
//指定底部邊框為雙邊框
border.Bottom.IsDoubled = true;
//實例化表對象
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
//指定列寬資訊
table.ColumnWidths = "100";
//建立行對象
Aspose.Pdf.Row row = table.Rows.Add();
//將表格儲存格新增至行的儲存格集合中
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
//設定單元格物件的邊框（雙邊框）
cell.Border = border;
//將表格加入到頁面的段落集合中
page.Paragraphs.Add(table);
dataDir = dataDir + "TableBorderTest_out.pdf";
//儲存 PDF 文件
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

## 結論
恭喜！現在您已經了解如何使用 Aspose.PDF for .NET 在 PDF 文件的表格中設定邊框。本逐步指南向您展示如何建立文件、新增頁面、設定表格邊框以及儲存 PDF 文件。現在您可以將這些知識應用到您自己的專案中。

### 常見問題解答

#### Q：我可以為表格的頂部和底部邊框設定不同的邊框樣式（例如虛線或點線）嗎？

 A：是的，您可以透過修改表格的上下邊框來設定不同的邊框樣式`border.Top.Style`和`border.Bottom.Style`提供的 C# 原始碼中的屬性。 Aspose.PDF for .NET 可讓您選擇各種邊框樣式，包括實線、虛線、點線、雙線等。

#### Q：如何設定表格邊框的顏色？

 A：可以透過修改表格邊框的顏色來設定`border.Color`C# 原始碼中的屬性。只需提供所需的顏色，例如`Aspose.Pdf.Color.Red`或任何其他有效的顏色表示，以自訂邊框顏色。

#### Q：是否可以將邊框套用到具有不同設定（例如，不同顏色或邊框樣式）的表格內的各個儲存格？

答：是的，您可以透過配置`cell.Border`每個單元格的屬性。這允許您根據您的要求擁有特定於單元格的邊框樣式和顏色。

#### Q：我可以刪除表格特定兩側的邊框（例如，左邊框和右邊框）嗎？

答：是的，您可以透過修改`border.Left`, `border.Right`, `border.Top`， 和`border.Bottom`C# 原始碼中的屬性。將這些屬性設為`null`將刪除表格對應邊的邊框。

#### Q：如何調整表格邊框的粗細？

 A：可以透過修改表格邊框的粗細來調整`border.Width`C# 原始碼中的屬性。只需設定所需的邊框寬度（以磅為單位）即可達到所需的厚度。