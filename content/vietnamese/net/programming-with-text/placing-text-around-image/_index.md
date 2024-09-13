---
title: Đặt Văn Bản Xung Quanh Hình Ảnh Trong Tệp PDF
linktitle: Đặt Văn Bản Xung Quanh Hình Ảnh Trong Tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách chèn văn bản xung quanh hình ảnh trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 260
url: /vi/net/programming-with-text/placing-text-around-image/
---
Trong hướng dẫn này, chúng tôi sẽ giải thích cách đặt văn bản xung quanh hình ảnh trong tệp PDF bằng thư viện Aspose.PDF cho .NET. Chúng tôi sẽ thực hiện từng bước để tạo bảng, thêm hình ảnh và định vị văn bản xung quanh hình ảnh bằng mã nguồn C# được cung cấp.

## Yêu cầu

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Đã cài đặt thư viện Aspose.PDF cho .NET.
- Hiểu biết cơ bản về lập trình C#.

## Bước 1: Thiết lập thư mục tài liệu

 Đầu tiên, bạn cần thiết lập đường dẫn đến thư mục mà bạn muốn lưu tệp PDF đã tạo. Thay thế`"YOUR DOCUMENT DIRECTORY"` trong`dataDir` biến có đường dẫn đến thư mục bạn mong muốn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tạo Tài liệu và Trang

 Tiếp theo, chúng ta tạo ra một`Document` đối tượng và thêm một trang vào đó bằng cách sử dụng`Pages.Add()` phương pháp.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Bước 3: Tạo bảng

 Chúng tôi tạo một bảng bằng cách sử dụng`Table` lớp và thêm nó vào bộ sưu tập đoạn văn của trang.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## Bước 4: Thiết lập chiều rộng cột và lề của bảng

 Chúng tôi thiết lập độ rộng cột của bảng và tạo một`MarginInfo` đối tượng để thiết lập lề.

```csharp
table1. ColumnWidths = "120,270";
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;
table1. DefaultCellPadding = margin;
```

## Bước 5: Thêm hình ảnh vào bảng

 Chúng tôi tạo ra một`Image` đối tượng, chỉ định đường dẫn tệp hình ảnh và đặt chiều cao và chiều rộng cố định của hình ảnh. Sau đó, chúng ta thêm hình ảnh vào bộ sưu tập đoạn văn của ô bảng.

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## Bước 6: Thêm văn bản xung quanh hình ảnh

 Chúng tôi tạo các biến chuỗi chứa văn bản định dạng HTML và tạo một`HtmlFragment`đối tượng. Sau đó, chúng ta thêm văn bản HTML vào ô bảng chứa hình ảnh.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## Bước 7: Thêm văn bản bổ sung

 Chúng tôi tạo ra một cái khác`HtmlFragment` đối tượng chứa văn bản định dạng HTML bổ sung và thêm nó vào một ô bảng riêng biệt.

```csharp
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

## Bước 8: Lưu tài liệu PDF

Cuối cùng, chúng ta lưu tài liệu PDF vào tệp đầu ra đã chỉ định.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

### Mã nguồn mẫu để Đặt văn bản xung quanh hình ảnh bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Khởi tạo đối tượng tài liệu
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Tạo một trang trong Pdf
Aspose.Pdf.Page page = doc.Pages.Add();
// Khởi tạo một đối tượng bảng
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
// Thêm bảng vào bộ sưu tập đoạn văn của phần mong muốn
page.Paragraphs.Add(table1);
// Thiết lập với chiều rộng cột của bảng
table1.ColumnWidths = "120 270";
// Tạo đối tượng MarginInfo và thiết lập lề trái, dưới, phải và trên của nó
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Đặt khoảng đệm ô mặc định thành đối tượng MarginInfo
table1.DefaultCellPadding = margin;
// Tạo các hàng trong bảng và sau đó tạo các ô trong các hàng
Aspose.Pdf.Row row1 = table1.Rows.Add();
// Tạo một đối tượng hình ảnh
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
// Chỉ định đường dẫn tệp hình ảnh
logo.File = dataDir + "aspose-logo.jpg";
// Chỉ định chiều cao cố định của hình ảnh
logo.FixHeight = 120;
// Chỉ định chiều rộng cố định của hình ảnh
logo.FixWidth = 110;
row1.Cells.Add();
// Thêm hình ảnh vào bộ sưu tập đoạn văn của ô bảng
row1.Cells[0].Paragraphs.Add(logo);
// Tạo biến chuỗi với văn bản chứa thẻ html
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
//Tạo một đối tượng văn bản để thêm vào bên phải hình ảnh
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
// Thêm các đoạn văn bản chứa văn bản HTML vào ô bảng
row1.Cells[1].Paragraphs.Add(TitleText);
// Đặt căn chỉnh theo chiều dọc của nội dung hàng thành Top
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
//Tạo các hàng trong bảng và sau đó tạo các ô trong các hàng
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
// Đặt giá trị khoảng cách hàng cho Hàng thứ hai là 2
SecondRow.Cells[0].ColSpan = 2;
// Đặt căn chỉnh theo chiều dọc của hàng thứ hai là Top
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
// Thêm các đoạn văn bản chứa văn bản HTML vào ô bảng
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
// Lưu tệp PDF
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách đặt văn bản xung quanh hình ảnh trong tài liệu PDF bằng thư viện Aspose.PDF cho .NET. Bằng cách làm theo hướng dẫn từng bước và thực thi mã C# được cung cấp, bạn có thể tạo bảng, thêm hình ảnh và định vị văn bản xung quanh hình ảnh trong tài liệu PDF.

### Câu hỏi thường gặp

#### H: Mục đích của hướng dẫn "Đặt văn bản xung quanh hình ảnh trong tệp PDF" là gì?

A: Hướng dẫn "Đặt văn bản xung quanh hình ảnh trong tệp PDF" trình bày cách sử dụng thư viện Aspose.PDF cho .NET để đặt văn bản xung quanh hình ảnh trong tài liệu PDF. Hướng dẫn cung cấp hướng dẫn từng bước và mã nguồn C# để giúp bạn tạo bảng, thêm hình ảnh và định vị văn bản xung quanh hình ảnh.

#### H: Tại sao tôi muốn chèn văn bản xung quanh hình ảnh trong tài liệu PDF?

A: Đặt văn bản xung quanh hình ảnh giúp tăng cường khả năng trình bày trực quan của tài liệu PDF, khiến chúng hấp dẫn và nhiều thông tin hơn. Kỹ thuật này thường được sử dụng trong các tài liệu, tờ rơi, báo cáo và các tài liệu khác mà bạn muốn kết hợp hình ảnh và văn bản theo cách thẩm mỹ.

#### H: Tôi phải thiết lập thư mục tài liệu như thế nào?

A: Để thiết lập thư mục tài liệu:

1.  Thay thế`"YOUR DOCUMENT DIRECTORY"` trong`dataDir` biến có đường dẫn đến thư mục mà bạn muốn lưu tệp PDF đã tạo.

#### H: Làm thế nào để tạo bảng và thêm hình ảnh vào đó?

 A: Hướng dẫn này hướng dẫn bạn quy trình tạo bảng bằng cách sử dụng`Table` lớp và thêm hình ảnh vào bảng bằng cách sử dụng`Image` lớp. Bạn sẽ chỉ định đường dẫn tệp hình ảnh, chiều cao và chiều rộng trước khi thêm nó vào ô bảng.

#### H: Làm thế nào để định vị văn bản xung quanh hình ảnh?

 A: Để định vị văn bản xung quanh hình ảnh, bạn sẽ tạo văn bản định dạng HTML bằng cách sử dụng`HtmlFragment` lớp. Văn bản này sẽ chứa cả tiêu đề và nội dung văn bản. Sau đó, bạn sẽ thêm văn bản HTML này vào ô bảng nằm cạnh ô hình ảnh.

#### H: Tôi có thể tùy chỉnh giao diện của văn bản và hình ảnh không?

A: Có, bạn có thể tùy chỉnh giao diện của văn bản và hình ảnh bằng thẻ HTML và thuộc tính. Ví dụ, bạn có thể đặt kích thước phông chữ, màu sắc, kiểu và căn chỉnh cho văn bản. Ngoài ra, bạn có thể điều chỉnh kích thước và kích thước của hình ảnh.

#### H: Làm thế nào để lưu tài liệu PDF?

 A: Sau khi thêm hình ảnh và văn bản vào bảng, bạn có thể lưu tài liệu PDF bằng cách sử dụng`Save` phương pháp của`Document` lớp. Cung cấp đường dẫn tệp đầu ra mong muốn làm đối số cho`Save` phương pháp.

#### H: Kết quả mong đợi của hướng dẫn này là gì?

A: Bằng cách làm theo hướng dẫn và thực thi mã C# được cung cấp, bạn sẽ tạo ra một tài liệu PDF minh họa cách đặt văn bản xung quanh hình ảnh. Tài liệu đầu ra sẽ chứa một bảng có hình ảnh và văn bản được định vị xung quanh nó.

#### H: Tôi có thể sử dụng định dạng hình ảnh khác ngoài JPG không?

 A: Có, bạn có thể sử dụng các định dạng hình ảnh khác nhau được hỗ trợ bởi thư viện Aspose.PDF, chẳng hạn như PNG, BMP, GIF, v.v. Khi tạo`Image` đối tượng, chỉ định đường dẫn tệp của định dạng hình ảnh mong muốn.

#### H: Có cần Giấy phép Aspose hợp lệ cho hướng dẫn này không?

A: Có, cần phải có Giấy phép Aspose hợp lệ để hướng dẫn này hoạt động chính xác. Bạn có thể mua giấy phép đầy đủ hoặc xin giấy phép tạm thời 30 ngày từ trang web Aspose.