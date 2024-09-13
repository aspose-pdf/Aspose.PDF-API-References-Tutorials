---
title: Thêm cột lặp lại trong tài liệu PDF
linktitle: Thêm cột lặp lại trong tài liệu PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách thêm cột lặp lại vào tài liệu PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 20
url: /vi/net/programming-with-tables/add-repeating-column/
---
Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách thêm một cột lặp lại trong tài liệu PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích mã nguồn bằng C# từng bước. Vào cuối hướng dẫn này, bạn sẽ biết cách tạo một bảng có cột lặp lại trong tài liệu PDF. Hãy bắt đầu nào!

## Bước 1: Thiết lập môi trường
Trước tiên, hãy đảm bảo bạn đã thiết lập môi trường phát triển C# của mình với Aspose.PDF cho .NET. Thêm tham chiếu đến thư viện và nhập các không gian tên cần thiết.

## Bước 2: Tạo tài liệu PDF
Ở bước này, chúng ta sẽ tạo một tài liệu PDF mới.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

Chúng tôi đã tạo một tài liệu PDF trống để có thể thêm nội dung.

## Bước 3: Tạo bảng
Trong bước này chúng ta tạo một bảng chính (`outerTable`) và một bảng lồng nhau (`mytable`) sẽ được lặp lại trong cột.

```csharp
Table outerTable = new Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

Table mytable = new Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

Chúng tôi đã chỉ định các thuộc tính của bảng như chiều rộng cột và chế độ ngắt bảng lồng nhau.

## Bước 4: Thêm bảng vào tài liệu
Bây giờ chúng ta thêm các bảng đã tạo vào tài liệu PDF.

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);
```

Đầu tiên chúng ta thêm bảng chính (`outerTable`) vào tài liệu PDF. Tiếp theo, chúng ta thêm bảng lồng nhau (`mytable` ) như một đoạn văn trong một ô trong bảng chính. Chúng tôi cũng chỉ định số lượng cột lặp lại cho`mytable` (trong ví dụ này là 5 cột).

## Bước 5: Thêm tiêu đề và dòng
Bây giờ chúng ta thêm tiêu đề và hàng vào bảng.

```csharp
Row headerRow = mytable.Rows.Add();
headerRow.Cells.Add("header 1");
headerRow.Cells.Add("header 2");
headerRow.Cells.Add("header 3");
// ...
//Thêm các tiêu đề khác ở đây

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
     Row row1 = mytable.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
     // ...
     // Thêm các cột khác vào đây
}
```

Đầu tiên chúng ta thêm tiêu đề vào hàng đầu tiên của bảng (`headerRow`). Sau đó, chúng ta thêm các hàng dữ liệu từ một vòng lặp. Trong ví dụ này, chúng ta thêm 6 hàng dữ liệu.

## Bước 6: Lưu tài liệu PDF
Cuối cùng, chúng ta lưu tài liệu PDF vào tập tin đã chỉ định.

```csharp
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
doc.Save(outFile);
```

Hãy đảm bảo chỉ định đúng thư mục và tên tệp để lưu tệp PDF đầu ra.

### Mã nguồn ví dụ để thêm cột lặp lại bằng Aspose.PDF cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

string outFile = dataDir + "AddRepeatingColumn_out.pdf";
// Tạo một tài liệu mới
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();

// Tạo một bảng bên ngoài chiếm toàn bộ trang
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

// Khởi tạo một đối tượng bảng sẽ được lồng bên trong outerTable sẽ ngắt bên trong cùng một trang
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;

// Thêm outerTable vào các đoạn văn trang
// Thêm mytable vào outerTable
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);

// Thêm hàng tiêu đề
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

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)

{
	// Tạo các hàng trong bảng và sau đó tạo các ô trong các hàng
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
doc.Save(outFile);
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách thêm một cột lặp lại trong tài liệu PDF bằng Aspose.PDF cho .NET. Bạn có thể sử dụng hướng dẫn từng bước này để tạo các bảng có các cột lặp lại trong các dự án C# của riêng bạn.

### Câu hỏi thường gặp về việc thêm cột lặp lại vào tài liệu PDF

#### H: Tôi có thể tùy chỉnh số lượng cột lặp lại trong bảng lồng nhau không?

 A: Có, bạn có thể tùy chỉnh số lượng cột lặp lại trong bảng lồng nhau. Trong ví dụ được cung cấp, chúng tôi thiết lập`mytable.RepeatingColumnsCount = 5;`, nghĩa là sẽ có 5 cột được lặp lại. Bạn có thể thay đổi giá trị này thành bất kỳ số nào bạn muốn.

#### H: Có thể thêm nhiều hàng vào bảng lồng nhau một cách động không?

A: Có, bạn có thể thêm động nhiều hàng hơn vào bảng lồng nhau theo cùng cách như trong hướng dẫn. Bạn có thể sử dụng vòng lặp hoặc bất kỳ logic nào khác để thêm hàng dựa trên dữ liệu của bạn.

#### H: Tôi có thể áp dụng kiểu và định dạng cho bảng và các ô trong bảng không?

A: Có, bạn có thể áp dụng kiểu và định dạng cho bảng và các ô của bảng bằng Aspose.PDF cho .NET. Thư viện cung cấp nhiều thuộc tính và phương pháp khác nhau để tùy chỉnh giao diện của bảng và nội dung của bảng.

#### H: Aspose.PDF cho .NET có tương thích với .NET Core không?

A: Có, Aspose.PDF cho .NET tương thích với .NET Core. Bạn có thể sử dụng nó trong cả ứng dụng .NET Framework và .NET Core.

#### H: Tôi có thể sử dụng cách này để thêm các cột lặp lại vào tài liệu PDF hiện có không?

A: Có, bạn có thể sử dụng cách tiếp cận này để thêm các cột lặp lại vào tài liệu PDF hiện có. Chỉ cần tải tài liệu hiện có bằng Aspose.PDF cho .NET và làm theo các bước tương tự để tạo và thêm cột lặp lại.