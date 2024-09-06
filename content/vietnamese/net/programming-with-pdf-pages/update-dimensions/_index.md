---
title: Cập nhật kích thước trang PDF
linktitle: Cập nhật kích thước trang PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Hướng dẫn từng bước để cập nhật kích thước trang PDF bằng Aspose.PDF cho .NET. Kiểm tra kích thước theo nhu cầu của bạn.
type: docs
weight: 150
url: /vi/net/programming-with-pdf-pages/update-dimensions/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước để cập nhật kích thước trang trong tài liệu PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích mã nguồn C# được đóng gói và cung cấp cho bạn hướng dẫn toàn diện để giúp bạn hiểu và triển khai tính năng này trong các dự án của riêng bạn. Vào cuối hướng dẫn này, bạn sẽ biết cách thay đổi kích thước trang trong tài liệu PDF bằng Aspose.PDF cho .NET.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#
- Aspose.PDF cho .NET được cài đặt trong môi trường phát triển của bạn

## Bước 1: Xác định thư mục tài liệu
Đầu tiên, bạn cần thiết lập đường dẫn đến thư mục tài liệu của mình. Đây là vị trí bạn muốn lưu tài liệu PDF đã chỉnh sửa. Thay thế "YOUR DOCUMENTS DIRECTORY" bằng đường dẫn thích hợp.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Mở tài liệu PDF
 Sau đó, bạn có thể mở tài liệu PDF hiện có bằng cách sử dụng`Document` lớp Aspose.PDF. Hãy chắc chắn chỉ định đường dẫn tài liệu chính xác.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Bước 3: Nhận Bộ sưu tập Trang
 Bây giờ bạn có thể truy cập vào bộ sưu tập trang của tài liệu PDF bằng cách sử dụng`Pages` tài sản của`Document` lớp học.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Bước 4: Lấy một trang cụ thể
Sau đó, bạn có thể chọn một trang cụ thể của tài liệu bằng cách sử dụng chỉ mục của trang trong bộ sưu tập. Trong ví dụ này, chúng tôi đang sử dụng trang thứ hai (chỉ mục 1).

```csharp
Page pdfPage = pageCollection[1];
```

## Bước 5: Xác định kích thước trang mới
 Bây giờ bạn có thể thiết lập kích thước trang mới bằng cách sử dụng`SetPageSize()` phương pháp của`Page`đối tượng. Trong ví dụ này, chúng tôi thiết lập kích thước trang thành A4 (11,7 x 8,3 inch), chuyển đổi thành điểm (1 inch = 72 điểm).

```csharp
pdfPage.SetPageSize(597.6, 842.4);
```

## Bước 6: Lưu tài liệu đã cập nhật
 Cuối cùng, bạn có thể lưu tài liệu PDF đã cập nhật vào một tệp bằng cách sử dụng`Save()` phương pháp của`Document`lớp. Hãy chắc chắn chỉ định đúng đường dẫn và tên tệp.

```csharp
dataDir = dataDir + "UpdateDimensions_out.pdf";
pdfDocument.Save(dataDir);
```

### Mã nguồn mẫu để Cập nhật Kích thước bằng Aspose.PDF cho .NET 

```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mở tài liệu
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Nhận bộ sưu tập trang
PageCollection pageCollection = pdfDocument.Pages;
// Lấy trang cụ thể
Page pdfPage = pageCollection[1];
// Đặt kích thước trang là A4 (11,7 x 8,3 in) và trong Aspose.Pdf, 1 inch = 72 điểm
// Vì vậy, kích thước A4 tính theo điểm sẽ là (842,4, 597,6)
pdfPage.SetPageSize(597.6, 842.4);
dataDir = dataDir + "UpdateDimensions_out.pdf";
// Lưu tài liệu đã cập nhật
pdfDocument.Save(dataDir);
System.Console.WriteLine("\nPage dimensions updated successfully.\nFile saved at " + dataDir);

```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách cập nhật kích thước của một trang trong tài liệu PDF bằng Aspose.PDF cho .NET. Bằng cách làm theo hướng dẫn từng bước này, bạn có thể dễ dàng thay đổi kích thước của một trang trong tài liệu PDF khi cần. Aspose.PDF cung cấp một API mạnh mẽ và linh hoạt để làm việc với các tệp PDF và thực hiện nhiều thao tác khác nhau, bao gồm thay đổi kích thước trang. Với kiến thức này, bạn có thể kiểm soát và tùy chỉnh kích thước của các trang PDF để đáp ứng nhu cầu cụ thể của mình.

### Câu hỏi thường gặp để cập nhật kích thước trang PDF

#### H: Làm thế nào tôi có thể cập nhật kích thước của một trang cụ thể trong tài liệu PDF bằng Aspose.PDF cho .NET?

A: Để cập nhật kích thước của một trang cụ thể trong tài liệu PDF bằng Aspose.PDF cho .NET, bạn có thể làm theo các bước sau:

1. Thiết lập thư mục tài liệu bằng cách chỉ định đường dẫn nơi tệp PDF gốc của bạn nằm và nơi bạn muốn lưu tệp PDF đã cập nhật. Thay thế "YOUR DOCUMENTS DIRECTORY" bằng đường dẫn thích hợp.
2.  Mở tài liệu PDF hiện có để cập nhật bằng cách sử dụng`Document` lớp Aspose.PDF. Hãy chắc chắn chỉ định đúng đường dẫn đến tài liệu PDF gốc.
3.  Truy cập bộ sưu tập trang của tài liệu PDF bằng cách sử dụng`Pages` tài sản của`Document` lớp học.
4. Chọn trang cụ thể mà bạn muốn cập nhật từ bộ sưu tập trang bằng cách sử dụng chỉ mục của trang. Trong mã nguồn C# được cung cấp, chúng tôi đang sử dụng trang thứ hai (chỉ mục 1).
5.  Xác định kích thước trang mới bằng cách sử dụng`SetPageSize()` phương pháp của`Page` đối tượng. Trong ví dụ, chúng tôi đặt kích thước trang thành khổ A4 (11,7 x 8,3 inch), chuyển đổi thành điểm (1 inch = 72 điểm).
6.  Lưu tài liệu PDF đã cập nhật vào một tệp bằng cách sử dụng`Save()` phương pháp của`Document`lớp. Hãy chắc chắn chỉ định đúng đường dẫn và tên tệp.

#### H: Tôi có thể cập nhật kích thước của nhiều trang trong tài liệu PDF cùng lúc không?

A: Có, bạn có thể sửa đổi mã nguồn được cung cấp để cập nhật kích thước của nhiều trang trong tài liệu PDF cùng lúc. Thay vì chọn một trang cụ thể (như được hiển thị trong bước 4), bạn có thể lặp qua tất cả các trang trong bộ sưu tập trang và đặt kích thước trang mong muốn cho mỗi trang.

#### H: Làm thế nào để chuyển đổi kích thước trang từ inch sang point khi sử dụng Aspose.PDF cho .NET?

 A: Trong Aspose.PDF cho .NET, đơn vị đo lường được sử dụng cho kích thước trang là điểm, trong đó 1 inch tương đương với 72 điểm. Để chuyển đổi inch sang điểm, bạn có thể sử dụng công thức:`points = inches * 72`. Ví dụ, để đặt kích thước trang là 11,7 x 8,3 inch, bạn có thể tính toán các kích thước tương ứng theo điểm là (11,7 * 72) và (8,3 * 72).

#### H: Việc cập nhật kích thước trang có ảnh hưởng đến bố cục nội dung của tài liệu PDF không?

A: Có, việc cập nhật kích thước của một trang sẽ ảnh hưởng đến bố cục nội dung của tài liệu PDF trên trang cụ thể đó. Khi bạn thay đổi kích thước trang, nội dung trên trang sẽ được điều chỉnh cho phù hợp với kích thước mới.

#### H: Có thể hoàn nguyên những thay đổi và khôi phục lại kích thước trang ban đầu sau khi cập nhật không?

A: Có, nếu bạn muốn khôi phục các thay đổi và khôi phục kích thước trang gốc, bạn có thể giữ một bản sao của tài liệu PDF gốc trước khi thực hiện thay đổi hoặc mở lại tài liệu PDF gốc mà không lưu các thay đổi. Theo cách này, kích thước ban đầu sẽ được giữ nguyên.