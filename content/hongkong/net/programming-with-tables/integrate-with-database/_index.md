---
title: 與 PDF 文件中的資料庫集成
linktitle: 與 PDF 文件中的資料庫集成
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 將資料庫中的資料嵌入 PDF 檔案中。
type: docs
weight: 120
url: /zh-hant/net/programming-with-tables/integrate-with-database/
---
在本教學中，我們將學習如何使用 Aspose.PDF for .NET 將資料庫中的資料嵌入 PDF 檔案中。我們將一步步解釋C#的原始碼。在本教學結束時，您將了解如何將資料庫中的表格資料匯入 PDF 文件。開始吧！

## 第一步：建構環境
請確定您已使用 Aspose.PDF for .NET 配置 C# 開發環境。新增對庫的引用並導入必要的命名空間。

## 第2步：建立資料表
我們建立一個 DataTable 實例來表示我們想要嵌入 PDF 文件中的資料。在這個範例中，我們建立一個包含三個欄位的 DataTable：Employee_ID、Employee_Name 和 Gender。我們也使用虛擬資料向 DataTable 新增兩行。

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));

DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);

dr = dt. NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
```

## 步驟 3：建立 PDF 文件和表格
我們建立一個 Document 實例並在該文件中新增一個頁面。接下來，我們建立一個 Table 實例來表示 PDF 文件中的表格。我們定義表格列寬和邊框樣式。

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "40 100 100 100";
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## 步驟4：將DataTable中的資料匯入到表中
我們使用 ImportDataTable 方法將 DataTable 中的資料匯入 PDF 文件中的表格。

```csharp
table.ImportDataTable(dt, true, 0, 1, 3, 3);
```

## 步驟 5：將表格新增至文件中
我們將表格新增到文件頁面的段落集合中。

```csharp
doc.Pages[1].Paragraphs.Add(table);
```

## 第 6 步：儲存文檔
我們使用嵌入式資料庫中的資料儲存 PDF 文件。

```csharp
doc.Save(dataDir + "DataIntegrated_out.pdf");
```

恭喜！現在您知道如何使用 Aspose.PDF for .NET 將資料庫資料嵌入 PDF 文件中。

### 使用 Aspose.PDF for .NET 與資料庫整合的範例原始碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));
//以程式設計方式將 2 行加入到 DataTable 物件中
DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
//建立文件實例
Document doc = new Document();
doc.Pages.Add();
//初始化表的新實例
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
//設定表格的列寬
table.ColumnWidths = "40 100 100 100";
//將表格邊框顏色設定為淺灰色
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
//設定表格單元格的邊框
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.ImportDataTable(dt, true, 0, 1, 3, 3);

//將表格物件新增至輸入文件的第一頁
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "DataIntegrated_out.pdf";
//儲存包含表格物件的更新文檔
doc.Save(dataDir);

Console.WriteLine("\nDatabase integrated successfully.\nFile saved at " + dataDir);
```

## 結論
在本教學中，我們學習如何使用 Aspose.PDF for .NET 將資料庫中的資料嵌入 PDF 文件中。您可以使用此逐步指南從您自己的資料庫匯入資料並將其顯示在 PDF 文件中。進一步探索 Aspose.PDF 文檔，發現這個強大的庫提供的其他功能和可能性。

### 與 PDF 文件中的資料庫整合的常見問題解答

#### Q：我可以將 Aspose.PDF for .NET 與不同的資料庫類型（例如 MySQL、SQL Server 或 Oracle）一起使用嗎？

答：是的，您可以將 Aspose.PDF for .NET 與不同的資料庫類型（如 MySQL、SQL Server、Oracle 等）一起使用。 Aspose.PDF for .NET 提供了從各種資料來源（包括資料庫、XML 檔案等）讀取資料的功能。您可以從所需的資料庫類型中檢索資料並將其填入 DataTable 或與 Aspose.PDF for .NET 相容的任何其他資料結構中。

#### Q：如何自訂 PDF 文件中表格的外觀？

答：您可以使用 Aspose.PDF for .NET 程式庫提供的各種屬性來自訂 PDF 文件中表格的外觀。例如，您可以為表格及其儲存格設定不同的邊框樣式、背景顏色、字型樣式和對齊方式。有關自訂表格外觀的更多詳細信息，請參閱 Aspose.PDF for .NET 文件。

#### Q：從資料庫匯入的資料是否可以新增超連結或互動元素？

答：是的，您可以為從資料庫匯入的資料新增超連結或其他互動元素。 Aspose.PDF for .NET 支援在 PDF 文件中新增超連結、書籤和其他互動元素。您可以在將資料表中的內容匯入表中之前對其進行操作，並包含超連結或其他互動功能。

#### 問：如果表格超過一定行數，我可以對表格進行分頁嗎？

答：是的，如果表格超過一定的行數，您可以對錶進行分頁。為了實現這一點，您可以使用`IsInNewPage`Row 物件的屬性指示新頁面應在特定行之後開始。您可以計算每頁顯示的行數並設定`IsInNewPage`相應的財產。

#### Q：如何將嵌入資料庫資料的 PDF 文件匯出為不同的文件格式，例如 DOCX 或 XLSX？

答：Aspose.PDF for .NET 可讓您將 PDF 文件轉換為各種其他文件格式，包括 DOCX (Microsoft Word) 和 XLSX (Microsoft Excel)。您可以將 Aspose.PDF for .NET 程式庫與其他 Aspose 程式庫（例如 Aspose.Words 和 Aspose.Cells）結合使用來實現此目的。首先，儲存嵌入資料庫資料的 PDF 文檔，然後使用相應的 Aspose 庫將其轉換為您所需的文件格式。