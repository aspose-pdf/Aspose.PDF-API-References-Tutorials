---
title: Căn chỉnh văn bản cho nội dung hàng bảng
linktitle: Căn chỉnh văn bản cho nội dung hàng bảng
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách căn chỉnh nội dung hàng trong bảng PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 210
url: /vi/net/programming-with-tables/text-alignment-for-table-row-content/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước căn chỉnh nội dung của một hàng trong bảng của tài liệu PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích mã nguồn C# được cung cấp và chỉ cho bạn cách triển khai mã đó.

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

## Bước 4: Cấu hình viền ô bảng
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

## Bước 6: Cấu hình căn chỉnh đường dọc
Chúng ta sẽ định cấu hình căn chỉnh theo chiều dọc của các hàng trong bảng:

```csharp
row.VerticalAlignment = VerticalAlignment.Center;
```

## Bước 7: Thêm nội dung vào ô hàng
Chúng tôi sẽ thêm nội dung vào các ô hàng:

```csharp
row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
row.Cells.Add("Column("+row_count+",2)");
row.Cells.Add("Column("+row_count+",3)");
```

## Bước 8: Thêm bảng vào trang tài liệu
Bây giờ hãy thêm bảng vào trang tài liệu:

```csharp
Page tocPage = doc.Pages.Add();
tocPage.Paragraphs.Add(table);
```

## Bước 9: Lưu tài liệu PDF
Cuối cùng, chúng ta sẽ lưu tài liệu PDF:

```csharp
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

### Mã nguồn mẫu cho Căn chỉnh văn bản cho nội dung hàng trong bảng bằng Aspose.PDF cho .NET

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

// Tạo tài liệu PDF
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Khởi tạo một phiên bản mới của Bảng
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Đặt màu đường viền bảng là LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// đặt đường viền cho ô trong bảng
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
// Lưu tài liệu cập nhật chứa đối tượng bảng
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

## Phần kết luận
Xin chúc mừng! Bây giờ bạn đã học cách căn chỉnh nội dung của một hàng trong bảng trong tài liệu PDF bằng Aspose.PDF cho .NET. Hướng dẫn từng bước này chỉ cho bạn cách tạo tài liệu, khởi tạo bảng, định cấu hình đường viền và căn chỉnh, thêm nội dung và lưu tài liệu PDF. Bây giờ bạn có thể áp dụng kiến thức này vào dự án của riêng mình.

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể căn chỉnh nội dung của các ô trong bảng theo chiều ngang?

 Đáp: Bạn có thể căn chỉnh nội dung của các ô trong bảng theo chiều ngang bằng cách đặt`HorizontalAlign` thuộc tính của tế bào`TextState` sự vật. Ví dụ: để căn giữa văn bản, hãy sử dụng`cell.TextState.HorizontalAlignment = HorizontalAlignment.Center` . Bạn cũng có thể đặt nó thành`HorizontalAlignment.Left` hoặc`HorizontalAlignment.Right` để căn lề trái và phải tương ứng.

#### Câu hỏi: Tôi có thể áp dụng các kiểu và màu đường viền khác nhau cho từng ô trong bảng không?

 Đáp: Có, bạn có thể áp dụng các kiểu và màu đường viền khác nhau cho từng ô trong bảng. Để tùy chỉnh đường viền cho một ô cụ thể, hãy đặt`cell.Border` tài sản sang một tài sản mới`BorderInfo`đối tượng với các cài đặt mong muốn, chẳng hạn như các cạnh của đường viền, chiều rộng và màu sắc.

#### Câu hỏi: Làm cách nào tôi có thể điều chỉnh căn chỉnh theo chiều dọc của nội dung bảng trong các ô?

 Đáp: Bạn có thể điều chỉnh căn chỉnh theo chiều dọc của nội dung bảng trong các ô bằng cách đặt`VerticalAlignment` thuộc tính của hàng để`VerticalAlignment.Center`, `VerticalAlignment.Top` , hoặc`VerticalAlignment.Bottom`. Thuộc tính này kiểm soát việc căn chỉnh theo chiều dọc của tất cả các ô trong hàng đó.

#### Câu hỏi: Có thể thêm nhiều cột hoặc hàng vào bảng một cách linh hoạt không?

 Đáp: Có, bạn có thể thêm nhiều cột và hàng vào bảng một cách linh hoạt bằng cách sử dụng`table.Rows.Add()` phương pháp thêm hàng mới và`row.Cells.Add()` phương pháp thêm ô mới vào hàng. Bạn có thể thực hiện việc này bên trong các vòng lặp hoặc dựa trên yêu cầu cụ thể của mình.

#### Câu hỏi: Làm cách nào tôi có thể đặt màu nền cho các ô cụ thể hoặc toàn bộ bảng?

 Đáp: Để đặt màu nền cho các ô cụ thể hoặc toàn bộ bảng, hãy sử dụng`BackgroundColor` tài sản của`Cell` hoặc`Table` sự vật. Ví dụ: để đặt màu nền của ô, hãy sử dụng`cell.BackgroundColor = Aspose.Pdf.Color.LightBlue`.