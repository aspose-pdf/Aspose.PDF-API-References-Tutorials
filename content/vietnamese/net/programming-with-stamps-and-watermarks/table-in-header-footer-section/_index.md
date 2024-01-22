---
title: Bảng ở phần Header Footer
linktitle: Bảng ở phần Header Footer
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách thêm bảng vào phần đầu trang/chân trang của tài liệu PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 170
url: /vi/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước cách thêm bảng vào phần đầu trang hoặc chân trang của tài liệu PDF bằng Aspose.PDF cho .NET. Mã nguồn C# được cung cấp chỉ cho bạn cách tạo tài liệu PDF trống, thêm trang, định cấu hình phần tiêu đề, tạo bảng, thêm hàng và ô vào bảng và cuối cùng là lưu tài liệu PDF.

## Bước 1: Thiết lập môi trường

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Một môi trường phát triển .NET được cài đặt.
- Thư viện Aspose.PDF dành cho .NET được tải xuống và tham chiếu trong dự án của bạn.

## Bước 2: Tạo tài liệu và trang PDF

 Bước đầu tiên là tạo một thể hiện của`Document` class và thêm một trang vào tài liệu. Đây là cách thực hiện:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Khởi tạo một đối tượng Tài liệu
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Tạo một trang trong tài liệu PDF
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

Đảm bảo thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục mà bạn muốn lưu tài liệu PDF.

## Bước 3: Cấu hình phần tiêu đề

 Bây giờ chúng ta sẽ định cấu hình phần tiêu đề của tài liệu PDF bằng cách tạo một phiên bản của`HeaderFooter` lớp học. Đây là cách thực hiện:

```csharp
// Tạo phần tiêu đề cho file PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Xác định phần tiêu đề cho trang
page. Header = header;

// Đặt lề trên của phần tiêu đề
header. Margin. Top = 20;
```

## Bước 4: Tạo bảng

 Bây giờ chúng ta sẽ tạo một bảng bằng cách sử dụng`Table` class và thêm nó vào bộ sưu tập đoạn văn của phần tiêu đề. Đây là cách thực hiện:

```csharp
// Khởi tạo một đối tượng Bảng
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Thêm bảng vào bộ sưu tập đoạn văn của phần tiêu đề
header.Paragraphs.Add(tab1);

// Xác định độ rộng của các cột trong bảng
tab1.ColumnWidths = "60,300";
```

Đoạn mã trên tạo một bảng có hai cột có chiều rộng được chỉ định.

## Bước 5: Thêm hàng và ô vào bảng

 Bây giờ chúng ta sẽ thêm hàng và ô vào bảng bằng cách sử dụng`Row` lớp học và`Cell` lớp học. Đây là cách thực hiện:

```csharp
// Tạo một hàng trong bảng và thêm ô
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in header section");
row1.BackgroundColor = Color.Gray;

// Hợp nhất ô đầu tiên của hàng đầu tiên
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Tạo một hàng khác trong bảng và thêm một ô có hình ảnh
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.BackgroundColor = Color.White;
Aspose.Pdf.Cell cell2 = row2.Cells.Add();
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";
img. FixWidth = 60;
cell2.Paragraphs.Add(img);
row2.Cells.Add("The logo is beautiful!");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
```

## Bước 6: Lưu tài liệu PDF

Khi bảng đã được thêm vào phần tiêu đề, chúng ta có thể lưu tài liệu PDF. Đây là cách thực hiện:

```csharp
// Lưu tệp PDF
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

Đảm bảo thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục mà bạn muốn lưu tài liệu PDF.

### Mã nguồn mẫu cho Bảng trong Phần chân trang đầu trang sử dụng Aspose.PDF cho .NET 
```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Khởi tạo phiên bản Tài liệu bằng cách gọi hàm tạo trống
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Tạo một trang trong tài liệu pdf
Aspose.Pdf.Page page = pdfDocument.Pages.Add();

// Tạo phần tiêu đề của tệp PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//Đặt Odd Header cho file PDF
page.Header = header;

// Đặt lề trên cho phần tiêu đề
header.Margin.Top = 20;

// Khởi tạo một đối tượng bảng
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Thêm bảng vào bộ sưu tập đoạn văn của phần mong muốn
header.Paragraphs.Add(tab1);

// Đặt đường viền ô mặc định bằng đối tượng BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Đặt độ rộng cột của bảng
tab1.ColumnWidths = "60 300";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";

// Tạo các hàng trong bảng và sau đó tạo các ô trong các hàng
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;

// Đặt giá trị khoảng hàng cho hàng đầu tiên là 2
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Tạo các hàng trong bảng và sau đó tạo các ô trong các hàng
Aspose.Pdf.Row row2 = tab1.Rows.Add();

// Đặt màu nền cho Row2
row2.BackgroundColor = Color.White;

// Thêm ô chứa hình ảnh
Aspose.Pdf.Cell cell2 = row2.Cells.Add();

// Đặt chiều rộng hình ảnh thành 60
img.FixWidth = 60;

// Thêm hình ảnh vào ô bảng
cell2.Paragraphs.Add(img);
row2.Cells.Add("Logo is looking fine !");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Đặt căn chỉnh theo chiều dọc của văn bản là căn giữa
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;

// Lưu tệp Pdf
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");

```

## Phần kết luận

Xin chúc mừng! Bạn đã tìm hiểu cách thêm bảng vào phần đầu trang hoặc chân trang của tài liệu PDF bằng Aspose.PDF cho .NET. Giờ đây, bạn có thể tùy chỉnh đầu trang và chân trang bằng cách thêm bảng để hiển thị thông tin bổ sung trong tài liệu PDF của mình.

### Câu hỏi thường gặp về bảng ở phần chân trang đầu trang

#### Hỏi: Mục đích của việc thêm bảng vào phần đầu trang hoặc chân trang của tài liệu PDF là gì?

Đáp: Việc thêm bảng vào phần đầu trang hoặc chân trang của tài liệu PDF cho phép bạn hiển thị thông tin có cấu trúc và sắp xếp như tiêu đề, phụ đề, biểu trưng hoặc bất kỳ nội dung nào khác mà bạn muốn xuất hiện nhất quán trên mỗi trang của tài liệu.

#### Câu hỏi: Làm cách nào để mã nguồn C# được cung cấp có thể thêm bảng vào phần đầu trang hoặc chân trang của tài liệu PDF?

Đáp: Mã này thể hiện quy trình tạo một tài liệu PDF trống, thêm trang, định cấu hình phần tiêu đề, tạo bảng có các hàng và ô và cuối cùng là lưu tài liệu PDF. Kết quả là một bảng hiển thị trong phần tiêu đề của tài liệu PDF.

#### Câu hỏi: Tôi có thể tùy chỉnh hình thức của các ô trong bảng, chẳng hạn như đường viền, màu nền và kiểu văn bản không?

Trả lời: Có, bạn có thể tùy chỉnh giao diện của các ô trong bảng bằng cách đặt các thuộc tính như viền ô, màu nền, kiểu văn bản, phông chữ, cỡ chữ, v.v.

#### Hỏi: Bảng được thêm vào phần tiêu đề của tài liệu PDF như thế nào?

Đáp: Mã thêm bảng vào tập hợp đoạn văn của phần tiêu đề, đảm bảo rằng bảng được hiển thị trong tiêu đề của mỗi trang.

#### Câu hỏi: Tôi có thể thêm nhiều hàng và ô vào bảng nếu cần không?

 Đáp: Hoàn toàn có thể, bạn có thể thêm nhiều hàng và ô vào bảng bằng cách sử dụng`Rows.Add()` Và`Cells.Add()` phương pháp. Điều này cho phép bạn cấu trúc nội dung bảng như mong muốn.

#### Hỏi: Có thể điều chỉnh độ rộng của các cột trong bảng không?
 Đáp: Có, bạn có thể điều chỉnh độ rộng của các cột trong bảng bằng cách sử dụng`ColumnWidths` tài sản. Điều này cho phép bạn kiểm soát cách bố trí của bảng.

#### Câu hỏi: Làm cách nào tôi có thể mở rộng các ô trên nhiều cột hoặc hàng trong bảng?
 Đáp: Để mở rộng các ô trên nhiều cột, bạn có thể sử dụng`ColSpan` thuộc tính của ô tương ứng. Tương tự, bạn có thể sử dụng`RowSpan` thuộc tính để mở rộng các ô trên nhiều hàng.

#### Hỏi: Điều gì xảy ra nếu tôi muốn thêm bảng vào cả phần đầu trang và chân trang của tài liệu PDF?

Đáp: Bạn có thể làm theo cách tiếp cận tương tự cho cả phần đầu trang và chân trang. Đơn giản chỉ cần tạo một`HeaderFooter` ví dụ cho phần chân trang, định cấu hình và thêm bảng vào bộ sưu tập đoạn văn của nó.

#### Câu hỏi: Tôi có thể sử dụng hình ảnh trong các ô của bảng không và làm cách nào để đạt được điều đó?

 Đáp: Có, bạn có thể thêm hình ảnh vào trong các ô của bảng. Ví dụ mã minh họa việc thêm hình ảnh vào một ô bằng cách tạo một`Image` đối tượng, đặt đường dẫn và kích thước tệp của nó, sau đó thêm nó vào các đoạn văn của ô.

#### Câu hỏi: Làm cách nào để đảm bảo bảng xuất hiện nhất quán trên tất cả các trang trong tài liệu PDF?

 Đáp: Khi bạn thêm bảng vào phần đầu trang hoặc chân trang bằng cách sử dụng`HeaderFooter` Ví dụ: Aspose.PDF đảm bảo rằng bảng xuất hiện nhất quán trên mỗi trang, cung cấp bố cục thống nhất.