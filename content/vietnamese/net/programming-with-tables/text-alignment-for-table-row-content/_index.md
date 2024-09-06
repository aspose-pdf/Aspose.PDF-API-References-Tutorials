---
title: Căn chỉnh văn bản cho nội dung hàng bảng
linktitle: Căn chỉnh văn bản cho nội dung hàng bảng
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách căn chỉnh nội dung hàng trong bảng PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 210
url: /vi/net/programming-with-tables/text-alignment-for-table-row-content/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước để căn chỉnh nội dung của một hàng trong bảng của tài liệu PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích mã nguồn C# được cung cấp và chỉ cho bạn cách triển khai.

## Bước 1: Tạo tài liệu PDF
Đầu tiên, chúng ta sẽ tạo tài liệu PDF:

```csharp
var dataDir = "YOUR DOCUMENTS DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Bước 2: Khởi tạo bảng
Tiếp theo, chúng ta sẽ khởi tạo bảng:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Bước 3: Thiết lập màu viền bảng
Chúng ta sẽ cấu hình màu đường viền bảng:

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Bước 4: Cấu hình đường viền ô của bảng
Chúng ta sẽ cấu hình đường viền ô của bảng:

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Bước 5: Lặp lại để thêm 10 hàng vào bảng
Bây giờ chúng ta sẽ sử dụng vòng lặp để thêm 10 hàng vào bảng:

```csharp
for (int row_count = 0; row_count < 10; row_count++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row.VerticalAlignment = VerticalAlignment.Center;

     row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
     row.Cells.Add("Column("+row_count+",2)");
     row.Cells.Add("Column("+row_count+",3)");
}
```

## Bước 6: Cấu hình căn chỉnh đường thẳng đứng
Chúng ta sẽ cấu hình căn chỉnh theo chiều dọc của các hàng trong bảng:

```csharp
row.VerticalAlignment = VerticalAlignment.Center;
```

## Bước 7: Thêm nội dung vào các ô hàng
Chúng ta sẽ thêm nội dung vào các ô hàng:

```csharp
row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
row.Cells.Add("Column("+row_count+",2)");
row.Cells.Add("Column("+row_count+",3)");
```

## Bước 8: Thêm bảng vào trang tài liệu
Bây giờ chúng ta hãy thêm bảng vào trang tài liệu:

```csharp
Page tocPage = doc.Pages.Add();
tocPage.Paragraphs.Add(table);
```

## Bước 9: Lưu tài liệu PDF
Cuối cùng, chúng ta sẽ lưu tài liệu PDF:

```csharp
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

### Mã nguồn ví dụ cho Căn chỉnh văn bản cho nội dung hàng bảng bằng Aspose.PDF cho .NET

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

// Tạo tài liệu PDF
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Khởi tạo một phiên bản mới của Bảng
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Đặt màu viền bảng là LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// thiết lập đường viền cho các ô của bảng
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// tạo một vòng lặp để thêm 10 hàng
for (int row_count = 0; row_count < 10; row_count++)
{
	// thêm hàng vào bảng
	Aspose.Pdf.Row row = table.Rows.Add();
	row.VerticalAlignment = VerticalAlignment.Center;

	row.Cells.Add("Column (" + row_count + ", 1)" + DateTime.Now.Ticks);
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
Page tocPage = doc.Pages.Add();
// Thêm đối tượng bảng vào trang đầu tiên của tài liệu đầu vào
tocPage.Paragraphs.Add(table);
// Lưu tài liệu cập nhật có chứa đối tượng bảng
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

## Phần kết luận
Xin chúc mừng! Bây giờ bạn đã học cách căn chỉnh nội dung của một hàng trong bảng trong tài liệu PDF bằng Aspose.PDF cho .NET. Hướng dẫn từng bước này chỉ cho bạn cách tạo tài liệu, khởi tạo bảng, cấu hình đường viền và căn chỉnh, thêm nội dung và lưu tài liệu PDF. Bây giờ bạn có thể áp dụng kiến thức này vào các dự án của riêng mình.

### Câu hỏi thường gặp

#### H: Làm thế nào để căn chỉnh nội dung của các ô trong bảng theo chiều ngang?

 A: Bạn có thể căn chỉnh nội dung của các ô trong bảng theo chiều ngang bằng cách thiết lập`HorizontalAlign` tính chất của tế bào`TextState` đối tượng. Ví dụ, để căn giữa văn bản, hãy sử dụng`cell.TextState.HorizontalAlignment = HorizontalAlignment.Center` . Bạn cũng có thể thiết lập nó thành`HorizontalAlignment.Left` hoặc`HorizontalAlignment.Right` để căn trái và căn phải tương ứng.

#### H: Tôi có thể áp dụng nhiều kiểu đường viền và màu sắc khác nhau cho từng ô trong bảng không?

 A: Có, bạn có thể áp dụng các kiểu đường viền và màu sắc khác nhau cho từng ô trong bảng. Để tùy chỉnh đường viền cho một ô cụ thể, hãy đặt`cell.Border` tài sản cho một cái mới`BorderInfo`đối tượng có các thiết lập mong muốn, chẳng hạn như cạnh viền, chiều rộng và màu sắc.

#### H: Làm thế nào để điều chỉnh căn chỉnh theo chiều dọc của nội dung bảng trong các ô?

 A: Bạn có thể điều chỉnh sự căn chỉnh theo chiều dọc của nội dung bảng trong các ô bằng cách thiết lập`VerticalAlignment` thuộc tính của hàng để`VerticalAlignment.Center`, `VerticalAlignment.Top` , hoặc`VerticalAlignment.Bottom`. Thuộc tính này kiểm soát sự căn chỉnh theo chiều dọc của tất cả các ô trong hàng đó.

#### H: Có thể thêm nhiều cột hoặc hàng vào bảng theo cách động không?

 A: Có, bạn có thể thêm nhiều cột và hàng vào bảng một cách linh hoạt bằng cách sử dụng`table.Rows.Add()` phương pháp để thêm hàng mới và`row.Cells.Add()` phương pháp thêm ô mới vào hàng. Bạn có thể thực hiện việc này bên trong vòng lặp hoặc dựa trên yêu cầu cụ thể của bạn.

#### H: Làm thế nào để thiết lập màu nền cho các ô cụ thể hoặc toàn bộ bảng?

 A: Để thiết lập màu nền cho các ô cụ thể hoặc toàn bộ bảng, hãy sử dụng`BackgroundColor` tài sản của`Cell` hoặc`Table` đối tượng. Ví dụ, để thiết lập màu nền của một ô, hãy sử dụng`cell.BackgroundColor = Aspose.Pdf.Color.LightBlue`.