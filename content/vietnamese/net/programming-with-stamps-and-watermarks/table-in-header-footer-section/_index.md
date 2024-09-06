---
title: Bảng Trong Phần Đầu Trang Chân Trang
linktitle: Bảng Trong Phần Đầu Trang Chân Trang
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách thêm bảng vào phần đầu trang/chân trang của tài liệu PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 170
url: /vi/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước về cách thêm bảng vào phần đầu trang hoặc chân trang của tài liệu PDF bằng Aspose.PDF cho .NET. Mã nguồn C# được cung cấp sẽ chỉ cho bạn cách tạo tài liệu PDF trống, thêm trang, cấu hình phần đầu trang, tạo bảng, thêm hàng và ô vào bảng và cuối cùng là lưu tài liệu PDF.

## Bước 1: Thiết lập môi trường

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Môi trường phát triển .NET đã được cài đặt.
- Thư viện Aspose.PDF dành cho .NET đã được tải xuống và tham chiếu trong dự án của bạn.

## Bước 2: Tạo Tài liệu PDF và Trang

 Bước đầu tiên là tạo một phiên bản của`Document` lớp và thêm một trang vào tài liệu. Sau đây là cách thực hiện:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Khởi tạo một đối tượng Tài liệu
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Tạo một trang trong tài liệu PDF
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

Hãy nhớ thay thế "YOUR DOCUMENTS DIRECTORY" bằng đường dẫn thực tế đến thư mục mà bạn muốn lưu tài liệu PDF.

## Bước 3: Cấu hình phần tiêu đề

 Bây giờ chúng ta sẽ cấu hình phần tiêu đề của tài liệu PDF bằng cách tạo một phiên bản của`HeaderFooter` lớp. Đây là cách thực hiện:

```csharp
// Tạo phần tiêu đề cho tệp PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Xác định phần tiêu đề cho trang
page. Header = header;

// Đặt lề trên của phần tiêu đề
header. Margin. Top = 20;
```

## Bước 4: Tạo bảng

 Bây giờ chúng ta sẽ tạo một bảng bằng cách sử dụng`Table` lớp và thêm nó vào bộ sưu tập đoạn văn của phần tiêu đề. Sau đây là cách thực hiện:

```csharp
// Khởi tạo một đối tượng Bảng
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Thêm bảng vào bộ sưu tập đoạn văn của phần tiêu đề
header.Paragraphs.Add(tab1);

// Xác định độ rộng của các cột trong bảng
tab1.ColumnWidths = "60,300";
```

Đoạn mã trên tạo ra một bảng có hai cột có độ rộng được chỉ định.

## Bước 5: Thêm hàng và ô vào bảng

 Bây giờ chúng ta sẽ thêm các hàng và ô vào bảng bằng cách sử dụng`Row` lớp và`Cell` lớp. Đây là cách thực hiện:

```csharp
// Tạo một hàng trong bảng và thêm ô
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in header section");
row1.BackgroundColor = Color.Gray;

// Gộp ô đầu tiên của hàng đầu tiên
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

Sau khi bảng đã được thêm vào phần tiêu đề, chúng ta có thể lưu tài liệu PDF. Thực hiện như sau:

```csharp
// Lưu tệp PDF
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

Hãy nhớ thay thế "YOUR DOCUMENTS DIRECTORY" bằng đường dẫn thực tế đến thư mục mà bạn muốn lưu tài liệu PDF.

### Mã nguồn mẫu cho Bảng trong Phần Đầu trang Chân trang sử dụng Aspose.PDF cho .NET 
```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Khởi tạo thể hiện Document bằng cách gọi hàm tạo rỗng
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Tạo một trang trong tài liệu pdf
Aspose.Pdf.Page page = pdfDocument.Pages.Add();

//Tạo Phần Tiêu đề của tệp PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Đặt Tiêu đề Lẻ cho tệp PDF
page.Header = header;

// Đặt lề trên cho phần tiêu đề
header.Margin.Top = 20;

// Khởi tạo một đối tượng bảng
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Thêm bảng vào bộ sưu tập đoạn văn của phần mong muốn
header.Paragraphs.Add(tab1);

// Đặt đường viền ô mặc định bằng cách sử dụng đối tượng BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Thiết lập với chiều rộng cột của bảng
tab1.ColumnWidths = "60 300";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";

// Tạo các hàng trong bảng và sau đó tạo các ô trong các hàng
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;

// Đặt giá trị khoảng cách hàng cho hàng đầu tiên là 2
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Tạo các hàng trong bảng và sau đó tạo các ô trong các hàng
Aspose.Pdf.Row row2 = tab1.Rows.Add();

// Đặt màu nền cho Row2
row2.BackgroundColor = Color.White;

// Thêm ô chứa hình ảnh
Aspose.Pdf.Cell cell2 = row2.Cells.Add();

// Đặt chiều rộng hình ảnh là 60
img.FixWidth = 60;

// Thêm hình ảnh vào ô bảng
cell2.Paragraphs.Add(img);
row2.Cells.Add("Logo is looking fine !");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Đặt căn chỉnh theo chiều dọc của văn bản thành căn giữa
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;

// Lưu tệp PDF
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");

```

## Phần kết luận

Xin chúc mừng! Bạn đã học cách thêm bảng vào phần đầu trang hoặc chân trang của tài liệu PDF bằng Aspose.PDF cho .NET. Bây giờ bạn có thể tùy chỉnh phần đầu trang và chân trang bằng cách thêm bảng để hiển thị thông tin bổ sung trong tài liệu PDF của mình.

### Câu hỏi thường gặp về bảng trong phần đầu trang và chân trang

#### H: Mục đích của việc thêm bảng vào phần đầu trang hoặc chân trang của tài liệu PDF là gì?

A: Thêm bảng vào phần đầu trang hoặc chân trang của tài liệu PDF cho phép bạn hiển thị thông tin có cấu trúc và được sắp xếp hợp lý như tiêu đề, phụ đề, logo hoặc bất kỳ nội dung nào khác mà bạn muốn hiển thị thống nhất trên mỗi trang của tài liệu.

#### H: Mã nguồn C# được cung cấp thực hiện chức năng thêm bảng vào phần đầu trang hoặc chân trang của tài liệu PDF như thế nào?

A: Mã này minh họa quá trình tạo một tài liệu PDF trống, thêm trang, cấu hình phần tiêu đề, tạo bảng có hàng và ô, và cuối cùng là lưu tài liệu PDF. Kết quả là một bảng được hiển thị trong phần tiêu đề của tài liệu PDF.

#### H: Tôi có thể tùy chỉnh giao diện của các ô trong bảng như đường viền, màu nền và kiểu văn bản không?

A: Có, bạn có thể tùy chỉnh giao diện của các ô trong bảng bằng cách thiết lập các thuộc tính như đường viền ô, màu nền, kiểu văn bản, phông chữ, cỡ chữ, v.v.

#### H: Làm thế nào để thêm bảng vào phần tiêu đề của tài liệu PDF?

A: Mã này thêm bảng vào bộ sưu tập đoạn văn của phần tiêu đề, đảm bảo rằng bảng được hiển thị ở phần tiêu đề của mỗi trang.

#### H: Tôi có thể thêm nhiều hàng và ô vào bảng khi cần không?

 A: Hoàn toàn có thể, bạn có thể thêm nhiều hàng và ô vào bảng bằng cách sử dụng`Rows.Add()` Và`Cells.Add()` phương pháp. Điều này cho phép bạn cấu trúc nội dung bảng theo ý muốn.

#### H: Có thể điều chỉnh độ rộng của các cột trong bảng không?
 A: Có, bạn có thể điều chỉnh chiều rộng của các cột trong bảng bằng cách sử dụng`ColumnWidths` thuộc tính. Điều này cho phép bạn kiểm soát bố cục của bảng.

#### H: Làm thế nào tôi có thể kéo dài các ô trên nhiều cột hoặc hàng trong bảng?
 A: Để kéo dài các ô trên nhiều cột, bạn có thể sử dụng`ColSpan`thuộc tính của ô tương ứng. Tương tự, bạn có thể sử dụng`RowSpan` thuộc tính kéo dài các ô trên nhiều hàng.

#### H: Điều gì xảy ra nếu tôi muốn thêm bảng vào cả phần đầu trang và phần chân trang của tài liệu PDF?

 A: Bạn có thể làm theo cách tiếp cận tương tự cho cả phần đầu trang và phần chân trang. Chỉ cần tạo một`HeaderFooter` trường hợp cho phần chân trang, cấu hình nó và thêm bảng vào bộ sưu tập đoạn văn của nó.

#### H: Tôi có thể sử dụng hình ảnh trong các ô của bảng không và thực hiện như thế nào?

 A: Có, bạn có thể thêm hình ảnh vào các ô của bảng. Ví dụ mã minh họa việc thêm hình ảnh vào một ô bằng cách tạo một`Image` đối tượng, thiết lập đường dẫn tệp và kích thước của nó, sau đó thêm nó vào các đoạn văn của ô.

#### H: Làm thế nào để đảm bảo bảng xuất hiện thống nhất trên tất cả các trang trong tài liệu PDF?

 A: Khi bạn thêm bảng vào phần đầu trang hoặc chân trang bằng cách sử dụng`HeaderFooter` Ví dụ, Aspose.PDF đảm bảo rằng bảng xuất hiện nhất quán trên mỗi trang, mang lại bố cục thống nhất.