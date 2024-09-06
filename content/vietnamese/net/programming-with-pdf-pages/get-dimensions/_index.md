---
title: Nhận Kích thước Trang PDF
linktitle: Nhận Kích thước Trang PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Trong hướng dẫn này, chúng tôi giải thích cách lấy kích thước trang PDF và thực hiện thao tác bằng Aspose.PDF cho .NET. Các bước chi tiết được cung cấp để hướng dẫn bạn thực hiện quy trình.
type: docs
weight: 60
url: /vi/net/programming-with-pdf-pages/get-dimensions/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước để lấy kích thước trang trong tệp PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích mã nguồn C# được đóng gói và cung cấp cho bạn hướng dẫn toàn diện để giúp bạn hiểu và triển khai tính năng này trong các dự án của riêng bạn. Vào cuối hướng dẫn này, bạn sẽ biết cách lấy kích thước của một trang trong tệp PDF bằng Aspose.PDF cho .NET.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#
- Aspose.PDF cho .NET được cài đặt trong môi trường phát triển của bạn

## Bước 1: Xác định thư mục tài liệu
Đầu tiên, bạn cần thiết lập đường dẫn đến thư mục tài liệu của mình. Đây là vị trí lưu trữ tệp PDF của bạn. Thay thế "YOUR DOCUMENTS DIRECTORY" bằng đường dẫn phù hợp.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Mở tài liệu PDF
 Sau đó, bạn có thể mở tệp PDF bằng cách sử dụng`Document` lớp Aspose.PDF. Hãy chắc chắn chỉ định đúng đường dẫn đến tệp PDF.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Bước 3: Thêm một trang trống (nếu cần)
 Nếu tài liệu PDF đã chứa các trang, bạn có thể chuyển đến một trang hiện có bằng cách sử dụng chỉ mục`1` (trang đầu tiên có chỉ mục là 1). Nếu không, bạn có thể thêm trang mới vào tài liệu.

```csharp
Page page = pdfDocument.Pages.Count > 0? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

## Bước 4: Lấy kích thước trang
 Bây giờ bạn có thể lấy kích thước trang bằng cách sử dụng`GetPageRect()` phương pháp của`Page` đối tượng. Phương pháp này trả về một`Rectangle` đối tượng chứa các kích thước của trang. Bạn có thể truy cập chiều rộng và chiều cao bằng cách sử dụng`Width` Và`Height` của cải.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

## Bước 5: Xoay trang
 Nếu bạn muốn xoay trang, bạn có thể sử dụng`Rotate` tài sản của`Page`đối tượng. Trong ví dụ này, trang được xoay 90 độ.

```csharp
page. Rotate = Rotate. on90;
```

## Bước 6: Lấy lại kích thước trang
 Sau khi xoay trang, bạn có thể lấy lại kích thước trang bằng cách sử dụng`GetPageRect()` phương pháp.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

### Mã nguồn mẫu cho Get Dimensions sử dụng Aspose.PDF cho .NET 

```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mở tài liệu
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Thêm một trang trống vào tài liệu pdf
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
// Nhận thông tin chiều cao và chiều rộng của trang
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
// Xoay trang ở góc 90 độ
page.Rotate = Rotation.on90;
// Nhận thông tin chiều cao và chiều rộng của trang
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);

```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách lấy kích thước của một trang trong tệp PDF bằng Aspose.PDF cho .NET. Bằng cách làm theo các bước được cung cấp, bạn có thể dễ dàng trích xuất kích thước trang và thực hiện các thao tác xử lý PDF khác. Aspose.PDF cho .NET cung cấp tính linh hoạt tuyệt vời để làm việc với các tệp PDF và cho phép bạn phát triển các giải pháp mạnh mẽ và tùy chỉnh.

Bạn có thể thoải mái khám phá thêm tài liệu của Aspose.PDF để tìm hiểu tất cả các tính năng mà thư viện này cung cấp.

### Câu hỏi thường gặp để lấy kích thước trang PDF

#### H: Làm thế nào để lấy được kích thước của một trang cụ thể trong tệp PDF?

A: Để có được kích thước của một trang cụ thể trong tệp PDF, bạn có thể sử dụng`GetPageRect()` phương pháp của`Page` đối tượng trong Aspose.PDF cho .NET. Phương pháp này trả về một`Rectangle` đối tượng chứa kích thước (chiều rộng và chiều cao) của trang.

####  Q: Cái gì làm`GetPageRect(true)` method do in the provided C# source code?

 A: Cái`GetPageRect(true)` phương pháp trong mã nguồn C# được cung cấp trả về kích thước của trang sau khi áp dụng bất kỳ phép xoay nào. Nếu trang được xoay, phương pháp sẽ trả về kích thước của trang được xoay, có thể khác với kích thước ban đầu.

#### H: Tôi có thể lấy kích thước của tất cả các trang trong tài liệu PDF bằng Aspose.PDF cho .NET không?

 A: Có, bạn có thể lấy kích thước của tất cả các trang trong tài liệu PDF bằng cách lặp lại qua`Pages` bộ sưu tập của`Document` đối tượng và sử dụng`GetPageRect(true)` phương pháp cho từng trang.

#### H: Làm thế nào tôi có thể xác định hướng của một trang (dọc hay ngang) dựa trên kích thước của nó?

A: Để xác định hướng của một trang dựa trên kích thước của nó, bạn có thể so sánh chiều rộng và chiều cao của trang. Nếu chiều rộng lớn hơn chiều cao, trang sẽ ở hướng ngang, và nếu chiều cao lớn hơn chiều rộng, trang sẽ ở hướng dọc.

#### H: Tôi có thể sửa đổi kích thước của trang bằng Aspose.PDF cho .NET không?

 A: Có, bạn có thể sửa đổi kích thước của một trang trong Aspose.PDF cho .NET. Sau khi nhận được`Rectangle` Đối tượng đại diện cho kích thước trang, bạn có thể điều chỉnh chiều rộng và chiều cao theo yêu cầu của mình và sau đó áp dụng các thay đổi vào trang.