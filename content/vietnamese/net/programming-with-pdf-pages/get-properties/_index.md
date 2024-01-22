---
title: Nhận thuộc tính PDF
linktitle: Nhận thuộc tính PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Hướng dẫn từng bước để lấy các thuộc tính PDF như kích thước hộp và xoay bằng Aspose.PDF cho .NET.
type: docs
weight: 100
url: /vi/net/programming-with-pdf-pages/get-properties/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình từng bước để có được các thuộc tính của tệp PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích mã nguồn C# đi kèm và cung cấp cho bạn hướng dẫn toàn diện để giúp bạn hiểu và triển khai tính năng này trong các dự án của riêng bạn. Ở cuối hướng dẫn này, bạn sẽ biết cách truy cập các thuộc tính khác nhau của trang PDF như hộp nghệ thuật, hộp cắt, hộp cắt, v.v. bằng cách sử dụng Aspose.PDF cho .NET.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Có kiến thức cơ bản về ngôn ngữ lập trình C#
- Aspose.PDF cho .NET được cài đặt trong môi trường phát triển của bạn

## Bước 1: Đặt thư mục tài liệu
Đầu tiên, bạn cần đặt đường dẫn đến thư mục tài liệu của mình. Đây là vị trí của tệp PDF có thuộc tính bạn muốn lấy. Thay thế "THƯ VIỆN TÀI LIỆU CỦA BẠN" bằng đường dẫn thích hợp.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Mở tài liệu PDF
 Tiếp theo, bạn cần mở tài liệu PDF bằng cách sử dụng`Document` lớp Aspose.PDF. Đảm bảo chỉ định đường dẫn chính xác đến tệp PDF.

```csharp
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

## Bước 3: Truy cập Bộ sưu tập Trang
 Bây giờ bạn có thể truy cập bộ sưu tập trang của tài liệu bằng cách sử dụng`Pages` tài sản của`pdfDocument` sự vật.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Bước 4: Đi đến một trang cụ thể
Sau đó, bạn có thể chuyển đến một trang cụ thể bằng cách sử dụng chỉ mục của trang trong bộ sưu tập. Trong ví dụ bên dưới, chúng ta truy cập trang thứ hai (chỉ mục 1).

```csharp
Page pdfPage = pageCollection[1];
```

## Bước 5: Lấy thuộc tính trang
 Bây giờ bạn có thể lấy các thuộc tính khác nhau của trang PDF, chẳng hạn như hộp nghệ thuật, hộp cắt, hộp cắt, v.v., bằng cách sử dụng các thuộc tính tương ứng của`pdfPage` sự vật.

```csharp
Console.WriteLine("ArtBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
Console.WriteLine("BleedBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.BleedBox.Height, pdf

Page.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
Console.WriteLine("CropBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
Console.WriteLine("MediaBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
Console.WriteLine("TrimBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
Console.WriteLine("Rect: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
Console.WriteLine("Page number: {0}", pdfPage.Number);
Console.WriteLine("Rotate: {0}", pdfPage.Rotate);
```

### Mã nguồn mẫu cho Nhận thuộc tính bằng Aspose.PDF cho .NET 

```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mở tài liệu
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
// Nhận bộ sưu tập trang
PageCollection pageCollection = pdfDocument.Pages;
// Nhận trang cụ thể
Page pdfPage = pageCollection[1];
// Nhận thuộc tính trang
System.Console.WriteLine("ArtBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
System.Console.WriteLine("BleedBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.BleedBox.Height, pdfPage.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
System.Console.WriteLine("CropBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
System.Console.WriteLine("MediaBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
System.Console.WriteLine("TrimBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
System.Console.WriteLine("Rect : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
System.Console.WriteLine("Page Number : {0}", pdfPage.Number);
System.Console.WriteLine("Rotate : {0}", pdfPage.Rotate);

```

## Phần kết luận
Xin chúc mừng! Bạn đã lấy thành công các thuộc tính của tệp PDF bằng Aspose.PDF cho .NET. Bạn đã học cách mở tài liệu PDF, điều hướng đến một trang cụ thể và nhận các thuộc tính trang khác nhau, chẳng hạn như hộp kích thước và góc xoay. Bây giờ bạn có thể sử dụng thông tin này để tùy chỉnh việc xử lý tệp PDF của mình dựa trên thuộc tính của chúng.

Hãy nhớ xem tài liệu chính thức của Aspose.PDF cho .NET để biết thêm thông tin về các tính năng nâng cao và khả năng tùy chỉnh.

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể lấy các thuộc tính của tệp PDF bằng Aspose.PDF cho .NET?

Trả lời: Để lấy các thuộc tính của tệp PDF bằng Aspose.PDF cho .NET, bạn có thể làm theo các bước sau:

1. Đặt thư mục tài liệu bằng cách chỉ định đường dẫn đến tệp PDF có thuộc tính bạn muốn truy xuất.
2.  Mở tài liệu PDF bằng cách sử dụng`Document` lớp Aspose.PDF, cung cấp đường dẫn chính xác tới tệp PDF.
3.  Truy cập bộ sưu tập trang của tài liệu bằng cách sử dụng`Pages` tài sản của`pdfDocument` sự vật.
4. Chuyển đến một trang cụ thể bằng cách sử dụng chỉ mục của trang trong bộ sưu tập (lập chỉ mục bắt đầu từ 1).
5.  Nhận các thuộc tính khác nhau của trang PDF, chẳng hạn như ArtBox, BleedBox, CropBox, MediaBox, TrimBox, Rect, Page Number và Rotation, bằng cách sử dụng các thuộc tính tương ứng của`pdfPage` sự vật.

#### Câu hỏi: Các thuộc tính khác nhau của trang PDF mà tôi có thể truy xuất bằng Aspose.PDF cho .NET là gì?

Trả lời: Bạn có thể truy xuất các thuộc tính khác nhau của trang PDF bằng Aspose.PDF cho .NET, chẳng hạn như:

- ArtBox: Thể hiện kích thước của tác phẩm nghệ thuật của trang.
- BleedBox: Thể hiện kích thước tràn lề của trang.
- CropBox: Thể hiện kích thước của nội dung hiển thị của trang sau khi cắt xén.
- MediaBox: Thể hiện kích thước của phương tiện vật lý của trang.
- TrimBox: Thể hiện kích thước của nội dung được cắt bớt của trang.
- Rect: Biểu thị kích thước của khung giới hạn của trang.
- Số trang: Thể hiện số trang trong tài liệu.
- Xoay: Thể hiện góc xoay của trang.

#### Hỏi: Làm cách nào để truy cập một trang cụ thể trong tài liệu PDF để truy xuất các thuộc tính của nó?

 Đáp: Để truy cập một trang cụ thể trong tài liệu PDF và truy xuất các thuộc tính của nó, bạn có thể sử dụng`Pages` tài sản của`pdfDocument` đối tượng để truy cập vào bộ sưu tập trang của tài liệu. Sau đó, bạn có thể sử dụng chỉ mục của trang trong bộ sưu tập để chuyển đến trang mong muốn. Ví dụ: để truy cập trang thứ hai, bạn có thể sử dụng`pdfDocument.Pages[1]` (lập chỉ mục bắt đầu từ 1).

#### Câu hỏi: Tôi có thể thực hiện các thao tác trên thuộc tính được truy xuất, chẳng hạn như sửa đổi hoặc thay đổi kích thước hộp trang không?

Trả lời: Có, khi bạn truy xuất các thuộc tính của trang PDF bằng Aspose.PDF cho .NET, bạn có thể thực hiện nhiều thao tác khác nhau trên chúng. Ví dụ: bạn có thể sửa đổi kích thước của hộp trang, xoay trang hoặc sử dụng thông tin được truy xuất để xử lý và thao tác tùy chỉnh đối với tài liệu PDF.

#### Câu hỏi: Aspose.PDF for .NET có hỗ trợ trích xuất các thuộc tính từ các tệp PDF được mã hóa hoặc bảo vệ bằng mật khẩu không?

Trả lời: Có, Aspose.PDF for .NET hỗ trợ trích xuất các thuộc tính từ các tệp PDF được mã hóa hoặc bảo vệ bằng mật khẩu. Miễn là bạn cung cấp mật khẩu chính xác để mở tài liệu PDF, bạn có thể truy cập và truy xuất các thuộc tính của nó bằng cách sử dụng phương pháp tương tự được trình bày trong hướng dẫn.