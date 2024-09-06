---
title: Nhận Thuộc tính PDF
linktitle: Nhận Thuộc tính PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Hướng dẫn từng bước để có được các thuộc tính PDF như kích thước hộp và góc quay bằng Aspose.PDF cho .NET.
type: docs
weight: 100
url: /vi/net/programming-with-pdf-pages/get-properties/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước để có được các thuộc tính của PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích mã nguồn C# được đóng gói và cung cấp cho bạn hướng dẫn toàn diện để giúp bạn hiểu và triển khai tính năng này trong các dự án của riêng bạn. Vào cuối hướng dẫn này, bạn sẽ biết cách truy cập các thuộc tính khác nhau của trang PDF như hộp nghệ thuật, hộp cắt, hộp cắt, v.v., bằng Aspose.PDF cho .NET.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#
- Aspose.PDF cho .NET được cài đặt trong môi trường phát triển của bạn

## Bước 1: Thiết lập thư mục tài liệu
Trước tiên, bạn cần thiết lập đường dẫn đến thư mục tài liệu của mình. Đây là vị trí của tệp PDF có thuộc tính bạn muốn lấy. Thay thế "YOUR DOCUMENTS DIRECTORY" bằng đường dẫn thích hợp.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Mở tài liệu PDF
 Tiếp theo, bạn cần mở tài liệu PDF bằng cách sử dụng`Document` lớp Aspose.PDF. Hãy chắc chắn chỉ định đúng đường dẫn đến tệp PDF.

```csharp
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

## Bước 3: Truy cập Bộ sưu tập trang
 Bây giờ bạn có thể truy cập vào bộ sưu tập trang của tài liệu bằng cách sử dụng`Pages` tài sản của`pdfDocument` sự vật.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Bước 4: Đi đến một trang cụ thể
Sau đó, bạn có thể nhảy đến một trang cụ thể bằng cách sử dụng chỉ mục của trang trong bộ sưu tập. Trong ví dụ dưới đây, chúng ta truy cập trang thứ hai (chỉ mục 1).

```csharp
Page pdfPage = pageCollection[1];
```

## Bước 5: Lấy thuộc tính trang
 Bây giờ bạn có thể có được các thuộc tính khác nhau của trang PDF, chẳng hạn như hộp nghệ thuật, hộp cắt, hộp cắt, v.v., bằng cách sử dụng các thuộc tính tương ứng của`pdfPage` sự vật.

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

### Mã nguồn mẫu cho Get Properties sử dụng Aspose.PDF cho .NET 

```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mở tài liệu
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
// Nhận bộ sưu tập trang
PageCollection pageCollection = pdfDocument.Pages;
// Lấy trang cụ thể
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
Xin chúc mừng! Bạn đã thành công trong việc lấy được các thuộc tính của PDF bằng Aspose.PDF cho .NET. Bạn đã học cách mở tài liệu PDF, điều hướng đến một trang cụ thể và lấy các thuộc tính trang khác nhau, chẳng hạn như hộp kích thước và xoay. Bây giờ bạn có thể sử dụng thông tin này để tùy chỉnh cách xử lý các tệp PDF của mình dựa trên các thuộc tính của chúng.

Hãy nhớ kiểm tra tài liệu chính thức Aspose.PDF dành cho .NET để biết thêm thông tin về các tính năng nâng cao và khả năng tùy chỉnh.

### Câu hỏi thường gặp

#### H: Làm thế nào tôi có thể lấy được các thuộc tính của PDF bằng Aspose.PDF cho .NET?

A: Để có được các thuộc tính của PDF bằng Aspose.PDF cho .NET, bạn có thể làm theo các bước sau:

1. Thiết lập thư mục tài liệu bằng cách chỉ định đường dẫn đến tệp PDF có thuộc tính mà bạn muốn lấy.
2.  Mở tài liệu PDF bằng cách sử dụng`Document` lớp Aspose.PDF, cung cấp đường dẫn chính xác đến tệp PDF.
3.  Truy cập bộ sưu tập trang của tài liệu bằng cách sử dụng`Pages` tài sản của`pdfDocument` sự vật.
4. Nhảy tới một trang cụ thể bằng cách sử dụng chỉ mục của trang đó trong bộ sưu tập (chỉ mục bắt đầu từ 1).
5.  Nhận các thuộc tính khác nhau của trang PDF, chẳng hạn như ArtBox, BleedBox, CropBox, MediaBox, TrimBox, Rect, Page Number và Rotation, bằng cách sử dụng các thuộc tính tương ứng của`pdfPage` sự vật.

#### H: Tôi có thể lấy những thuộc tính nào của trang PDF bằng Aspose.PDF cho .NET?

A: Bạn có thể lấy nhiều thuộc tính khác nhau của trang PDF bằng Aspose.PDF cho .NET, chẳng hạn như:

- ArtBox: Biểu thị kích thước của tác phẩm nghệ thuật trên trang.
- BleedBox: Biểu thị kích thước phần tràn lề của trang.
- CropBox: Biểu thị kích thước của nội dung hiển thị trên trang sau khi cắt.
- MediaBox: Biểu thị kích thước của phương tiện vật lý trên trang.
- TrimBox: Biểu thị kích thước của nội dung đã cắt bớt trên trang.
- Rect: Biểu thị kích thước của hộp giới hạn trang.
- Số trang: Biểu thị số trang trong tài liệu.
- Xoay: Biểu thị góc xoay của trang.

#### H: Làm thế nào để truy cập vào một trang cụ thể trong tài liệu PDF để lấy các thuộc tính của trang đó?

 A: Để truy cập một trang cụ thể trong tài liệu PDF và lấy các thuộc tính của nó, bạn có thể sử dụng`Pages` tài sản của`pdfDocument` đối tượng để truy cập bộ sưu tập các trang của tài liệu. Sau đó, bạn có thể sử dụng chỉ mục của trang trong bộ sưu tập để nhảy đến trang mong muốn. Ví dụ, để truy cập trang thứ hai, bạn có thể sử dụng`pdfDocument.Pages[1]` (chỉ mục bắt đầu từ 1).

#### H: Tôi có thể thực hiện các thao tác trên các thuộc tính đã truy xuất, chẳng hạn như sửa đổi hoặc thay đổi kích thước hộp trang không?

A: Có, sau khi bạn lấy các thuộc tính của trang PDF bằng Aspose.PDF cho .NET, bạn có thể thực hiện nhiều thao tác khác nhau trên chúng. Ví dụ, bạn có thể sửa đổi kích thước của các hộp trang, xoay trang hoặc sử dụng thông tin đã lấy để xử lý và thao tác tùy chỉnh tài liệu PDF.

#### H: Aspose.PDF cho .NET có hỗ trợ trích xuất thuộc tính từ các tệp PDF được mã hóa hoặc bảo vệ bằng mật khẩu không?

A: Có, Aspose.PDF cho .NET hỗ trợ trích xuất các thuộc tính từ các tệp PDF được mã hóa hoặc được bảo vệ bằng mật khẩu. Miễn là bạn cung cấp đúng mật khẩu để mở tài liệu PDF, bạn có thể truy cập và lấy các thuộc tính của nó bằng cách sử dụng cùng một phương pháp được trình bày trong hướng dẫn.