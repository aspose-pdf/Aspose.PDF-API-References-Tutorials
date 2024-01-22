---
title: Nhận tất cả chú thích từ trang
linktitle: Nhận tất cả chú thích từ trang
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách sử dụng Aspose.PDF cho .NET để truy xuất tất cả chú thích từ trang PDF bằng hướng dẫn từng bước này.
type: docs
weight: 70
url: /vi/net/annotations/getallannotationsfrompage/
---
Bài viết này sẽ hướng dẫn bạn quy trình trích xuất tất cả chú thích từ trang PDF bằng Aspose.PDF cho .NET. Aspose.PDF for .NET là thư viện cho phép các nhà phát triển tạo, chỉnh sửa và chuyển đổi tài liệu PDF. Với sự trợ giúp của hướng dẫn này, bạn sẽ có thể nhận được tất cả các chú thích từ một trang PDF cụ thể bằng mã nguồn C# được cung cấp.

Thực hiện theo các bước bên dưới để nhận tất cả Chú thích cho trang PDF bằng Aspose.PDF cho .NET:

## Bước 1: Đường dẫn đến thư mục tài liệu

Bước đầu tiên để nhận tất cả chú thích từ trang PDF bằng Aspose.PDF cho .NET là đặt đường dẫn đến thư mục tài liệu nơi lưu trữ tệp PDF của bạn. Bạn có thể làm điều này bằng cách sửa đổi dòng mã sau:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
## Bước 2: Tệp PDF của bạn được lưu trữ

Thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn đến thư mục lưu trữ tệp PDF của bạn. Ví dụ:

```csharp
string dataDir = @"C:\Users\JohnDoe\Documents\PDFs\";
```

## Bước 3: Mở tài liệu

Bước tiếp theo là mở tài liệu PDF có chứa các chú thích bạn muốn trích xuất. Bạn có thể làm điều này bằng cách thêm đoạn mã sau:

```csharp
Document pdfDocument = new Document(dataDir + "GetAllAnnotationsFromPage.pdf");
```

Dòng mã này khởi tạo một phiên bản mới của lớp Tài liệu và tải tài liệu PDF "GetAllAnnotationsFromPage.pdf". Thay thế tên tệp này bằng tên tệp PDF của bạn.

## Bước 4: Lặp lại tất cả các chú thích

Khi bạn đã mở tài liệu PDF, bạn có thể lặp qua tất cả các chú thích trên một trang cụ thể. Ví dụ: để lặp qua tất cả các chú thích trên trang đầu tiên của tài liệu PDF, hãy thêm mã sau:

```csharp
foreach (MarkupAnnotation annotation in pdfDocument.Pages[1].Annotations)
{
    // Mã ở đây
}
```

Mã này lặp qua tất cả các chú thích trên trang đầu tiên của tài liệu PDF và gán từng chú thích cho biến "chú thích".

## Bước 5: Nhận thuộc tính chú thích

Để trích xuất các thuộc tính của từng chú thích, bạn có thể thêm đoạn mã sau vào vòng lặp foreach:

```csharp
Console.WriteLine("Title : {0} ", annotation.Title);
Console.WriteLine("Subject : {0} ", annotation.Subject);
Console.WriteLine("Contents : {0} ", annotation.Contents);
```

Mã này ghi Tiêu đề, Chủ đề và Nội dung của từng chú thích vào bảng điều khiển.

### Mã nguồn ví dụ để nhận tất cả chú thích từ trang bằng Aspose.PDF cho .NET

Đây là mã nguồn hoàn chỉnh để nhận tất cả chú thích từ trang PDF bằng Aspose.PDF cho .NET:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mở tài liệu
Document pdfDocument = new Document(dataDir + "GetAllAnnotationsFromPage.pdf");

// Lặp lại tất cả các chú thích
foreach (MarkupAnnotation annotation in pdfDocument.Pages[1].Annotations)
{
	// Nhận thuộc tính chú thích
	Console.WriteLine("Title : {0} ", annotation.Title);
	Console.WriteLine("Subject : {0} ", annotation.Subject);
	Console.WriteLine("Contents : {0} ", annotation.Contents);                
}
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã khám phá cách lấy tất cả chú thích từ một trang cụ thể của tài liệu PDF bằng Aspose.PDF cho .NET. Bằng cách làm theo hướng dẫn từng bước và sử dụng mã nguồn C# được cung cấp, nhà phát triển có thể dễ dàng trích xuất và quản lý chú thích từ tài liệu PDF của họ.

### Câu hỏi thường gặp

#### Hỏi: Chú thích trong tài liệu PDF là gì?

Đáp: Chú thích trong tài liệu PDF là các thành phần tương tác cung cấp thông tin, nhận xét hoặc ghi chú bổ sung về các phần cụ thể của tài liệu. Chú thích có thể bao gồm ghi chú văn bản, nhận xét, đánh dấu và các yếu tố tương tác khác.

#### Hỏi: Tôi có thể chỉ nhận chú thích từ các trang cụ thể không?

Đáp: Có, với Aspose.PDF cho .NET, bạn có thể nhận chú thích từ các trang cụ thể hoặc thậm chí từ toàn bộ tài liệu, tùy thuộc vào yêu cầu của bạn.

#### Câu hỏi: Aspose.PDF cho .NET có hỗ trợ trích xuất chú thích từ các tệp PDF được bảo vệ bằng mật khẩu không?

 Trả lời: Có, Aspose.PDF for .NET hỗ trợ trích xuất chú thích từ các tệp PDF được bảo vệ bằng mật khẩu. Bạn cần cung cấp mật khẩu chính xác khi tải tài liệu PDF bằng cách sử dụng`Document` lớp học.

#### Câu hỏi: Tôi có thể lọc chú thích dựa trên thuộc tính của chúng, chẳng hạn như nội dung hoặc tác giả không?

Trả lời: Có, Aspose.PDF cho .NET cung cấp các phương thức để truy cập và lọc chú thích dựa trên thuộc tính của chúng, chẳng hạn như nội dung, tác giả hoặc ngày tạo. Bạn có thể lặp qua tất cả các chú thích và kiểm tra các thuộc tính cụ thể mà bạn muốn lọc.

#### Câu hỏi: Aspose.PDF for .NET có hỗ trợ trích xuất chú thích từ các loại tài liệu PDF khác nhau không?

Trả lời: Có, Aspose.PDF cho .NET cung cấp nhiều phương pháp khác nhau để trích xuất chú thích từ các loại tài liệu PDF khác nhau, bao gồm chú thích đánh dấu văn bản, chú thích văn bản miễn phí, v.v.