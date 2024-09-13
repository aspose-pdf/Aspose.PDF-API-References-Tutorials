---
title: Bảng Trong Phần Đầu Trang Chân Trang
linktitle: Bảng Trong Phần Đầu Trang Chân Trang
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách thêm bảng vào phần đầu trang/chân trang của tài liệu PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 170
url: /vi/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
## Giới thiệu

Bạn đã bao giờ thấy mình đang nhìn chằm chằm vào một tài liệu PDF đơn giản, ước rằng nó có thêm nét riêng biệt đó không? Vâng, bạn thật may mắn! Aspose.PDF cho .NET cho phép bạn tạo và thao tác các tệp PDF như một chuyên gia. Hôm nay, chúng ta sẽ tìm hiểu một tính năng tiện dụng cho phép bạn thêm một bảng vào tiêu đề của tài liệu PDF. Bạn sẽ không chỉ học cách thực hiện mà tôi còn hướng dẫn bạn từng bước, giúp toàn bộ quá trình trở nên dễ dàng như bơ. 🎉

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu phần mã hóa thực tế, hãy đảm bảo rằng bạn có mọi thứ cần thiết để bắt đầu. Sau đây là những gì bạn cần:

1.  Visual Studio: Đảm bảo rằng bạn đã cài đặt Visual Studio trên máy tính của mình. Nếu chưa, bạn có thể tải xuống từ[Trang web của Microsoft](https://visualstudio.microsoft.com/).
2.  Thư viện Aspose.PDF: Bạn phải có thư viện Aspose.PDF cho .NET. Bạn có thể sử dụng liên kết sau để lấy[Aspose.PDF cho gói .NET](https://releases.aspose.com/pdf/net/).
3. Kiến thức cơ bản về C#: Bạn nên có ít nhất một hiểu biết cơ bản về C#. Đừng lo lắng nếu bạn vẫn đang học; Tôi sẽ làm cho nó đơn giản nhất có thể!

## Nhập gói

Được rồi, đã đến lúc xắn tay áo lên và bắt tay vào viết mã! Nhưng trước tiên, chúng ta cần thiết lập môi trường của mình bằng cách nhập các gói cần thiết. Sau đây là cách thực hiện:

###  Mở dự án của bạn
Mở dự án Visual Studio nơi bạn sẽ thực hiện thao tác tạo PDF. 

###  Thêm tham chiếu đến Aspose.PDF
1. Trình quản lý gói NuGet: Nhấp chuột phải vào dự án của bạn trong Solution Explorer và chọn "Quản lý gói NuGet".
2. Tìm kiếm Aspose.PDF: Trong thanh tìm kiếm, nhập "Aspose.PDF" và cài đặt gói.

Đến cuối bước này, mọi thứ sẽ được thiết lập xong và sẵn sàng để bắt đầu viết mã!

Bây giờ, hãy bắt tay vào làm một số mã! Thực hiện theo các bước sau để tạo một bảng trong phần tiêu đề của tệp PDF của bạn:

## Bước 1: Đặt đường dẫn đến thư mục tài liệu của bạn

Trước khi bắt đầu tạo PDF, chúng ta cần xác định nơi lưu trữ tài liệu. Sau đây là cách thực hiện:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Thay đổi thư mục này thành thư mục thực tế của bạn
```

 Thay thế`YOUR DOCUMENT DIRECTORY`với đường dẫn mà bạn muốn lưu PDF. Đường dẫn này có thể nằm ở bất kỳ đâu trên hệ thống của bạn—chỉ cần đảm bảo rằng đường dẫn đó có thể truy cập được!

## Bước 2: Khởi tạo tài liệu

Tiếp theo, chúng ta sẽ tạo một tài liệu PDF mới.

```csharp
// Khởi tạo thể hiện Document bằng cách gọi hàm tạo rỗng
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();
```

Những gì chúng ta đang làm ở đây là tạo một tài liệu PDF trống để thêm tất cả các nội dung bổ sung.

## Bước 3: Tạo một trang mới

Hãy thêm một trang mới vào tài liệu của chúng ta. 

```csharp
// Tạo một trang trong tài liệu pdf
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

Hãy coi trang này như một tấm vải trắng để chúng ta có thể vẽ nên kiệt tác của mình!

## Bước 4: Tạo phần tiêu đề

Bây giờ chúng ta sẽ thiết lập tiêu đề cho tệp PDF.

```csharp
// Tạo Phần Tiêu đề của tệp PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
```

Phần đầu này sẽ giữ bảng của chúng ta. 

## Bước 5: Gán Header cho Trang

Tiếp theo, chúng ta muốn đảm bảo tiêu đề xuất hiện trên trang.

```csharp
// Đặt Tiêu đề Lẻ cho tệp PDF
page.Header = header;
```

## Bước 6: Đặt lề trên cùng

Để đảm bảo phần tiêu đề có đủ khoảng trống ở phía trên, hãy điều chỉnh lề.

```csharp
//Đặt lề trên cho phần tiêu đề
header.Margin.Top = 20;
```

Việc đặt lề giống như cung cấp cho văn bản của bạn một khoảng không gian riêng tư—không ai thích bị chật chội cả!

## Bước 7: Tạo bảng

Bây giờ là lúc tạo bảng sẽ đưa vào tiêu đề của chúng ta.

```csharp
// Khởi tạo một đối tượng bảng
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Bước 8: Thêm Bảng vào Tiêu đề

Chúng ta sẽ thêm bảng mới tạo vào bộ sưu tập đoạn văn của tiêu đề.

```csharp
// Thêm bảng vào bộ sưu tập đoạn văn của phần mong muốn
header.Paragraphs.Add(tab1);
```

## Bước 9: Thiết lập đường viền ô

Hãy cung cấp cho bảng của chúng ta một số cấu trúc bằng cách xác định đường viền ô mặc định.

```csharp
// Đặt đường viền ô mặc định bằng cách sử dụng đối tượng BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Bước 10: Xác định độ rộng cột

Bạn có thể chỉ định độ rộng của mỗi cột trong bảng.

```csharp
// Thiết lập với chiều rộng cột của bảng
tab1.ColumnWidths = "60 300";
```

Các giá trị thể hiện chiều rộng của mỗi cột theo điểm. Hãy thoải mái điều chỉnh chúng cho phù hợp với nhu cầu của bạn!

## Bước 11: Tạo hàng và thêm ô

Đã đến lúc thêm vào một số hàng và ô! 

```csharp
//Tạo các hàng trong bảng và sau đó tạo các ô trong các hàng
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;
```

Thao tác này sẽ tạo ra hàng đầu tiên có ô chứa văn bản và đặt màu nền của ô này thành màu xám.

## Bước 12: Thiết lập khoảng cách hàng và kiểu văn bản

Bạn có muốn hàng của mình trải dài trên nhiều cột không? Đây là cách thực hiện:

```csharp
// Đặt giá trị khoảng cách hàng cho hàng đầu tiên là 2
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");
```

Bước này không chỉ thiết lập khoảng cách hàng mà còn thay đổi màu chữ và phông chữ.

## Bước 13: Thêm hàng thứ hai

Chúng ta hãy thêm một hàng nữa vào bảng nhé?

```csharp
// Tạo một hàng khác trong bảng
Aspose.Pdf.Row row2 = tab1.Rows.Add();

// Đặt màu nền cho Row2
row2.BackgroundColor = Color.White;
```

## Bước 14: Thêm hình ảnh vào hàng thứ hai

Bây giờ chúng ta sẽ thêm logo vào để làm cho chiếc bàn trông thật bắt mắt!

```csharp
// Thêm ô chứa hình ảnh
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg"; // Hãy chắc chắn đặt hình ảnh vào thư mục của bạn
```

 Đừng quên thay thế`"aspose-logo.jpg"` với tên thực tế của hình ảnh của bạn!

## Bước 15: Điều chỉnh chiều rộng hình ảnh

Đặt chiều rộng hình ảnh để đảm bảo hình ảnh trông vừa vặn trong ô.

```csharp
// Đặt chiều rộng hình ảnh là 60
img.FixWidth = 60;

//Thêm hình ảnh vào ô bảng
Aspose.Pdf.Cell cell2 = row2.Cells.Add();
cell2.Paragraphs.Add(img);
```

## Bước 16: Thêm văn bản vào ô thứ hai

Đã đến lúc thêm một đoạn văn bản nhỏ bên cạnh logo của chúng tôi!

```csharp
row2.Cells.Add("Logo is looking fine !");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");
```

## Bước 17: Căn chỉnh văn bản theo chiều dọc và chiều ngang

Đảm bảo mọi thứ trông gọn gàng. Căn chỉnh văn bản của bạn!

```csharp
// Đặt căn chỉnh theo chiều dọc của văn bản thành căn giữa
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
```

## Bước 18: Lưu tài liệu PDF

Cuối cùng nhưng không kém phần quan trọng, hãy cùng lưu lại sáng tạo của chúng ta!

```csharp
// Lưu tệp PDF
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

Và thế là xong! Bạn đã tạo được một tệp PDF tuyệt đẹp có kèm theo một bảng ở phần tiêu đề!

## Phần kết luận

Và thế là xong! Bạn đã thêm thành công một bảng vào tiêu đề của tài liệu PDF bằng Aspose.PDF cho .NET. Thật tuyệt vời khi chỉ cần một vài dòng mã có thể biến một tệp PDF đơn giản thành một tài liệu trông chuyên nghiệp. Cho dù bạn đang chuẩn bị báo cáo, hóa đơn hay bài thuyết trình, thêm một chút sáng tạo có thể tạo nên sự khác biệt. 

## Câu hỏi thường gặp

### Aspose.PDF dành cho .NET là gì?
Aspose.PDF for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển tạo và xử lý các tài liệu PDF theo chương trình.

### Tôi có cần giấy phép để sử dụng Aspose.PDF không?
 Trong khi bạn có thể sử dụng thư viện miễn phí trong thời gian dùng thử, bạn cần phải có giấy phép để sử dụng lâu dài. Bạn có thể lấy[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) để đánh giá.

### Tôi có thể tìm tài liệu ở đâu?
Bạn có thể tìm thấy tài liệu và ví dụ toàn diện trên[Trang tài liệu Aspose.PDF](https://reference.aspose.com/pdf/net/).

### Tôi có thể liên hệ với bộ phận hỗ trợ về các vấn đề kỹ thuật bằng cách nào?
 Bạn có thể liên hệ để được hỗ trợ thông qua[Diễn đàn Aspose](https://forum.aspose.com/c/pdf/10).

### Tôi có thể tạo bảng ở các phần khác của tệp PDF không?
Hoàn toàn được! Bạn cũng có thể tạo bảng ở phần chân trang và phần thân bài; chỉ cần làm theo các bước tương tự.