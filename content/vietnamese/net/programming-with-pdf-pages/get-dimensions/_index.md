---
title: Nhận kích thước trang PDF
linktitle: Nhận kích thước trang PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Trong hướng dẫn này, chúng tôi giải thích cách lấy kích thước trang PDF và thực hiện các thao tác bằng Aspose.PDF cho .NET. Các bước chi tiết được cung cấp để hướng dẫn bạn trong suốt quá trình.
type: docs
weight: 60
url: /vi/net/programming-with-pdf-pages/get-dimensions/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình từng bước để lấy kích thước trang trong tệp PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích mã nguồn C# đi kèm và cung cấp cho bạn hướng dẫn toàn diện để giúp bạn hiểu và triển khai tính năng này trong các dự án của riêng bạn. Ở cuối hướng dẫn này, bạn sẽ biết cách lấy kích thước của một trang trong tệp PDF bằng Aspose.PDF cho .NET.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Có kiến thức cơ bản về ngôn ngữ lập trình C#
- Aspose.PDF cho .NET được cài đặt trong môi trường phát triển của bạn

## Bước 1: Xác định thư mục tài liệu
Đầu tiên, bạn cần đặt đường dẫn đến thư mục tài liệu của mình. Đây là vị trí chứa tệp PDF của bạn. Thay thế "THƯ VIỆN TÀI LIỆU CỦA BẠN" bằng đường dẫn thích hợp.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Mở tài liệu PDF
 Sau đó, bạn có thể mở tệp PDF bằng cách sử dụng`Document` lớp Aspose.PDF. Đảm bảo chỉ định đường dẫn chính xác đến tệp PDF.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Bước 3: Thêm trang trống (nếu cần)
 Nếu tài liệu PDF đã chứa các trang, bạn có thể chuyển tới trang hiện có bằng cách sử dụng chỉ mục`1` (trang đầu tiên có chỉ số là 1). Nếu không, bạn có thể thêm một trang mới vào tài liệu.

```csharp
Page page = pdfDocument.Pages.Count > 0? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

## Bước 4: Lấy kích thước trang
 Bây giờ bạn có thể lấy kích thước trang bằng cách sử dụng`GetPageRect()` phương pháp của`Page` sự vật. Phương thức này trả về một`Rectangle` đối tượng chứa kích thước của trang. Bạn có thể truy cập chiều rộng và chiều cao bằng cách sử dụng`Width` Và`Height` của cải.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

## Bước 5: Xoay trang
 Nếu bạn muốn xoay trang, bạn có thể sử dụng`Rotate` tài sản của`Page`sự vật. Trong ví dụ này, trang được xoay 90 độ.

```csharp
page. Rotate = Rotate. on90;
```

## Bước 6: Lấy lại kích thước trang
 Sau khi xoay trang, bạn có thể lấy lại kích thước trang bằng cách sử dụng`GetPageRect()` phương pháp.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

### Mã nguồn mẫu để Nhận thứ nguyên bằng Aspose.PDF cho .NET 

```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mở tài liệu
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Thêm một trang trống vào tài liệu pdf
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
// Nhận thông tin về chiều cao và chiều rộng của trang
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
// Xoay trang một góc 90 độ
page.Rotate = Rotation.on90;
// Nhận thông tin về chiều cao và chiều rộng của trang
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);

```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã tìm hiểu cách lấy kích thước của một trang trong tệp PDF bằng Aspose.PDF cho .NET. Bằng cách làm theo các bước được cung cấp, bạn có thể dễ dàng trích xuất kích thước trang và thực hiện các thao tác thao tác PDF khác. Aspose.PDF for .NET mang đến sự linh hoạt tuyệt vời khi làm việc với các tệp PDF và cho phép bạn phát triển các giải pháp mạnh mẽ và tùy chỉnh.

Vui lòng khám phá thêm tài liệu của Aspose.PDF để khám phá tất cả các tính năng được thư viện này cung cấp.

### Câu hỏi thường gặp để lấy kích thước trang PDF

#### H: Làm cách nào tôi có thể nhận được kích thước của một trang cụ thể trong tệp PDF?

Đáp: Để biết kích thước của một trang cụ thể trong tệp PDF, bạn có thể sử dụng`GetPageRect()` phương pháp của`Page` đối tượng trong Aspose.PDF cho .NET. Phương thức này trả về một`Rectangle` đối tượng chứa kích thước (chiều rộng và chiều cao) của trang.

####  Hỏi: Cái gì làm`GetPageRect(true)` method do in the provided C# source code?

 Đáp: Cái`GetPageRect(true)` phương thức trong mã nguồn C# được cung cấp sẽ trả về kích thước của trang sau khi áp dụng bất kỳ phép xoay nào. Nếu trang được xoay, phương thức sẽ trả về kích thước của trang được xoay, có thể khác với kích thước ban đầu.

#### Câu hỏi: Tôi có thể lấy kích thước của tất cả các trang trong tài liệu PDF bằng Aspose.PDF cho .NET không?

 Trả lời: Có, bạn có thể lấy kích thước của tất cả các trang trong tài liệu PDF bằng cách lặp qua`Pages` bộ sưu tập của`Document` đối tượng và sử dụng`GetPageRect(true)` phương pháp cho từng trang.

#### Câu hỏi: Làm cách nào tôi có thể xác định hướng của trang (dọc hoặc ngang) dựa trên kích thước của trang?

Đáp: Để xác định hướng của trang dựa trên kích thước của nó, bạn có thể so sánh chiều rộng và chiều cao của trang. Nếu chiều rộng lớn hơn chiều cao thì trang sẽ ở hướng ngang và nếu chiều cao lớn hơn chiều rộng thì trang sẽ ở hướng dọc.

#### Câu hỏi: Tôi có thể sửa đổi kích thước của trang bằng Aspose.PDF cho .NET không?

 Trả lời: Có, bạn có thể sửa đổi kích thước của một trang trong Aspose.PDF cho .NET. Sau khi nhận được`Rectangle` đối tượng đại diện cho kích thước trang, bạn có thể điều chỉnh chiều rộng và chiều cao theo yêu cầu của mình, sau đó áp dụng các thay đổi cho trang.